# Instructions: Setting Up Linked Mentions for Syllabus Sections

## Overview

This document explains how to add collapsible "Linked Mentions" sections to your syllabus that automatically display all the bullet points from your notes that link to each specific syllabus section.

## Requirements

- **Dataview plugin** must be installed and enabled in Obsidian
- Your notes must contain links to syllabus sections in this format: `[[mmed_anaes_part_a_syllabus#Section Name|ⓘ]]`

## How It Works

1. The DataviewJS code searches all files in the "ANAESTHESIA CONTENT" folder
2. It reads the content of files that link to the syllabus
3. It finds lines containing links to a specific section
4. It identifies the nearest heading above each linked line
5. It groups results by heading and displays them in individually collapsible sections
6. Each heading name is a clickable link that jumps to that section in the source note
7. Results are sorted by page name, then by heading name
8. Shows total count of mentions and sections at the top

## Template Code

Place this code block under any section header in your syllabus:

```markdown
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "SECTION_NAME_HERE";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus"))
> );
>
> // For each page that links here, read its content
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>
>         // Find lines with the specific section link
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 // Find the nearest heading above this line
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>
>                 // Capture indentation level before cleaning
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>
>                 // Remove the link syntax for cleaner display
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 // Remove leading bullet marker and whitespace
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 // Convert markdown bold to HTML
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>
>                 // Create link to the heading
>                 let locationLink = heading
>                     ? dv.fileLink(page.file.path, false, heading)
>                     : page.file.link;
>
>                 results.push({
>                     content: cleanLine.trim(),
>                     indentLevel: indentLevel,
>                     location: locationLink,
>                     pageName: page.file.name,
>                     filePath: page.file.path,
>                     headingName: heading || "No heading",
>                     headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link
>                 });
>             }
>         }
>     }
> }
>
> if (results.length > 0) {
>     // Group by heading
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {
>                 pageName: r.pageName,
>                 filePath: r.filePath,
>                 headingName: r.headingName,
>                 headingLink: r.headingLink,
>                 items: []
>             };
>         }
>         grouped[key].items.push(r);
>     }
>
>     // Sort groups
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>
>     // Create collapsible section for each heading
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>
>         // Create clickable internal link
>         const link = summary.createEl("a", {
>             cls: "internal-link",
>             href: group.filePath
>         });
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>
>         // Add count
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>
>         // Create content list
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             // Apply indentation based on original nesting level
>             if (item.indentLevel > 0) {
>                 li.style.marginLeft = `${item.indentLevel * 20}px`;
>             }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
```

## Step-by-Step Instructions

### 1. Identify the Section Header

Find the section in your syllabus where you want to add linked mentions. For example:

```markdown
#### Basic Physical and Mathematical Principles
```

### 2. Copy the Template

Copy the entire template code block above (including the callout wrapper).

### 3. Paste Under the Header

Paste it directly under the section header, typically after any existing comments:

```markdown
#### Basic Physical and Mathematical Principles
<!-- covered-by: [[some links]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> ...
```

### 4. Customize the Section Name

Change line 2 of the DataviewJS code to match the exact section header name:

```javascript
let targetSection = "Basic Physical and Mathematical Principles";
```

**Important:** The section name must match EXACTLY as it appears in your wikilinks from notes.

### 5. Test in Reading View

Switch to Reading View to see the collapsible callout appear. Click the arrow to expand/collapse it.

## Customization Options

### Change the Callout Type

Change `[!info]-` to other callout types:
- `[!note]-` - Note style (blue)
- `[!tip]-` - Tip style (green)
- `[!warning]-` - Warning style (yellow)
- `[!abstract]-` - Abstract style (cyan)

### Keep it Expanded by Default

Remove the `-` after the callout type:
```markdown
> [!info] 📎 Linked Mentions
```

### Change the Icon

Replace `📎` with any emoji:
- `🔗` Link
- `📌` Pin
- `📋` Clipboard
- `🔍` Search
- `↩️` Back arrow

### Modify Display Format

The current implementation groups results by heading and displays them as collapsible sections with bullet lists. Each heading is a clickable link that navigates to that section in the source note.

### Change Sort Order

Current default: Sorts by page name first, then by heading name within each page.

To sort in reverse order:
```javascript
results.sort((a, b) => {
    let pageCompare = b.pageName.localeCompare(a.pageName);
    if (pageCompare !== 0) return pageCompare;
    return b.headingName.localeCompare(a.headingName);
});
```

To sort by content only:
```javascript
results.sort((a, b) => a.content.localeCompare(b.content));
```

To sort by heading first, then page:
```javascript
results.sort((a, b) => {
    let headingCompare = a.headingName.localeCompare(b.headingName);
    if (headingCompare !== 0) return headingCompare;
    return a.pageName.localeCompare(b.pageName);
});
```

## Troubleshooting

