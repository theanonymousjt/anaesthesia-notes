# Master of Medicine (Anaesthesiology) Part A Syllabus

**Current as of: 23 April 2019**

---

## Overview of Weightages

- **Physiology**: ~32%
- **Pharmacology + Biostatistics**: ~33%
- **Physics and Equipment**: ~15%
- **Anatomy**: ~10%
- **Clinical Medicine**: ~10%

---

## 1. PHYSIOLOGY (~32% of Total Weightage)
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.2. PEDIATRIC]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "1. PHYSIOLOGY (~32% of Total Weightage)";
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

### 1.1 Cardiovascular System
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#4. CARDIOVASCULAR MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY#2. VASCULAR DISEASE PATHOPHYSIOLOGY AND ASSESSMENT]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES#3.1. CARDIOVASCULAR SYSTEM EFFECTS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "1.1 Cardiovascular System";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({
>                     content: cleanLine.trim(),
>                     indentLevel: indentLevel,
>                     pageName: page.file.name,
>                     filePath: page.file.path,
>                     headingName: heading || "No heading",
>                     headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link
>                 });
>             }
>         }
>     }
> }
> if (results.length > 0) {
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
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {
>             cls: "internal-link",
>             href: group.filePath
>         });
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) {
>                 li.style.marginLeft = `${item.indentLevel * 20}px`;
>             }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

#### Functional Anatomy
- Functional anatomy of the heart, including properties of cardiac muscle, nodal and conductive tissue, and its relationship to cardiac function

#### Cardiac Cycle
- Mechanical and electrical changes during the cardiac cycle
- Electrophysiological control

#### Cardiac Output
- Factors that influence cardiac output and its control
- Application of this knowledge to clinical practice
- Electrophysiological control of the heart

#### Cardiac and Vascular Compliance
- Concept of cardiac and vascular compliance

#### Circulation: Overall Control
- Distribution and regulation of circulation overall

#### Circulation: Regional Control
- Distribution, arrangements and regulation of regional circulation
- Coronary, muscle (skeletal), skin
- Other organs covered in specific physiology topics

#### Myocardial Oxygen Balance
- Myocardial oxygen balance

#### Embolism
- Physiology of embolism, ischaemia and infarction

#### Capillary/Lymphatic Circulation
- Capillary circulation
- Lymphatic circulation
- Fluid exchange in tissues

#### Blood Volume Control
- Control of blood volume in normal and abnormal conditions

#### CVS Responses to Changes
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.3. GERIATRIC#3.3. CARDIOVASCULAR AGING]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#1.1. DEFINITION OF OBESITY]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#1.3. BODY FAT DISTRIBUTION]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#3.4. CARDIOVASCULAR AND HEMATOLOGIC SYSTEMS]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#3.5. GASTROINTESTINAL SYSTEM]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "CVS Responses to Changes";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

Cardiovascular responses to physiological and common pathological changes:
- Extremes of age
- Exercise
- Obesity
- Altitude changes
- Artificial ventilation
- Blood loss and shock
- Fluid loading and cardiac failure

---

### 1.2 Respiratory System
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#3. PULMONARY MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES#3.2. RESPIRATORY SYSTEM EFFECTS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "1.2 Respiratory System";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

#### Structure/Function
- Structure and function of the respiratory system
- Humidification and heat exchange

#### Lung Volumes and Capacities
- Lung volumes and capacities
- Application of this knowledge to normal and diseased respiratory states
- Dead space: anatomical and physiological

#### Mechanics of Breathing
- Mechanics of breathing: pressure, flow, work, compliance, muscles, etc.
- Control of ventilation and changes in ventilation in abnormal physiological and common pathological conditions
- Respiratory reflexes

#### Alveolar Ventilation
- Alveolar ventilation

#### Pulmonary Circulation
- Pulmonary circulation
- Pulmonary interstitial space and lymphatic function
- Their relevance in clinical practice

#### V/Q Matching
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "V/Q Matching";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
- Normal and abnormal matching of ventilation and perfusion
- Mechanisms causing ventilation-perfusion inequality
- Effects of posture, respiratory and circulatory changes
- Clinical significance

#### O2/CO2 Exchange and Transport
- Principles involved in transport of oxygen and carbon dioxide in blood
- Applications in clinical practice
- Blood-tissue gas exchange
- O2 cascade

#### Changes with Physiology/Pathophysiology
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.3. GERIATRIC#3.4. PULMONARY AGING]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#3.1. RESPIRATORY SYSTEM]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Changes with Physiology/Pathophysiology";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
Respiration responses to conditions:
- Extremes of age
- Exercise
- Obesity
- Altitude changes: high and low barometric pressures, short and long term adaptation
- Changes in posture (including under anaesthesia)
- Common pathological conditions affecting ventilation and gaseous exchange

#### Causes/Effects of Hypoxia and Ventilation Disorders
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#3.2. OBSTRUCTIVE SLEEP APNEA (OSA)]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#3.3. OBESITY HYPOVENTILATION SYNDROME (OHS)]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Causes/Effects of Hypoxia and Ventilation Disorders";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
Causes and effects of:
- Hypoxia and asphyxia
- Hypoventilation and hyperventilation

#### Respiratory Therapy
- Respiratory inadequacy and failure; principles of therapy
- Artificial ventilation: including common modes of ventilation used in anaesthesia

#### Non-Respiratory Functions
- Non-respiratory functions of lung

---

### 1.3 Renal, Cellular, Body Fluids and Electrolytes, Acid Base
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY#1. OCULAR ANATOMY AND PHYSIOLOGY]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#7. RENAL AND FLUID MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES#3.3. REGIONAL PERFUSION EFFECTS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "1.3 Renal, Cellular, Body Fluids and Electrolytes, Acid Base";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

#### Renal System

**Functional Anatomy/Perfusion**
- Functional anatomy of the kidneys
- Physiology, peculiar features and regulation of renal blood flow

**Glomerular Filtration/Tubular Function**
- Glomerular filtration and tubular function
- Counter-current mechanisms in the kidney
- Regulation of renal function

**Assessment of Function**
- Measurement of glomerular filtration rate and renal blood flow
- Physiological effects and clinical assessment of renal dysfunction

