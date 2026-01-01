# Prompt: Fix Collapsible Grouped Linked Mentions in Obsidian

## Context

I have an Obsidian vault with medical study notes. I've set up a DataviewJS query in my syllabus file that displays "linked mentions" - showing all bullet points from my notes that link to specific syllabus sections.

## Current Setup

**Files involved:**
- Syllabus: `/Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/mmed_anaes_part_a_syllabus.md`
- Example note: `/Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS.md`
- Instructions: `/Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/INSTRUCTIONS_Linked_Mentions_Setup.md`

**Link format in notes:**
```markdown
* **Amplitude:** The maximal displacement of a graph or wave from the x axis    [[mmed_anaes_part_a_syllabus#Basic Physical and Mathematical Principles|ⓘ]].
```

**Current code location:**
The DataviewJS code is in the syllabus under section "Basic Physical and Mathematical Principles" (around line 892-989).

## What Currently Works

1. ✅ The query finds all lines that link to a specific syllabus section
2. ✅ It identifies the nearest heading above each linked line
3. ✅ It groups results by heading
4. ✅ The main callout is collapsible
5. ✅ It shows total counts

## What's NOT Working

1. ❌ **Heading links are not clickable** - The heading names show as plain text instead of clickable links
2. ❌ **Individual sections are not collapsible** - Each heading group should have its own collapse/expand, but they don't work

## Desired Behavior

I want the output to look like this:

```
📎 Linked Mentions [click to expand main callout]
  ↓ When expanded:

  Total: 45 mentions across 8 sections
  ---

  ▶ [1.1.1. AMPLITUDE, FREQUENCY, AND WAVELENGTH] (7)  ← clickable link, collapsed by default
    ↓ When expanded:
    • **Amplitude:** The maximal displacement of a graph or wave from the x axis
    • **Frequency:** The number of complete cycles in a given time period
    • **Wavelength:** The length from a point on one wave...
    (etc.)

  ▶ [1.1.2. DIFFERENTIATION AND INTEGRATION] (5)  ← clickable link, collapsed by default
    ↓ When expanded:
    • **Differentiation:** Differentiating the equation...
    (etc.)
```

**Key requirements:**
- Each heading name should be a **clickable link** that jumps to that section in the source note
- Each heading group should be **individually collapsible** (details/summary tags)
- Content should display as a clean bulleted list
- Sorted by page name, then heading name

## Current Code (Lines 892-989 in syllabus)

```markdown
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Basic Physical and Mathematical Principles";
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
>                 // Remove the link syntax for cleaner display
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>
>                 // Create link to the heading
>                 let locationLink = heading
>                     ? dv.fileLink(page.file.path, false, heading)
>                     : page.file.link;
>
>                 results.push({
>                     content: cleanLine.trim(),
>                     location: locationLink,
>                     pageName: page.file.name,
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
>     dv.paragraph("---");
>
>     // Create collapsible section for each heading
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>
>         // Add link and count
>         const linkSpan = summary.createEl("span");
>         linkSpan.appendChild(group.headingLink);
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>
>         const contentDiv = details.createEl("div", {cls: "dataview-result-list"});
>         const ul = contentDiv.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.textContent = item.content;
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
```

## Technical Environment

- **Platform:** Obsidian with Dataview plugin
- **Vault path:** `/Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/`
- **DataviewJS version:** Latest (assumed)
- **Key API objects available:**
  - `dv` - Dataview API
  - `dv.el()` - Create DOM elements
  - `dv.fileLink()` - Create Obsidian links
  - `dv.paragraph()` - Render paragraphs
  - `app.vault` - Obsidian Vault API

## The Problem

In the current code (lines 969-985), two issues:

1. **`group.headingLink` is not rendering as a clickable link** when appended to the summary element. It's created with `dv.fileLink()` but appears as plain text.

2. **The `<details>` elements are not functioning** as collapsible sections. They should have clickable arrows that expand/collapse the content list.

## What I've Tried

- Using `summary.innerHTML` with the link (made links clickable but broke collapsing)
- Using `appendChild()` with DOM elements (didn't make links clickable)
- Wrapping links in `<span>` elements
- Using different DOM element types

## Request

Please provide working code that:
1. Makes the heading names **clickable links** that navigate to the source note section
2. Makes each heading group **individually collapsible** with working details/summary tags
3. Keeps the content clean as a bulleted list
4. Maintains the sorting and grouping logic

**Important:** The code must work within DataviewJS in Obsidian's reading view, using only the available Dataview and Obsidian APIs.

## Success Criteria

When I view the syllabus in reading view:
- [ ] I can click on heading names to jump to that section in my notes
- [ ] I can click the arrow next to each heading to expand/collapse just that heading's content
- [ ] The total count is displayed at the top
- [ ] Content is shown as a clean bulleted list
- [ ] Everything is sorted by page name, then heading name

## Additional Notes

- The outer callout (`> [!info]- 📎 Linked Mentions`) works fine and should remain unchanged
- Only the inner grouping/collapsing logic (lines 969-985) needs fixing
- If the solution requires a different approach (e.g., generating markdown instead of DOM manipulation), that's fine too

Please provide the corrected code section that I can directly replace in my syllabus file.