### "No backlinks found to this section"

**Possible causes:**
1. The `targetSection` name doesn't exactly match the section anchor in your links
2. No notes actually link to this section yet
3. The section name has special characters that need exact matching

**Solution:** Check your note links and ensure they use the exact section name.

### Links are not clickable

**Cause:** The link creation code is not properly configured

**Solution:** Ensure the code creates `<a>` elements with:
- `cls: "internal-link"` class
- `data-href` attribute with the full path including heading anchor
- Proper `textContent` for the heading name

Example:
```javascript
const link = summary.createEl("a", {
    cls: "internal-link",
    href: group.filePath
});
link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
link.textContent = group.headingName;
```

### Callout not collapsible

**Cause:** The DataviewJS block is outside the callout

**Solution:** Ensure every line of the dataviewjs block starts with `> ` (including the triple backticks)

### Individual sections not collapsible

**Cause:** The `<details>` and `<summary>` elements are not properly structured

**Solution:** Verify that each group uses `dv.el("details", "")` and `details.createEl("summary")` to create the collapsible structure. The content list must be a child of the `details` element.

### Query is slow

**Cause:** Reading file contents for many files can be slow

**Solution:** This is expected behavior. The query runs each time you open the file in reading view.

## Advanced: Batch Application

To apply this to multiple sections at once:

1. Create a list of all section names you want to add
2. Copy the template for each section
3. Use find-and-replace to update the `targetSection` variable for each one
4. Paste all blocks into your syllabus file

## Example: Multiple Sections

```markdown
#### Basic Physical and Mathematical Principles

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Basic Physical and Mathematical Principles";
> [rest of code...]
> ```

**Mathematical Concepts:**
- Exponential functions
- Integration

#### Behavior of Gases, Liquids and Vapors

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Behavior of Gases, Liquids and Vapors";
> [rest of code...]
> ```

- Laws governing the behavior of gases
```

## Technical Implementation Notes

### Clickable Links
The heading links are created as proper Obsidian internal links using HTML `<a>` elements:
- **Class:** `internal-link` (Obsidian's standard class for internal links)
- **href attribute:** File path only
- **data-href attribute:** Full path including heading anchor (`filePath#headingName`)
- **textContent:** The heading name to display

This approach works because Obsidian recognizes `<a>` elements with the `internal-link` class and `data-href` attributes as navigable internal links.

**Why not use markdown or `dv.fileLink()`?**
- Markdown `[[...]]` syntax doesn't render as links when embedded in HTML elements
- `dv.fileLink()` returns a Dataview link object, not a DOM element, so it can't be directly appended to HTML
- `dv.renderValue()` and `MarkdownRenderer.renderMarkdown()` are not available in DataviewJS scope

### Collapsible Sections
Each heading group uses native HTML `<details>` and `<summary>` elements:
- `dv.el("details", "")` creates the container
- `details.createEl("summary")` creates the clickable header
- Content is nested inside the `details` element as a `<ul>` list

This provides native browser-based collapse/expand functionality without requiring custom CSS or JavaScript.

### Grouping Logic
Results are grouped by a composite key of `pageName::headingName` to ensure that:
- Multiple mentions under the same heading are grouped together
- Each unique heading in each page gets its own collapsible section
- Proper sorting by page name first, then heading name

### Content Formatting
The content from your notes is cleaned and formatted before display:
1. **Capture indentation:** `^(\s*)` - Captures leading spaces before processing (2 spaces = 1 indent level)
2. **Remove wikilinks:** `\[\[.*?\]\]` - Removes all `[[link]]` syntax
3. **Remove bullet markers:** `^\s*[\*\-]\s*` - Removes leading `*` or `-` and whitespace
4. **Convert bold formatting:** `\*\*text\*\*` → `<strong>text</strong>` - Converts markdown bold to HTML
5. **Apply indentation:** `marginLeft = indentLevel * 20px` - Preserves visual nesting with left margin
6. **Render as HTML:** Uses `innerHTML` instead of `textContent` to properly display formatted content

This ensures the content displays cleanly with proper formatting (bold text, indentation, etc.) without duplicate bullets or visible link syntax. Nested bullet points maintain their visual hierarchy.

## General Notes

- The query only runs in **Reading View**, not in Edit Mode
- Results are grouped by heading and sorted by note name, then by heading name within each note
- The main callout is collapsed by default (use `[!info]` instead of `[!info]-` to keep it expanded)
- If no heading is found above a line, it will be grouped under "No heading"
- Total count of mentions and sections is displayed at the top

## Support

If you encounter issues:
1. Check that Dataview plugin is enabled
2. Verify the folder path is correct: `"ANAESTHESIA CONTENT"`
3. Check browser console for JavaScript errors (Ctrl+Shift+I or Cmd+Option+I)
4. Ensure your links use the exact section header text