**Control of Acid-Base, Osmolality, Electrolytes**
- Maintenance of acid-base, fluid osmolality and electrolyte balance
- Role of the kidney in handling glucose, nitrogenous products and drugs

**Response to Changes**
- Renal responses to hypovolaemia, hypotension, surgical stress and anaesthesia

**Endocrine Functions**
- Endocrine functions of the kidney

---

#### Body Fluids and Electrolytes

**Body Water Compartments**
- Body water: distribution, movement and regulation
- Electrolyte composition of body fluids: distribution and regulation

**Electrolytes Function/Regulation**
- Function, regulation and physiological importance of:
  - Sodium
  - Potassium
  - Magnesium
  - Calcium
  - Phosphate ions

**Lymph**
- Composition and functions of lymph

**Determinants of Fluid/Electrolyte Movement**
- Osmotic pressure, oncotic pressure and reflection coefficients
- Measurement of osmolality and regulation of osmolality

**Disturbances/Evaluation/Therapy**
- Disturbances of body fluids and electrolytes in pathological conditions:
  - Dehydration
  - Over-hydration
  - Oedema
  - Electrolyte changes
- Evaluation and principles of therapy

---

#### Acid Base Physiology

**Acid-Base Balance**
- Chemistry and physiology of acid-base balance in the body
- Application of this knowledge to clinical situations
- Henderson-Hasselbalch equation and its application

**Regulation**
- Chemistry of buffer mechanisms and their roles in the body
- Regulation of acid-base balance by the respiratory and renal system

**Changes in Disordered States**
- Evaluation (including interpretation of arterial blood gases and electrolyte findings)
- Principles of therapy

---

#### Cellular Physiology

**Components of Cell/Function**
- Structure and functions of a cell and cellular components:
  - Mitochondria
  - Endoplasmic reticulum
  - Other organelles
- Sources of energy available to cells through metabolic processes

**Cell Membrane**
- Cell membrane and its properties
- Mechanisms of transport across cell membranes:
  - Diffusion
  - Facilitated diffusion
  - Primary active transport
  - Secondary active transport

**Intracellular/Extracellular Fluid and Electrolytes**
- Composition of intracellular fluid and its regulation
- Role of the sodium-potassium pump
- Membrane potentials and the Gibbs-Donnan Effect

**Receptors, G-proteins, Secondary Messengers**
- Role of receptors, G-proteins and secondary messengers

---

### 1.4 Nervous System, Musculoskeletal
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY#1. OCULAR ANATOMY AND PHYSIOLOGY]], [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY#3. OCULOCARDIAC REFLEX]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#5. NEUROLOGIC MANAGEMENT]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "1.4 Nervous System, Musculoskeletal";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

#### Neurophysiology
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#2. NEUROANATOMY]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#7. NEUROPHYSIOLOGY]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#8. BRAIN METABOLIC REQUIREMENTS]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#9. CEREBRAL BLOOD FLOW REGULATION]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#11. ANESTHETIC EFFECTS ON CEREBRAL PHYSIOLOGY]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#12. SPINAL CORD PHYSIOLOGY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Neurophysiology";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**Electrophysiology**
- Electrophysiology of neural tissue including:
  - Resting membrane potential
  - Conduction of nervous impulses
  - Action potentials
  - Excitatory and inhibitory post-synaptic potentials
  - Synaptic function

**Integration CNS Activity**
- Integration of central nervous system activity via:
  - Cerebellum
  - Hypothalamus
  - Limbic system

**Cerebrospinal Fluid**
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#5. CEREBROSPINAL FLUID SYSTEM]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Neurophysiology";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
- Physiology of cerebrospinal fluid
- Formation, drainage, regulation and function

**Cerebral/Spinal Cord Circulation**
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#4. CEREBROVASCULAR ANATOMY]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#6. SPINAL CORD ANATOMY]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#9. CEREBRAL BLOOD FLOW REGULATION]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#10. REGIONAL BLOOD FLOW CONTROL]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Neurophysiology";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
- Cerebral blood flow, cerebral perfusion pressure and cerebral metabolism in:
  - Normal patient
  - Patients under anaesthesia (effects of anaesthesia)
  - Patients with intracranial pathology

**Blood Brain Barrier**
- Structure, role and function of blood brain barrier

**Intra-Cranial/Intra-Ocular Pressure**
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#14. INTRACRANIAL PRESSURE]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#15. CEREBRAL EDEMA TYPES]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#16. ADDITIONAL CAUSES OF INTRACRANIAL HYPERTENSION]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Neurophysiology";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
- Intra-cranial and intra-ocular pressure: normal and regulation

**Neurotransmitters**
- Major neurotransmitters and their physiological role

**Principles of Reflex Activity**
- Principles of reflex activity

**Physiology of Pain**
<!-- covered-by: [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.3. ACUTE PAIN]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.4. CHRONIC PAIN]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Neurophysiology";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
- Definition of pain
- Mechanisms of nociception
- Spinal cord modulation
- Role of chemical mediators
- Central processing of the noxious impulse
- Inhibitory pathways and opioid receptors

**Sleep Physiology**
- Physiology of sleep
- Stages, basis and changes of electroencephalography with sleep, sedation and anaesthesia

---

#### Muscle Physiology

**Physiology/Functional Anatomy**
- Physiology and functional anatomy of:
  - Skeletal muscle
  - Smooth muscle
  - Cardiac muscle

**Microanatomy**
- Muscle spindle and Golgi organ
- Concept of motor units
- Types of skeletal muscle fibres (fast or slow)

**Neuromuscular Junction**
- The neuromuscular junction and its receptors
- Mechanism of excitation-contraction coupling
- Monosynaptic stretch reflex

**Single Twitch/Tetanus/Treppe Effect**
- Single twitch, tetanus and Treppe effect, and their physiological basis
- Relationship between muscle length and tension

---

### 1.5 Liver, Nutrition, Gastrointestinal

#### Liver Physiology
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#3.5. GASTROINTESTINAL SYSTEM]], [[8. CLINICAL ANAESTHESIA/8.4 LIVER SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Liver Physiology";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**Circulation**
- Anatomical and physiological considerations in hepatic blood flow
- Changes that occur with anaesthesia
- Portal circulation and its significance

**Storage, Synthetic, Metabolic and Excretory Functions**
- Storage, synthetic, metabolic and excretory functions of the liver
- Physiological consequences of hepatic disease
- Handling of bilirubin in the body

**Assessment of Function**
- Clinical laboratory assessment of liver function and hepatic failure

**Reticulo-Endothelial/Protective Functions**
- Reticulo-endothelial functions of the liver
- Protective function of the liver between the gut and the body

---

#### Nutrition and Metabolism

**Energy Balance**
- Energy balance
- Basal metabolic rate and its measurement
- Factors that influence metabolic rate

**Macro/Micro Nutrients**
- Uptake, synthesis and metabolism of carbohydrates, fat and protein
- Essential nutritional requirements
- Role of vitamins and trace elements

**Parenteral and Enteral Nutrition**
- Principles of parenteral nutrition and enteral nutrition

**Enzyme Systems**
- Common enzyme systems, evaluation of disturbances
- Consequences of anaerobic metabolism

**Consequences of Starvation/Sepsis/Burns/Trauma**
- Physiological consequences of starvation
- Metabolic consequences of sepsis, burns and trauma

---

#### Gastrointestinal Physiology

**Functions: Secretory/Digestion/Absorption**
- Secretory function:
  - Salivary glands
  - Stomach
  - Small intestine
  - Pancreas (external secretion)
  - Bile: volumes and composition, regulation
- Digestion and absorption of carbohydrate, fat and protein

**Oesophageal Motility**
- Swallowing
- Vomiting
- Factors preventing reflux of gastric contents into the oesophagus

**Gastric Motility**
- Control of gastric motility and emptying

**Splanchnic Circulation**
- Splanchnic circulation and its regulation

**GI Fluid Loss**
- Gastro-intestinal fluid losses: effects and principles of treatment

---

### 1.6 Maternal, Fetal and Neonatal

#### Maternal Physiology

**CVS/Resp Changes**
- Cardiovascular and respiratory changes during pregnancy and parturition
- Their causes and consequences
- Consequences of the supine posture during pregnancy

**Placenta: Anatomy/Physiology/Function**
Anatomy, physiology and function of the placenta, including:
- Placental gaseous and acid-base exchange
- Placental blood flow
- Barrier function

**Gaseous Transfer**
- Transfer of gases between mother and fetus
- Double Bohr and Haldane effects

**Non-Cardioresp Changes**
- Endocrine changes during pregnancy and their consequences
- Haematological changes with pregnancy

---

#### Fetal Neonatal Physiology

**CVS and Resp Changes**
- Fetal circulation during development
- Circulatory and respiratory changes that occur at birth

**Pulmonary Function of Neonate**
- Pulmonary function
- Airway size, gas transfer, respiratory work, lung volume and role of surfactant

**Fluid, Electrolytes, Kidney Function**
- Body fluids and electrolyte composition
- Control of body fluids in the neonate
- How the control and composition differ from the adult

**Blood Volume and Haemoglobin**
- Blood volume and haemoglobin changes

**Temperature Regulation**
- Temperature regulation in the neonate
- How this differs from the adult
- Physical and physiological reasons for these differences

**Other Organ Functions**
- Physiological differences in organ function (including liver) between neonate and adult

---

### 1.7 Endocrine and Thermoregulation

#### Endocrine
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#3.6. RENAL AND ENDOCRINE SYSTEMS]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#3.7. METABOLIC SYNDROME]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES#4.4. TEMPERATURE AND FLUID MANAGEMENT]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Endocrine";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**Secretions**
Secretions of:
- Pituitary
- Thyroid
- Parathyroid
- Adrenals
- Pancreas
- Kidney
- Heart

**Formation/Control/Consequence**
- Neural control of endocrine secretions
- Formation and control
- Metabolism and excretion
- Over-secretion and under-secretion
- Evaluation of function

**Prostaglandins and Other Autocoids**
- Prostaglandins and other autocoids

---

#### Temperature and Thermoregulation

**Mechanisms of Heat Production/Loss**
- Mechanisms for heat transfer between the body and its environment
- Mechanisms by which heat is produced by the body
- Mechanisms by which heat is lost and gained by the body

**Managing Body Temperature**
- Processes used for conserving and generating heat under lowered environmental temperature
- Effects of anaesthesia on these processes
- Processes used for losing heat and increasing heat loss under raised environmental temperature
- Effects of anaesthesia on these processes

**Thermoneutral Zone**
- Thermoneutral zone
- Energy requirements for maintaining normal body temperature

**Hypothermia: Effects**
- Effects of hypothermia

---

### 1.8 Haematology, Immunology
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY#2. VASCULAR DISEASE PATHOPHYSIOLOGY AND ASSESSMENT]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "1.8 Haematology, Immunology";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

#### Haematology

**Blood Constituents**
- Production, function and breakdown of blood constituents:
  - Red blood cells
  - Haemoglobin
  - Plasma proteins
- Constituents and functions of plasma

**Coagulation and Fibrinolysis**
- Platelets and their role in coagulation
- Intrinsic and extrinsic coagulation pathways
- Mechanisms of preventing thrombosis
- Fibrinolysis and its regulation

**Assessment of Function**
- Methods for assessing coagulation, platelet function and fibrinolysis

**Anaemia: Consequences**
- Consequences of acute and chronic anaemia

**Transfusion and Issues**
- Origin and importance of blood groups and cross-matching
- Constituents of blood products, their source, role and risks
- Changes during blood storage
- Problems of massive blood transfusion and their management

**Abnormal Haemoglobins**
- Abnormal haemoglobins and their clinical significance

---

#### Immunology

**Normal Immune Function**
- Basic immunology including non-specific resistance mechanisms and specific immunity
- Auto-immunity

**Tissue Typing/Transplant and Rejection**
- Principles of tissue typing
- Principles of tissue/organ transplantation
- Mechanisms of rejection of allogeneic organs

**Hypersensitivity Reactions**
- Mechanism and pathophysiological effects of hypersensitivity
- Significance of route of drug administration with regards to drug reactions
- Principles of management strategies for anaphylactic/anaphylactoid reactions

**Altered Immune Function**
- Effects of anaesthesia, surgery and critical illness on immune function
- Implications of depression of immune status

**Assessment of Function**
- Assessment of immune reaction

---

## 2. PHARMACOLOGY + BIOSTATISTICS (~33%)
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.2. PEDIATRIC]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "2. PHARMACOLOGY + BIOSTATISTICS (~33%)";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

### 2.1 General Pharmacology
<!-- covered-by: [[3. PHARMACOLOGY/3.1. BASIC PHARMACOLOGY]], [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY#4. OPHTHALMIC DRUGS AND SYSTEMIC EFFECTS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "2.1 General Pharmacology";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

#### Pharmacodynamics

**Basic Sciences**
- Knowledge of the biochemistry, physical chemistry of cellular membranes and intracellular elements for understanding drug actions and metabolism

**Modes of Drug Action**
- Modes of drug action:
  - Receptor theory
  - Enzyme interactions
  - Physico-chemical interactions

**Receptor Theory (in detail)**
Detailed knowledge including:
- Ionic fluxes
- Second messenger
- G proteins
- Nucleic acid synthesis
- Regulation of receptor number and activity
- Evidence for presence of receptors

**Dose-Effect Relationships**
Detailed knowledge with reference to:
- Graded and quantal response
- Therapeutic index
- Potency and efficacy
- Competitive and non-competitive antagonists
- Partial agonists
- Mixed agonist-antagonists
- Inverse agonists

**Law of Mass Action, Affinity, Dissociation Constants**
- Law of Mass Action
- Affinity
- Dissociation constants

**Mechanism of Action of GA Agents**
- Theories of mechanism of action of general anaesthetic agents

---

#### Pharmacokinetics
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#4.1. PHARMACOKINETIC PRINCIPLES]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Pharmacokinetics";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**Single/Multiple Compartment Models**
- Concept of single and multiple compartment models

**Key Concepts**
Concept of and mathematics required to apply:
- Half-life
- Clearance
- Zero and first order kinetics
- Volume of distribution
- Bio-availability
- Area under the plasma concentration time curve
- Extraction ratio
- Loading and maintenance dosage regimens

**Absorption of Drug**
- Absorption of drug at clinically utilized sites of administration
- Factors that will influence it

**Distribution of Drugs**
- Factors influencing the distribution of drugs:
  - Protein binding
  - Lipid solubility
  - pH, pKa
- Variation in different physiological and pathological conditions

**IV/Infusion Kinetics**
- Concepts related to intravenous and infusion kinetics
- Context sensitive half time
- Effect-site and effect-site equilibration time
- Clinical applications

**Epidural/Subarachnoid Space Kinetics**
- Pharmacokinetics of drugs administered in the epidural and subarachnoid space

**Drug Clearance**
- Mechanisms of drug clearance
- Variation in different physiological and pathological conditions

**Hepatic and Non-Hepatic Metabolism**
- Hepatic and non-hepatic metabolism of drugs
- Phase 1 and Phase 2 reactions
- Hepatic extraction ratio and its significance
- First pass effect
- Enzyme induction and inhibition

**Clinical Drug Monitoring**
- Clinical drug monitoring

---

#### Variability in Drug Actions

**Tolerance, Tachyphylaxis, Dependence**
- Tolerance
- Tachyphylaxis
- Dependence
- Addiction
- Idiosyncrasy
- Mechanisms of tolerance

**Alterations of Response**
Alterations to drug response due to:
- Different physiological conditions (e.g., neonates, elderly, pregnancy)
- Different pathological conditions (e.g., cardiac, respiratory, renal and hepatic disease)

**Adverse Drug Reaction**
- Adverse drug effects
- Anaphylaxis and anaphylactoid reaction

**Drug Interactions**
- Mechanisms of drug interaction

**Drug Abuse**
- Pathophysiology of drug abuse with particular reference to the perioperative period
- Potential drug interactions
- Specific drugs: alcohol, nicotine, benzodiazepines, opioids, cannabinoids, cocaine, amphetamines, ecstasy

**Pharmacogenetics**
Pharmacogenetic disorders:
- Malignant hyperpyrexia (in detail including treatment)
- Porphyria
- Atypical cholinesterase
- Variation of cytochrome function
- Management of malignant hyperthermia with reference to pharmacology of dantrolene

---

#### Pharmaceutical Aspects/Drug Development

**Drug Preparations**
- Shelf-life
- Changes in drug potency during storage
- Methods of preserving shelf-life of drugs
- Drug additives: buffers, anti-oxidants, anti-microbial and solubilizing agents

**Isomerism**
- Isomerism

**Drug Evaluation and Trials**
- Drug evaluation and trials

---

### 2.2 Core Anaesthetic Drugs
<!-- covered-by: [[3. PHARMACOLOGY/3.1. BASIC PHARMACOLOGY]], [[3. PHARMACOLOGY/3.2. MECHANISMS OF ANAESTHESIA AND CONSCIOUSNESS]], [[3. PHARMACOLOGY/3.3. INHALATIONAL AGENTS]], [[3. PHARMACOLOGY/3.4 INTRAVENOUS AGENTS]], [[3. PHARMACOLOGY/3.5. OPIOID ANALGESIA]], [[3. PHARMACOLOGY/3.6. NON OPIOID ANALGESIA]], [[3. PHARMACOLOGY/3.7. NEUROMUSCULAR BLOCKING AGENTS]], [[3. PHARMACOLOGY/3.8. LOCAL ANAESTHETICS]], [[3. PHARMACOLOGY/3.9. ADRENERGIC AGENTS]], [[3. PHARMACOLOGY/3.10. HYPOTENSIVE AGENTS]], [[3. PHARMACOLOGY/3.11. ANAESTHESIA ADJUNCTS]], [[3. PHARMACOLOGY/3.12. COMMONLY ENCOUNTERED DRUGS]], [[3. PHARMACOLOGY/3.13. LESS COMMONLY ENCOUNTERED DRUGS]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.2. PERIPHERAL NERVE BLOCKS]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.3. ACUTE PAIN]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.4. CHRONIC PAIN]], [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES#4.2. ANESTHESIA MAINTENANCE STRATEGIES]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "2.2 Core Anaesthetic Drugs";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**For each drug class, detailed knowledge when relevant of:**

**Pharmaceutical Characteristics:**
- Chemical nature/source
- Preparation, purity and stability
- Dosage, strengths of preparation
- Inhaled concentrations

**Pharmacokinetic Characteristics:**
- Routes of administration
- Absorption, distribution, metabolism and excretion

**Pharmacodynamic Characteristics:**
- Site/s and mechanisms of action
- Structure activity relationships
- Variation in drug effects
- Monitoring of drug effects
- Effects on other systems
- Unwanted, adverse effects and toxic effects

**Clinical Considerations:**
- Considerations in pregnancy and lactation
- Elderly, neonatal or paediatric patients
- Indications and contraindications for use

**Drug Classes:**
- Inhalational agents
- Intravenous agents
- Local anaesthetics
- Opioids
- Analgesics: Non-opioids (NSAIDs, Paracetamol)
- Neuromuscular blockers and reversal agents
- Antiemetics
- Adjuvant medications for pain
- Oxygen

---

### 2.3 Drugs for Management of Monitored Parameters/Major Systems of Anaesthetic Interest
<!-- covered-by: [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.3. ACUTE PAIN]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.4. CHRONIC PAIN]], [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY#1. INTRODUCTION TO VASCULAR AND ENDOVASCULAR ANESTHESIA]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "2.3 Drugs for Management of Monitored Parameters/Major Systems of Anaesthetic Interest";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**For each drug class, detailed knowledge when relevant of:**

**Pharmaceutical Characteristics:**
- Preparation, purity and stability
- Dosage, strengths of preparations

**Pharmacokinetic Characteristics:**
- Routes of administration
- Absorption, distribution, metabolism and excretion

**Pharmacodynamic Characteristics:**
- Site/s and mechanisms of action
- Structure activity relationships
- Variation in drug effects
- Monitoring of drug effects
- Effects on other systems
- Unwanted, adverse effects and toxic effects

**Clinical Considerations:**
- Considerations in pregnancy and lactation
- Elderly, neonatal or paediatric patients
- Indications and contraindications for use

**Categories:**

**ANS: Cholinergics and Anti-Cholinergics**
- Drugs that affect the autonomic system
- Cholinergic system and anticholinesterases

**CVS: Contractility, Rate, Rhythm, Vascular Tone**
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#2.4. HEMODYNAMIC MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#2.5. PHARMACOLOGIC SUPPORT]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "2.3 Drugs for Management of Monitored Parameters/Major Systems of Anaesthetic Interest";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
Drugs that affect the cardiovascular system:
- Contractility
- Rate and rhythm
- Vascular tone

**Resp: Bronchial Tone/Pulmonary Vasculature**
Drugs that affect the respiratory system:
- Bronchial tone
- Pulmonary vasculature

**Renal & Volume**
Drugs/fluids that affect renal system and volume status:
- Diuretics
- Blood products
- Fluid replacement

**Haemostasis Function**
- Drugs that affect the coagulation pathway
- Platelet function
- Fibrinolytic pathway

---

### 2.4 Drugs for Management of Conditions of Periop Concern and Poisoning

**Required knowledge includes:**
- General idea of preparations, strength and dosages
- Routes of administration
- Absorption, distribution, metabolism and excretion
- Site/s and mechanism of action
- Variation in drug effects
- Effects on other systems
- Adverse effects
- Indications and contraindications

**Categories:**

**Endocrine**
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#2.6. HORMONE REPLACEMENT THERAPY]], [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#2.8. OTHER MANAGEMENT CONSIDERATIONS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "2.4 Drugs for Management of Conditions of Periop Concern and Poisoning";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
Drugs that affect the endocrine system:
- Hypothalamic-pituitary-adrenal axis and steroids
- Diabetes mellitus
- Thyroid function

**GI Drugs**
Drugs that affect the gastrointestinal system:
- Gastric volume and composition
- Gastrointestinal vasculature

**Genitourinary Drugs**
- Drugs that affect the uterus and prostate

**Psychotherapeutic Drugs**
- Psychotherapeutic drugs

**Anticonvulsants**
- Anticonvulsant drugs including Mg

**Antimicrobials**
- Antimicrobials drugs

**Drugs Affecting Immune System + Cytotoxics**
- Drugs that affect the immune system
- Cytotoxic drugs

**Poisoning: General Management**
- General principles of the management of poisoning
- General knowledge of methods to decrease absorption and enhance drug elimination:
  - Charcoal
  - Emetic agents
  - Gastric lavage
  - Haemodialysis
  - Charcoal haemoperfusion

**Poisoning: Specific Effects/Management**
Physiological effects and management of overdose:
- Paracetamol
- Aspirin
- Tricyclic anti-depressants
- Sedatives
- Cyanide
- Digoxin
- Organophosphates

---

### 2.5 Biostatistics/Clinical Trials
<!-- covered-by: [[1. BASIC SCIENCES/1.2. STATISTICS#foundations-of-biostatistics]], [[1. BASIC SCIENCES/1.2. STATISTICS#research-design-and-methodology]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.3. ACUTE PAIN]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "2.5 Biostatistics/Clinical Trials";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

#### Design of Clinical Trial
<!-- covered-by: [[1. BASIC SCIENCES/1.2. STATISTICS#types-of-research-design]], [[1. BASIC SCIENCES/1.2. STATISTICS#management-of-bias]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Design of Clinical Trial";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

Considerations of a good study design including:
- Study design
- Types of errors and techniques to minimize errors
- Sampling
- Bias and confounders
- Optimal power of the study

#### Statistical Analysis
<!-- covered-by: [[1. BASIC SCIENCES/1.2. STATISTICS#data-structure-and-types]], [[1. BASIC SCIENCES/1.2. STATISTICS#descriptive-statistics]], [[1. BASIC SCIENCES/1.2. STATISTICS#hypothesis-testing-and-inferential-statistics]], [[1. BASIC SCIENCES/1.2. STATISTICS#statistical-tests-and-applications]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Statistical Analysis";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

- Types of data
- Descriptive statistics to measure central tendency and distribution of data
- Parametric and non-parametric tests in statistical inference
- Linear regression analysis and correlation
- Sensitivity, specificity, positive and negative predictive value of diagnostic tests
- Risks and estimation of risk
- Calculation of power of a study

#### Evidence Based Medicine
<!-- covered-by: [[1. BASIC SCIENCES/1.2. STATISTICS#advanced-statistical-methods]], [[1. BASIC SCIENCES/1.2. STATISTICS#critical-appraisal-and-interpretation]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Evidence Based Medicine";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

- Levels of evidence
- Systematic review
- Meta-analysis

---

## 3. PHYSICS AND EQUIPMENT (~15%)

### 3.1 Physics
<!-- covered-by: [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.2. PERIPHERAL NERVE BLOCKS]], [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY#7. LASER THERAPY PRINCIPLES]], [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY#4. ENDOVASCULAR INTERVENTIONS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "3.1 Physics";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

#### Basic Physical and Mathematical Principles
<!-- covered-by: [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#mathematical-definitions-and-relationships]], [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#newtons-laws-of-motion]] -->

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

**Mathematical Concepts:**
- Exponential functions
- Integration
- Differentiation
- Time constants and half life

**Electrical Concepts:**
- Current
- Potential difference
- Resistance
- Impedance
- Inductance
- Capacitance as they relate to biomedical apparatus

**SI System:**
<!-- covered-by: [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#si-units-and-measurement-systems]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Basic Physical and Mathematical Principles";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
- SI system of units
- Conversion between different units (e.g., of pressure measurement)

#### Behavior of Gases, Liquids and Vapors
<!-- covered-by: [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#gas-laws-and-behavior]], [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#critical-temperature-and-pressure]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Behavior of Gases, Liquids and Vapors";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

- Laws governing the behavior of gases, liquids and vapors
- In relation to temperature, pressure and volume

#### Physics of Flow
<!-- covered-by: [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#flow-dynamics]], [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#bernoulli-and-venturi-principles]], [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#coanda-effect]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Physics of Flow";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

- Principles of flow and velocity of gases and liquids
- Relationship to viscosity and density
- Characteristics of laminar and turbulent flow
- Application of Bernoulli's principle

#### Diffusion/Hydrostatic Pressure and Osmotic Forces
<!-- covered-by: [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#pressure-concepts-and-measurement]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Diffusion/Hydrostatic Pressure and Osmotic Forces";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

- Laws of diffusion: O2, CO2, drugs, electrolytes
- Concept of hydrostatic pressure and osmotic forces

#### Heat and Humidity

- Physical principles of heat transfer
- Relative and absolute humidity

#### Ultrasound

- Basic physics of ultrasound and the Doppler principle

---

### 3.2 Principle of Measurement
<!-- covered-by: [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#pressure-measurement-devices]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "3.2 Principle of Measurement";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

- Pressure measurement of gases and liquids
- Principles of measurement employed by apparatus in clinical use
- Including transducers
- Calibration

---

### 3.3 Clinical Monitoring
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#8. LABORATORY ASSESSMENT]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#9. COAGULATION MONITORING]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#10. ULTRASOUND IN TRAUMA]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#19. NEUROMONITORING]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#20. CENTRAL NERVOUS SYSTEM FUNCTION MONITORING]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#23. CEREBRAL PERFUSION MONITORING]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#24. INTRACRANIAL PRESSURE MONITORING]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#25. CEREBRAL OXYGENATION AND METABOLISM MONITORS]], [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY#3. CEREBROVASCULAR AND CAROTID PROCEDURES]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES#4.1. MONITORING REQUIREMENTS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "3.3 Clinical Monitoring";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**Includes everything required for monitoring at bedside, OT or ICU:**
- Principles
- Calibration
- Sources of errors
- Limitations
- Interpretation of readings or results

#### Cardiovascular System
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Cardiovascular System";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**Cardiac Function: Electrical**
- Electrocardiogram (ECG)
- Calibration, sources of errors and limitations

**Cardiac Function: Mechanical**
- Heart tones
- Echocardiography
- Doppler
- Cardiac output

**Vascular Pressure: Non-invasive**
- Non-invasive blood pressure measurement

**Vascular Pressure: Invasive**
Including:
- Invasive arterial blood pressure
- Central venous pressure
- Pulmonary arterial pressure
- Pulmonary artery occlusion pressure
- Left atrial pressure
- Left ventricular end-diastolic pressure (LVEDP)

**Vascular System: Volume and Resistance**
- Blood volume and SVR

**Organ Blood Flow**
- Organ blood flow measurement

---

#### Respiratory System
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Respiratory System";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**Evaluation of Respiratory Function**
- Lung volumes
- Gas flow
- Ventilation
- Blood flow
- Diffusion
- Compliance
- Resistance
- Gas transport
- Gas concentrations and pressures in ventilating gas mixtures and body fluids

**Measurements of Ventilation**
- Respirometers
- Inspiratory force
- Spirometry
- Flow-volume loops

**Measurements of Gases of Clinical Significance**
Including O2, CO2, nitrogen, anesthetic gases and vapors using:
- Ultraviolet or infra-red absorption
- Paramagnetic analysis
- Gas chromatography
- Mass spectrometry
- Raman scattering

**Capnography**
- Principles of capnography
- Calibration, sources of errors and limitations

**Measurement of Flow**
- Measurements of gas flow
- Flowmeters and rotameter

**Oxygenation**
- Measurements of oxygenation
- Pulse oximetry: principles, calibration, sources of errors and limitations

**Blood Gases**
- Measurements of blood gases
- Electrodes for pH, PO2, PCO2
- Calibration, temperature corrections, errors

---

#### Nervous System

**Brain/Spinal Cord:**

**Consciousness**
- Electroencephalogram (EEG) - raw and processed
- Principles and available anesthesia monitors (including Bispectral, others)
- Evoked potentials

**Other Neurological Functions**
- Motor (MEP) and sensory (SSEP)

**Intracranial Pressure**
- Intracranial pressure measurement

**Blood Flow and Oxygenation**
- Measurement of brain tissue oxygen saturation (including near infrared spectroscopy/cerebral oximetry)
- Measurement of regional flow:
  - Transcranial doppler
  - Jugular venous oxygen saturation

**Neuromuscular Function**
- Depth of paralysis
- Localisation for regional anaesthesia

---

#### Temperature and Humidity

**Principles of Temperature Sensing Devices**
- Principles of temperature sensing devices

**Measurement: Temperature and Humidity**
- Various sites of measurement
- Calibration
- Interpretation
- Sources of error

---

#### Miscellaneous Monitoring Devices

- Miscellaneous monitoring devices

#### Minimum Monitoring Standards

- Minimum monitoring standards

---

### 3.4 Equipment and Safety
<!-- covered-by: [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#electrical-power-systems]], [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#electrical-safety-in-healthcare]], [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY#7. LASER THERAPY PRINCIPLES]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "3.4 Equipment and Safety";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

#### Equipment

**Supply of Medical Gases**
- The supply of medical gases (bulk supply and cylinder)

**Oxygen Therapy**
- Oxygen supplementation and oxygen therapy

**Airway Devices for Positive Ventilation**
- Devices to facilitate manual and mechanical ventilation:
  - Masks
  - Airways
  - Supraglottic devices
  - Endotracheal tubes

**Devices to Facilitate Placement of Airway**
- Devices to facilitate endotracheal intubation and tube change adjuncts:
  - Bougies
  - Jet stylets
  - Soft and rigid tube change devices

**Suction**
- Set-up and operation of medical suction

**Breathing Circuits and Components**
- Circle breathing circuits and Ayre's T-piece and components
- Advantages and hazards of use
- Removal of carbon dioxide in a circle system and associated hazards

**Ventilators**
- Commonly used modes of ventilation available in anaesthetic practice

**Scavenging**
- Scavenging systems

**Vaporisers**
- Vaporisers

**Anaesthesia Machine**
- Components and operation of the anaesthetic machine
- Anaesthesia machine check

**Temperature and Humidity**
- Methods of maintaining and regulating temperature and humidity
- Active warming of patients: safety and hazards

---

#### Safety
<!-- covered-by: [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#electrical-shock-and-safety]], [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#operating-room-fires]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Safety";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**Electrical Safety**
- Microshock and macroshock
- Mechanisms for preventing these
- Safety features of the operating room and equipment used in the operating environment
- Surgical diathermy, its safe use and potential hazards

**Fire, Explosions, LASERs**
<!-- covered-by: [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#operating-room-fires]], [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#lasers-in-healthcare]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Safety";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
- Fire and explosions hazards: causes, prevention and management
- Surgical lasers, their safe use and potential hazards

**Biohazards**
- Anaesthetic gas pollution
- Infectious diseases: airborne and contact
- Universal precaution
- Needlestick injuries

**Radiological Investigations**
- Principles of radiological investigations (X-rays, CT scan and MRIs)
- Their safe use and potential hazards

---

#### Patient Safety Considerations

**Positioning and Pressure Effects**
- Safe positioning of patient on the operating table
- Potential hazards:
  - Nerve injury
  - Pressure points
  - Ophthalmic injuries
- Risks of tourniquet usage

**Drug Error**
- Considerations for prevention of drug errors:
  - Selection
  - Checks
  - Preparation
  - Labelling
  - Administration

**Blood Product Administration**
- Consideration for preventing error
- Management of reactions

---

## 4. ANATOMY (~10%)

### 4.1 Head and Neck (Including Airway)
<!-- covered-by: [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.2. PERIPHERAL NERVE BLOCKS]], [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY#1. OCULAR ANATOMY AND PHYSIOLOGY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "4.1 Head and Neck (Including Airway)";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

#### Face, Eye, External Ear

**In particular Eye:**
- Contents of the orbit
- Determinants of ocular perfusion and intra-ocular pressure
- Innervation and eye reflexes (including: oculo-cardiac, oculo-respiratory, oculo-emetic)
- Innervation of the face

#### Nose, Oral Cavity, Pharynx

**Nose:**
- Innervation and blood supply

**Oral Cavity:**
- Structures: floor of mouth, tongue, teeth, hard and soft palate
- Innervation

**Pharynx:**
- Subdivisions
- Innervation

#### Larynx

- Innervation
- Muscles
- Blood supply
- Cartilages
- Vocal cords, positions with paralysis
- Differences between infant and adult

#### Trachea

- Structure, innervation and relationships in neck and chest

#### Neck

- Surface anatomy
- Musculoskeletal structure
- Innervation
- Major vessels, nerves and nerve plexuses
- Structural relationships: normal anatomy and current imaging techniques (roentgenograms, ultrasound, CT and MRI)

---

### 4.2 Cardiovascular/Respiratory Anatomy

#### Cardiovascular System

**Heart**
- Normal anatomy of heart and major vessels
- Correlating to current imaging: Radiographic (roentgenograms, CT, MRI)
- Coronary circulation
- Heart conduction system
- Innervation and control systems

**Vessels of Anaesthetic Interest**
Anatomy, anatomical relations and ultrasonic anatomy of vessels in the following regions (relevant to vascular cannulation):
- Neck
- Subclavian and axillary region
- Femoral region
- Cubital fossa
- Wrist
- Foot

**Major Organ Systems**
- Blood supply of other major organs:
  - Kidneys
  - Central nervous system (including spinal cord)
  - Liver
  - Gastrointestinal system

---

#### Respiratory System

**Thorax**
- Thorax: surface anatomy, intra-thoracic structures and relations
- Innervation of the intra-thoracic structures
- Muscles of respiration
- Accessory muscles

**Lung**
- Tracheobronchial tree: divisions
- Lung lobes and segments
- Bronchial and pulmonary circulations
- Microscopic anatomy

---

### 4.3 Neuroanatomy (Central Nervous System and Peripheral Nervous System)
<!-- covered-by: [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.2. PERIPHERAL NERVE BLOCKS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "4.3 Neuroanatomy (Central Nervous System and Peripheral Nervous System)";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**Anatomy and (where relevant) radiological features**

#### Central Nervous System

**Skull and Brain**
- Skull
- Brain:
  - Cerebral cortex
  - Cerebellum
  - Basal ganglia
  - Major nuclei and motor and sensory pathways
  - Brain stem: nuclei and cranial nerves
  - Ventricular system
  - Cerebral circulation; circle of Willis, venous sinuses and drainage
- Meninges: Epidural, subdural and subarachnoid spaces
- Radiological features of common acute neurosurgical conditions

**Spine and Spinal Cord**
<!-- covered-by: [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.1. NEURAXIAL TECHNIQUES]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Central Nervous System";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```
- Variations in vertebral configurations
- Spinal and sacral nerves: dermatomal and myotomal innervation
- Ascending and descending tracts
- Epidural (cervical, thoracic, lumbar, caudal), subdural and subarachnoid space
- Blood supply

---

#### Autonomic Nervous System

**Parasympathetic Nervous System**
- Parasympathetic nervous system

**Sympathetic Nervous System**
- Sympathetic nervous system
- Role in controlling body function

---

#### Peripheral Nervous System

**Anatomy and (where relevant) radiological features (including ultrasound imaging)**

**Note:** Head and neck covered in head and neck section

**Truncal**
- Paravertebral space
- Intercostal space
- Neurovascular plane in the thorax and abdominal wall (e.g., transversus abdominis plane, rectus sheath, ilioinguinal)
- Perineum including penile innervation

**Brachial Plexus**
- Formation, branches, relations and distributions

**Lumbosacral Plexus**
- Formation, branches, relations and distributions

---

## 5. CLINICAL MEDICINE (~10%)

### 5.1 Acute Medicine

**Presentation, investigation and immediate management of common crises encountered in the OT**

#### Cardiovascular Conditions

- Abnormal rhythms:
  - Tachyarrhythmias
  - Bradyarrhythmias
  - Narrow or broad complex
  - Asystole
  - Associated with or without haemodynamic changes according to recognised guidelines including ACLS
- Hypotension or hypertension
- Acute myocardial ischaemia

#### Respiratory Issues

- Difficult airway algorithm
- Dyspnoea or hypoxia
- Hypocapnoea or hypocarbia
- Hypercapnoea or hypercarbia
- Laryngospasm or bronchospasm
- High airway pressures during positive pressure

#### Neurological Issues

- Perioperative confusion, delirium, cognitive dysfunction or failure to awaken

#### Specific Conditions of Interest

- Local anaesthetic toxicity
- Malignant hyperthermia
- Anaphylaxis
- Blood transfusion reaction
- Electrolyte abnormalities (e.g., hyperkalemia and hypokalemia)

---

### 5.2 Perioperative Medicine
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY#5. PREOPERATIVE ASSESSMENT AND PREPARATION]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "5.2 Perioperative Medicine";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_a_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_a_syllabus") && line.includes(targetSection)) {
>                 let heading = null;
>                 for (let j = i - 1; j >= 0; j--) {
>                     if (lines[j].match(/^#{1,6}\s+/)) {
>                         heading = lines[j].replace(/^#{1,6}\s+/, '').trim();
>                         break;
>                     }
>                 }
>                 let indentMatch = line.match(/^(\s*)/);
>                 let indentLevel = indentMatch ? Math.floor(indentMatch[1].length / 2) : 0;
>                 let cleanLine = line.replace(/\[\[.*?\]\]/g, '');
>                 cleanLine = cleanLine.replace(/^\s*[\*\-]\s*/, '');
>                 cleanLine = cleanLine.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
>                 results.push({content: cleanLine.trim(), indentLevel: indentLevel, pageName: page.file.name, filePath: page.file.path, headingName: heading || "No heading", headingLink: heading ? dv.fileLink(page.file.path, false, heading) : page.file.link});
>             }
>         }
>     }
> }
> if (results.length > 0) {
>     let grouped = {};
>     for (let r of results) {
>         let key = `${r.pageName}::${r.headingName}`;
>         if (!grouped[key]) {
>             grouped[key] = {pageName: r.pageName, filePath: r.filePath, headingName: r.headingName, headingLink: r.headingLink, items: []};
>         }
>         grouped[key].items.push(r);
>     }
>     let sortedGroups = Object.values(grouped).sort((a, b) => {
>         let pageCompare = a.pageName.localeCompare(b.pageName);
>         if (pageCompare !== 0) return pageCompare;
>         return a.headingName.localeCompare(b.headingName);
>     });
>     dv.paragraph(`**Total: ${results.length} mentions across ${sortedGroups.length} sections**`);
>     for (let group of sortedGroups) {
>         const details = dv.el("details", "");
>         const summary = details.createEl("summary");
>         const link = summary.createEl("a", {cls: "internal-link", href: group.filePath});
>         link.setAttribute("data-href", `${group.filePath}#${group.headingName}`);
>         link.textContent = group.headingName;
>         summary.appendChild(document.createTextNode(` (${group.items.length})`));
>         const ul = details.createEl("ul");
>         for (let item of group.items) {
>             const li = ul.createEl("li");
>             li.innerHTML = item.content;
>             if (item.indentLevel > 0) { li.style.marginLeft = `${item.indentLevel * 20}px`; }
>         }
>     }
> } else {
>     dv.paragraph("No backlinks found to this section.");
> }
> ```

**Common issues in perioperative medicine:**

#### Generic Preoperative Issues

Common perioperative issues:
- Airway assessment
- Premedication
- URTI

#### Specific Common Conditions

Pathophysiology, assessment and perioperative management of commonly encountered disease conditions:

**CVS Conditions:**
- Ischaemic heart disease
- Valvular heart disease
- Hypertension

**Respiratory Conditions:**
- Asthma
- Chronic obstructive lung disease
- Chronic smoking
- Obstructive sleep apnoea

**Endocrine Conditions:**
- Diabetes
- Hyper and hypothyroidism

**Metabolic Conditions:**
- Morbid obesity

**End Stage Renal Failure**
- End stage renal failure

**Haematological Conditions:**
- Anaemia
- Use of anti-coagulants or antiplatelet medication management

#### Abnormal Findings

Identification and appropriate management of abnormal findings in the perioperative period:

**History and Physical Examinations:**
- Heart murmur
- Thyroid nodule

**Investigations and Management:**
- Abnormal ECG
- CXR
- Blood investigations

#### Postoperative Management

- Criteria for safe extubation
- Management in recovery
- Acute pain management (e.g., management of patient on PCA, epidural)

---

**Document prepared by:**
Dr Tay Kwang Hui  
Master of Medicine (Anaesthesiology) Chief Examiner, 2019  
In consultation with Master of Medicine (Anaesthesiology) Examination Committee