# Master of Medicine (Anaesthesiology) Part B Syllabus

**Current as of 24th July 2019**  
**Prepared by Dr Tay Kwang Hui**

---

## Table of Contents

### Core Topics (C)
- [C1 Airway Oxygenation Ventilation](#c1-airway-oxygenation-ventilation)
- [C2 Sedation and General Anaesthesia](#c2-sedation-and-general-anaesthesia)
- [C3 Local and Regional Anaesthesia](#c3-local-and-regional-anaesthesia)
- [C4 Trauma Resuscitation and Crisis](#c4-trauma-resuscitation-and-crisis)
- [C5 Perioperative Medicine](#c5-perioperative-medicine)
- [C6 Ethics, Medico-Legal Issues, Quality Improvement & Evidence Based Medicine](#c6-ethics-medico-legal-issues-quality-improvement-evidence-based-medicine)

### Specialty Topics (S)
- [S1 Critical Care Medicine](#s1-critical-care-medicine)
- [S2 Pain Medicine](#s2-pain-medicine)
- [S3 Obstetrics Analgesia and Anaesthesia](#s3-obstetrics-analgesia-and-anaesthesia)
- [S4 Paediatrics Anaesthesia](#s4-paediatrics-anaesthesia)
- [S5 Neurosurgery and Neuroradiology](#s5-neurosurgery-and-neuroradiology)
- [S6 Cardiac surgery and interventional cardiology](#s6-cardiac-surgery-and-interventional-cardiology)
- [S7 Thoracic surgery](#s7-thoracic-surgery)
- [S8 General Surgical, Urological, Gynaecological and Endoscopic procedures](#s8-general-surgical-urological-gynaecological-and-endoscopic-procedures)
- [S9 Vascular surgery and interventional radiology](#s9-vascular-surgery-and-interventional-radiology)
- [S10 Orthopaedic Surgery](#s10-orthopaedic-surgery)
- [S11 Plastic, reconstructive and burns surgery](#s11-plastic-reconstructive-and-burns-surgery)
- [S12 Head and neck, ear nose & throat, dental surgery & electro-convulsive therapy](#s12-head-and-neck-ear-nose-throat-dental-surgery-electro-convulsive-therapy)
- [S13 Ophthalmic procedures](#s13-ophthalmic-procedures)
- [S14 Ambulatory Surgery](#s14-ambulatory-surgery)
- [S15 Non-Operating Room Anaesthesia (Remote)](#s15-non-operating-room-anaesthesia-remote)

---

## C1 Airway Oxygenation Ventilation
<!-- covered-by: [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#bernoulli-and-venturi-principles]], [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#coanda-effect]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#4. SPINE SURGERY]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#2. AIRWAY MANAGEMENT IN TRAUMA]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#3. PULMONARY MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#1. AIRWAY EVALUATION AND ASSESSMENT]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#2. PEDIATRIC ENT ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#3. PEDIATRIC AIRWAY EMERGENCIES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#4. SPECIALIZED ENT PROCEDURES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#5. ADULT AND COMPLEX ENT CONDITIONS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "C1 Airway Oxygenation Ventilation";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Airway Management
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#5.2. INTRAOPERATIVE MANAGEMENT]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Airway Management";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

#### Anatomy
- Anatomy of the Airway and Respiratory System (including Applied Anatomy) in adults and paediatrics
- Anatomy of structures within the neck and chest including radiological interpretations of X-ray, CT scan and MRI correlations

#### Airway Assessment
- History and Physical Examination (Bedside tests)
- Clinical indications and limitations of non-radiological airway tests (e.g. flexible nasendoscopy and spirometry with flow-volume loops)
- Patients requiring airway protection: Assessment and Management
- Potential difficult airway: Features, management and guidelines

#### Airway Management Equipment
- Required for basic or routine airway management: including those available on airway trolley, suction, laryngoscopes etc
- Devices to facilitate ventilation including nasal, oral airway, supraglottic airways etc
- Available endotracheal tube types including their characteristics, indications and contraindications, advantages and disadvantages
- Intubation and tube change adjuncts including bougie, tube exchangers, intubating LMAs
- Difficult airway management: Available devices on difficult airway trolley and to assist maintaining ventilation and/or oxygenation

#### Airway Management Guidelines and Techniques
- Routine or Basic Management: including confirmation of appropriate airway (including supraglottic airway device and endotracheal tube) placement
- Difficult airway management: Elective condition including known difficult airway, unstable cervical spine, awake intubation, airway anaesthesia, gaseous induction etc
- Difficult airway management: Emergent or unexpected or suboptimal condition: bleeding or combative patient etc
- Management of a 'can't intubate, can't oxygenate' situation
- Management of oxygenation of the patient with an unexpected difficult airway
- Indication, risks, advantages, disadvantages and technique of 'Front of neck access': Surgical airway or cricothyroidotomy
- Management of the acutely obstructed airway at various location/levels
- Management of shared airway

### Oxygenation
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#5.2. INTRAOPERATIVE MANAGEMENT]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Oxygenation";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Oxygen supply
- Measurement of oxygen concentration: principles and equipment
- Measurement of oxygenation: principles and equipment
- Hypoxaemia and different types of respiratory failure
- Methods of improving oxygenation with or without oxygenation including Continuous Positive Airway Pressure (CPAP) and Positive End-expiratory Pressure (PEEP)
- Preoxygenation: Basis; changes with physiology and pathology; and clinical uses
- Adverse effects of oxygen and oxygen therapy
- ECMO: Principles, Indications and Complications

### Ventilation
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#5.2. INTRAOPERATIVE MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]], [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#2.9. VENTILATORY MANAGEMENT]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Ventilation";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Spontaneous ventilation: at rest, changes in activity and environment
- Spontaneous ventilation: changes with age, pregnancy and obesity
- Indications and effects of positive pressure ventilation and positive end-expiratory pressure
- Classifications of ventilators: flow generation versus pressure generation
- Classifications of ventilation modes: including invasive and non-invasive
- Alternative ventilation modes including jet ventilation, high frequency ventilation
- Ventilation strategies: modifications for physiological changes and pathological conditions
- Measurement and interpretation of ventilation parameters including pressure, volume, flow etc
- Other assessment of ventilation: including arterial blood gas, lung/pleural ultrasound etc
- Nebulizers, Humidifiers, Drug Delivery Systems (Nitric Oxide, Others)

#### Respiratory Failure
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Respiratory Failure";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Pathophysiology, Classification
- Management: Non ventilatory and Ventilatory management
- Other management adjuncts: nitric oxide, steroids, Veno-venous Extracorporeal membrane oxygenation (VV ECMO)

### Extubation
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#5.2. INTRAOPERATIVE MANAGEMENT]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Extubation";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Clinical features that indicate a patient can be extubated safely
- Optimisation of the patient for extubation
- Extubation strategies for 'high risk' extubation situations
- Handover of 'high risk' extubation patient

### Complications involving airway, oxygenation and ventilation
1. Bronchospasm
2. Laryngospasm
3. Post obstructive (negative pressure) pulmonary oedema
4. Aspiration (including risk factors and measures to reduce these)
5. Respiratory Failure
6. Complications at extubation
7. Complications of mechanical ventilation: volutrauma, barotrauma

---

## C2 Sedation and General Anaesthesia
<!-- covered-by: [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#electrosurgery-diathermy]], [[3. PHARMACOLOGY/3.2. MECHANISMS OF ANAESTHESIA AND CONSCIOUSNESS]], [[3. PHARMACOLOGY/3.3. INHALATIONAL AGENTS]], [[3. PHARMACOLOGY/3.4 INTRAVENOUS AGENTS]], [[3. PHARMACOLOGY/3.7. NEUROMUSCULAR BLOCKING AGENTS]], [[3. PHARMACOLOGY/3.8. LOCAL ANAESTHETICS]], [[3. PHARMACOLOGY/3.11. ANAESTHESIA ADJUNCTS]], [[3. PHARMACOLOGY/3.13. LESS COMMONLY ENCOUNTERED DRUGS]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#4. PHARMACOLOGY IN OBESITY]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#5.2. INTRAOPERATIVE MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "C2 Sedation and General Anaesthesia";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Premedication: role and pharmacology
- Agents used to induce and/or maintain state of sedation or anaesthesia: pharmacology and use in different physiological and pathological conditions
- Balanced anaesthesia: concepts and components
- Physiological changes associated with anaesthesia
- Physiological changes in perioperative period including the effects of fasting, surgery, trauma, bleeding etc
- Physiological changes due to positioning or conditions induced for/during surgery (e.g. pneumoperitoneum, hypothermia)
- Monitoring of physiological changes under anaesthesia/during surgery (refer Part A syllabus on Clinical Monitoring)
- Management of physiological changes induced by anaesthesia and surgery
- Equipment for maintenance of state of anaesthesia (refer to Part A syllabus on Equipment)
- Safety considerations in operating theatre (refer to Part A syllabus on Safety)
- Procedures necessary for induction of anaesthesia: Airway, invasive lines for monitoring etc (covered in respective chapters)

### Complications of anaesthesia
1. Trauma; Pressure effects; Burns
2. Awareness
3. Neurologic: Confusion, delirium, cognitive dysfunction, failure to awaken
4. Chronic Environmental Exposure; Fertility, Teratogenicity, Carcinogenicity
5. Temperature: hypothermia
6. Hyperthermia: Malignant and Non-malignant
7. Anaphylaxis: including latex
8. Nausea and vomiting
9. Neuromuscular consequences: residual paralysis, muscle soreness

### Special Techniques/Issues
- Controlled hypotension
- Hypothermia
- High altitudes etc

---

## C3 Local and Regional Anaesthesia
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#5.3. REGIONAL ANAESTHESIA]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.1. NEURAXIAL TECHNIQUES]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.2. PERIPHERAL NERVE BLOCKS]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#3. ANESTHETIC TECHNIQUE SELECTION]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#5. UPPER EXTREMITY SURGERY]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#6. LOWER EXTREMITY SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "C3 Local and Regional Anaesthesia";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### General Considerations for Regional Anaesthesia
- Indications/Contra-indications and Risks vs Benefits
- Consent – Fundamentals, Principles and Considerations specific for RA
- Operating room preparation
- Patient safety issues: e.g. time out check, correct site confirmation, injection site preparation
- Monitoring Standards
- Applied Anatomy (Reference Part A Syllabus on Anatomy)
- Applied Pharmacology (Reference Part A Syllabus on Pharmacology)
- Role of Sedation
- Physiological consequence of RA
- Medications affecting the outcome of regional anaesthesia (bleeding, physiological response, additives)
- Complications associated with regional anaesthesia: Early and Late
- Post-procedural follow-up
- Role of RA in Evidence based Enhanced recovery after surgery (ERAS) Programmes

### Equipment (Reference to Part A Equipment)
- Equipment for delivery of local anaesthetic: e.g. regional block needles
- Equipment for safe and accurate delivery of local anaesthetics

### Specific Techniques
- Single shot versus Continuous catheter techniques
- Central neuraxial blocks
- Major nerve plexus (brachial, lumbosacral, cervical plexus) blocks
- Peripheral nerve blocks of specific nerves: ilioinguinal, penile, wrist, ankle blocks etc
- Intra-venous regional anaesthesia (Bier's block)

---

## C4 Trauma Resuscitation and Crisis Management
<!-- covered-by: [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#electrical-shock-and-safety]], [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#operating-room-fires]], [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#lasers-in-healthcare]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#6. POSTOPERATIVE COMPLICATIONS]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#4. SPINE SURGERY]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#8. SPECIAL CONSIDERATIONS]], [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]], [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY#3. OCULOCARDIAC REFLEX]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#1. INTRODUCTION TO TRAUMA ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#4. CARDIOVASCULAR MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#5. NEUROLOGIC MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#6. RESUSCITATION STRATEGIES]], [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY#5. COMPLICATIONS AND QUALITY IMPROVEMENT]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#3. PEDIATRIC AIRWAY EMERGENCIES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#5. ADULT AND COMPLEX ENT CONDITIONS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "C4 Trauma Resuscitation and Crisis Management";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Resuscitation and Crisis Management
- Generic immediate management
- Generic after crisis management: family, patient (disclosure and follow-up) and team

### Responding to and managing Patients with Specific Acute Physiological Derangements
1. Dyspnoea
2. Hypoxaemia
3. Hypocapnoea/hypocarbia
4. Hypercapnoea/hypercarbia
5. Laryngospasm
6. Bronchospasm
7. Respiratory arrest
8. Tachycardia or Bradycardia
9. Hypotension or Hypertension
10. Cardiac arrest
11. Hyperthermia
12. High airway pressures during positive pressure ventilation
13. Oliguria/anuria
14. Failure to wake from anaesthesia
15. Perioperative confusion, delirium and cognitive dysfunction

### Responding to and Managing Patients with Specific Pathological Presentations
- Tension pneumothorax
- Aspiration of gastric contents
- Severe bronchospasm/Asthma/exacerbation of COPD
- Pulmonary embolism
- Shock: Hypovolaemic
- Shock: Distributive including neurogenic shock
- Shock: Cardiogenic
- Shock: Obstructive
- Cardiac tamponade
- Acute myocardial ischaemia and/or infarction
- Arrhythmias causing haemodynamic compromise
- Acute pulmonary oedema
- Aortic dissection
- Massive haemorrhage, including haemoptysis
- Local anaesthetic toxicity
- Anaphylaxis
- Malignant hyperthermia
- Gas embolism
- Fat embolism
- Coma
- Raised intracranial pressure
- Ischaemic and haemorrhagic stroke
- Prolonged seizures
- Coagulopathy in association with surgery or trauma
- Electrolyte abnormalities: e.g. Hyperkalemia and hypokalemia

### Specific Knowledge and Skills Set by Systems

#### Cardiovascular related conditions
- Placement of invasive lines: Central Venous and Arterial Catheterization
- Pericardiocentesis
- Using Defibrillation and Cardioversion
- Using Cardiac Pacemakers

#### Respiratory related conditions (reference Airway, Oxygenation and Ventilation)
- Establishing artificial airway and ventilatory control
- Managing patients with respiratory failure and life-threatening hypoxaemia
- Acute management of tension pneumothorax
- Acute management of pleural effusion

#### Neurological Conditions
- Assessment and evaluation of altered mental state including neurological examination and scoring of the Glasgow Coma Scale
- Assessment and evaluation of acute neurological deficits

#### Metabolic and electrolyte disturbances
- Hyper/hypokalemia
- Hyper/hyponatremia
- Hyper/hypoglycemia
- Hyper/hypocalcemia
- Hyper/hypophosphataemia
- Hyper/hypomagnesemia
- Severe acid base disturbance including metabolic acidosis
- Thyroid storm
- Addisonian crisis
- Diabetic ketoacidosis
- Hyperosmolar, hyperglycaemic state
- Hypo-osmolar states
- Rhabdomyolysis
- Acute drug intoxication/poisoning, including the following: Alcoholic; Paracetamol; Organophosphate; Opioid; Antidepressants; Benzodiazepines (Reference Part A)

#### Environmental and equipment factors
- An operating room fire
- Electrical power failure in the operating suite
- Failure of pipeline gas supply
- Anaesthesia machine and ventilator malfunction
- Breathing circuit malfunctions such as stuck valves and massive leaks

### Management of Major Trauma, Burns, Mass Casualty and Warfare
- Assessment and management of trauma patient according to Advanced Trauma Life Support (ATLS), or equivalent protocols
- Perform a Primary and Secondary survey
- Adapt to the influence of age, body mass index (BMI), pregnancy, concurrent medical conditions and medications
- Preparation prior to the arrival of the trauma patient to the hospital
- Assessment and management of the patient with severe burn injury
- Preparation and management of equipment and personnel in event of a mass casualty, biological and/or chemical warfare

### Assessment and initial management of injuries associated with the following accidents/trauma
- Electrocution
- Drowning and near drowning
- Severe hypothermia
- Envenomation

### Management of Massive Haemorrhage
- Assessment, classification and management of haemorrhage
- Complications and consequence of haemorrhage
- Coagulopathy associated with trauma and haemorrhage
- Principles of fluid replacement therapy
- Use of blood products, including red blood cell concentrate, plasma, platelets and coagulation factors
- Use of various coagulation adjunctive medications

### Management of Blood and Blood Products Transfusions
- Including preservation and storage of blood and blood products
- Process of transfusion
- Reactions and management of reactions of transfusions

### Transfer of Patients
- Transfer of critically ill patients within institution, between different institutions and between different countries
- Process for arranging a patient transfer
- Challenges, difficulties and limitations of transferring critically ill patients by road or air

---

## C5 Perioperative Medicine
<!-- covered-by: [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#si-units-and-measurement-systems]], [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS#gas-laws-and-behavior]], [[1. BASIC SCIENCES/1.2. STATISTICS#research-design-and-methodology]], [[1. BASIC SCIENCES/1.2. STATISTICS#clinical-applications-of-statistics]], [[6. SPECIAL POPULATIONS/6.3. GERIATRIC#4. PERIOPERATIVE MANAGEMENT OF OLDER PATIENTS]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#2. PREOPERATIVE ASSESSMENT]], [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY#5. PREOPERATIVE ASSESSMENT AND PREPARATION]], [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY#2. VASCULAR DISEASE PATHOPHYSIOLOGY AND ASSESSMENT]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "C5 Perioperative Medicine";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Preoperative Management
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#5. PERIOPERATIVE CONSIDERATIONS]], [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Preoperative Management";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Assessment: Routine medical/surgical history, physical findings and investigations
- Assessment: Routine Airway
- Assessment: Specific to different physiological states and/or acute or chronic disease states (refer below)
- Assessment: Specific to surgical pathology or surgical techniques
- Risk assessment
- Factors improving surgical and long-term outcomes
- Strategies for prehabilitation and patient optimisation and the limits of such strategies
- Strategies to minimise the use of blood products
- Premedication, Fasting and management of chronic drug therapy (refer to Part A syllabus)
- Medical-legal considerations including consent, risk counselling, refusal of treatment and resuscitation status
- Strategies to minimise post-operative cognitive dysfunction
- Principles of enhanced recovery pathways

### Postoperative Management
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#6. POSTOPERATIVE COMPLICATIONS]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Postoperative Management";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Requirements and set-up of the post-anaesthesia care unit
- Acute Pain Management
- Consequences of and its management of Anaesthesia and Surgical Incisions:
  - Respiratory
  - Cardiovascular
  - Neurologic and Neuromuscular
  - Gastrointestinal: Nausea and Vomiting
- Role of a multidisciplinary team approach to improve patient recovery and discharge

### Different Physiological States
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.3. GERIATRIC]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#1. DEFINITION AND EPIDEMIOLOGY OF OBESITY]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#2. MANAGEMENT OF OBESITY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Different Physiological States";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

1. Obstetrics patients (Reference to obstetrics anaesthesia)
2. Paediatric patients (Reference to paediatric anaesthesia)
3. Overweight and obese patient
4. Geriatrics patients

### Common or important medical conditions

#### Respiratory System
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#3.2. OBSTRUCTIVE SLEEP APNEA (OSA)]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Respiratory System";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Obstructive disease
- Restrictive disease
- Pulmonary hypertension
- Infection: e.g. Upper respiratory tract infection
- Patient with respiratory disease for non-thoracic surgery versus thoracic surgery
- Tobacco Usage

#### Cardiovascular system
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#3.4. CARDIOVASCULAR AND HEMATOLOGIC SYSTEMS]], [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Cardiovascular system";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Ischemic Heart Disease
- Valvular Heart Disease
- Rhythm Disorders and Conduction Defects
- Pacemaker and/or Automated Implantable Cardioverter/Defibrillator (AICD)
- Heart Failure and Cardiomyopathy
- Cardiac Tamponade and Constrictive Pericarditis
- Pulmonary Embolism: subacute and/or history of
- Hypertension

#### Shock states

#### Vascular Diseases
- Cerebral circulation: TIAs; risks of CVAs; cerebral aneurysms
- Peripheral arteriosclerotic disease
- Aneurysms of ascending, descending and arch of aorta

#### Nutrition
- Malnutrition and optimisation

#### Gastro-intestinal and Hepatic conditions
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.4 LIVER SURGERY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Gastro-intestinal and Hepatic conditions";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Hepatic dysfunction
- Intestinal Obstruction
- Gastro-oesophageal reflux disease and hiatus hernia; gastro-oesophageal sphincter incompetency

#### Renal Impairment

#### Endocrine Conditions
- Pituitary Disease
- Thyroid Disease
- Parathyroid
- Adrenal Disease
- Pheochromocytoma
- Carcinoid Syndrome
- Diabetes Mellitus

#### Haematological Disorders
- Anemias
- Polycythemias
- Clotting disorders
- Antiplatelets and anticoagulants medications

#### Neuromuscular Disease (classified based on level of lesion)
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Neuromuscular Disease (classified based on level of lesion)";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Epilepsy, old CVA, previous head injury/ICH/SAH/SDH etc
- Parkinson's disease / cerebellar disease
- Spinal cord injury
- Peripheral nerves: e.g. demyelinating diseases (multiple sclerosis, Guillain-Barre Syndrome), Charcot-Marie-Tooth Disease; motor neuron diseases: amyotrophic lateral sclerosis, spinobulbar muscular atrophy, hereditary spastic paraplegia
- Primary muscle diseases
  - Muscular dystrophies: Duchenne's, Becker's, limb-girdle, congenital, myotonic
  - Mitochondrial myopathies
  - Channelopathies
  - Myasthenic syndromes (myasthenia gravis, Lambert-Eaton myasthenic syndrome, Congenital myasthenic syndromes)
  - Ion channel myotonias (acquired neuromyotonia, myotonia congenita)
  - Hyperkalemic periodic paralysis, paramyotonia congenita, potassium-aggravated myotonia
  - Hypokalemic periodic paralysis

#### Rheumatological/autoimmune disorders
- Rheumatoid arthritis
- Scleroderma
- Ankylosing spondylitis
- SLE and other conditions

---

## C6 Ethics Medico-Legal Issues Quality Improvement Evidence Based Medicine
<!-- covered-by: [[1. BASIC SCIENCES/1.2. STATISTICS#critical-appraisal-and-interpretation]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "C6 Ethics Medico-Legal Issues Quality Improvement Evidence Based Medicine";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Ethical and Medical-Legal issues
1. Informed consent
2. Professionalism
3. Credentialing and privilege to practice
4. Advance Directives/Do Not Resuscitate (DNR)
5. Patient Privacy Issues
6. Medical errors
7. Open disclosures
8. Costs of Medical/Anaesthesia Care, Operating Room Management
9. End of life decision making
10. HOTA and related issues
11. Research ethics

### Patient and Staff Safety
1. Definitions
2. Medication Errors, Reporting, Root cause analysis and Disclosures
3. Safety Practices: Guidelines
4. Non-technical skills
5. Staff impairment or disability

### Infection control

### Quality improvement

### Biostatistics and Evidence based Medicine/Practice - paper critic
<!-- covered-by: [[1. BASIC SCIENCES/1.2. STATISTICS#hypothesis-testing-and-inferential-statistics]], [[1. BASIC SCIENCES/1.2. STATISTICS#statistical-tests-and-applications]], [[1. BASIC SCIENCES/1.2. STATISTICS#advanced-statistical-methods]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Biostatistics and Evidence based Medicine/Practice - paper critic";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

(Reference Part A Syllabus)

### Research: Clinical trial
(Reference Part A Syllabus)

---

## S1 Critical Care Medicine
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#6. POSTOPERATIVE COMPLICATIONS]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#1. INTRODUCTION TO TRAUMA ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#4. CARDIOVASCULAR MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#7. RENAL AND FLUID MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#11. FUTURE DIRECTIONS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S1 Critical Care Medicine";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Applied Pharmacology
(Reference Part A Syllabus)

### Applied Physiology
(Reference Part A Syllabus)

### Clinical Monitoring
(Reference Part A Syllabus)

### General Care
- Indication and goals for admission
- Scoring systems to assess severity
- Universal precautions and infection control
- Nutrition
- Analgesia and sedation
- Effect of critical illness on the pharmacokinetics and pharmacodynamics of sedative and analgesic agents
- Weaning of sedative and analgesics agents
- Use of muscle relaxants
- Nosocomial infections
- Complications of prolonged intensive care
- Transfer of critically ill patients
- Communication: inter-disciplinary and patient/relatives

### Sepsis and multi-organ dysfunction
- Sepsis, severe sepsis and systemic inflammatory response syndrome (SIRS)
- Mechanisms of organ dysfunction
- Goal directed therapy of sepsis
- Antimicrobial agents
- Preventing infection in intensive care

### Acute circulatory failure and cardiovascular disorders
- Shock
- Monitoring: Cardiac output, Tissue perfusion, Arterial blood gases (Reference Part A)
- Heart Failure
- CVS support: Pharmacological (Reference Part A)
- Cardiac arrhythmias
- Pulmonary embolic disorders
- Cardiac arrest

### Respiratory failure and intensive care of respiratory disorders
(Reference Airway Oxygenation and Ventilation)
- Respiratory failure
- Principles of management of respiratory failure (Refer to C1: Airway Oxygenation, Ventilation)
- Conditions that lead to respiratory failure
- Complications of intubation and ventilation
- Strategies for weaning patients off ventilatory support
- Upper airway obstruction
- Tracheostomy

### Renal and fluid and electrolyte disorders
- Acute renal failure in the critically ill patient
- Conditions which can lead to acute renal failure
- Renal replacement therapy
- Fluid and electrolyte, and acid-base disturbances in the critically ill patient
- Postoperative care of the renal transplant recipient

### Metabolic and endocrine disorders
- Metabolic response to trauma, surgery and critical illness
- Acute metabolic and endocrine conditions

### Neurological and neuromuscular disorders

#### Determinants, control and monitoring of
- Intracranial and intraspinal pressure
- Cerebral blood flow
- Spinal cord perfusion

#### Pathophysiology, assessment and management of specific conditions
- Acute traumatic brain injury
- Raised intracranial pressure
- Prolonged seizures
- Acute spinal cord injury
- Hemiplegia, paraplegia, quadriplegia
- Delirium
- New neurological impairment
- Neurological deterioration (due to various vascular causes)
- Cerebral vasospasm
- Diabetes insipidus
- Cerebral salt wasting
- Neurosurgical patients postoperatively
- Encephalitis and meningitis
- Persistent vegetative state

#### Brain death and organ donation
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#2. BRAIN-DEAD DONORS (DONATION AFTER NEUROLOGIC DETERMINATION OF DEATH)]], [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#3. DONATION AFTER CIRCULATORY DETERMINATION OF DEATH (DCD)]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Brain death and organ donation";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Confirmation of brain death, issues with communication to family and medico-legal considerations
- Management of the brain-dead patient/potential organ donors

### Gastrointestinal disorders

#### Assessment and management of the following intra-abdominal conditions
- Oesophageal perforation
- Gastrointestinal haemorrhage
- Acute pancreatitis
- Acute and acute on chronic liver failure
- Abdominal sepsis
- Ischemic bowel
- Bowel perforation
- Intestinal obstruction
- Major abdominal trauma
- Post-major abdominal surgery

### Haematological and oncological disorders
(reference Trauma)

#### Coagulopathy due to
- Trauma
- Medications
- Disseminated intravascular coagulation
- Use of anti-coagulants for prevention and management of venous and arterial thrombosis and thromboembolism
- Management of anaemia and thrombocytopaenia
- Blood products and transfusion reactions

### Obstetric patient
(Reference Obstetrics Anaesthesia)
- Consideration and requirements
- Resuscitation
- Specific conditions:
  - Severe pre-eclampsia and eclampsia
  - Post-partum haemorrhage
  - Amniotic fluid embolism

---

## S2 Pain Medicine
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#5.4. POSTOPERATIVE ANALGESIA]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.3. ACUTE PAIN]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.4. CHRONIC PAIN]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES#6.1. ACUTE PAIN MANAGEMENT]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S2 Pain Medicine";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Pain Physiology and Anatomy
(Reference Part A Syllabus)

### Pain Pharmacology
(Reference Part A syllabus)

### Consideration with use of controlled medications

### Clinical Approach: General Principles

#### Biopsychosocial model

#### Differentiate
- Acute versus Chronic pain
- Nociceptive versus Neuropathic pain
- Somatic versus Visceral pain
- Background versus breakthrough pain

#### Other considerations
- Acute pain progressing to chronic pain
- Impact of psychological and social factors e.g.:
  - Mood: depression and anxiety
  - Placebo effect
  - Active and passive coping strategies
  - Illness behaviour
  - Compensation and third-party issues
- Multimodal and multidisciplinary pain management
- Complications of pain management modalities

### Clinical Approach: Specific Conditions

#### Specific to Acute Pain Conditions
- Traumatic, post-operative and acute and acute on chronic medical conditions: inflammatory, neurological, haematological, immunological, iatrogenic
- Multimodal and multidisciplinary management plan
- Considerations: Type of procedure, fast track surgery and enhanced recovery
- Organisation of perioperative pain management services

#### Specific to Chronic Pain Conditions
- Multimodal and multidisciplinary management plan of:
  - Nociceptive pain
  - Neuropathic pain
  - Inflammatory conditions
  - Central sensitization conditions
- Describe the basis of, indications and contra-indications of, effects of and evidence for:
  - Pharmacological therapy of neuropathic pain
  - Pharmacological therapy of chronic visceral and somatic pain
  - Opioid usage in chronic pain
  - Interventional pain therapy

### Clinical Approach: Specific Patient groups

#### Multimodal and multidisciplinary management plan for situations
- Opioid tolerant, opioid dependent or addicted patients presenting with acute pain
- Altered physiology: Extremes of age (young and old), Pregnancy and breastfeeding
- Co-morbidities such as obstructive sleep apnoea, renal or hepatic impairment
- Patients with cancer

---

## S3 Obstetrics Anaesthesia and Analgesia

### Peri-partum changes in maternal anatomy and physiology
(Reference Part A)
- Implications for anaesthesia

### Changes in physiological and biochemical reference ranges in pregnancy
(Reference Part A)

### Pharmacological impact of pregnancy
(Reference Part A)

### Maternal-Fetal and Fetal physiology
(Reference Part A)

### Perioperative management of a pregnant patient
- General Principles
- Caesarean Section

### Analgesia techniques for labour and delivery
- Options, Risks, Consent, Complication management

### Complications during Pregnancy

#### Problems presenting during pregnancy and delivery
- Anaesthesia for cervical cerclage or non-obstetric surgery
- Ectopic pregnancy
- Spontaneous abortion
- Gestational trophoblastic disease (hydatid mole)
- Heart disease (valvular disorders, pulmonary hypertension, congenital heart disease, arrhythmias, cardiomyopathy)
- Hypertension (chronic, pregnancy-induced, pre-eclampsia)
- Neurologic (seizures, myasthenia, spinal cord injury, multiple sclerosis, subarachnoid hemorrhage)
- Respiratory conditions (asthma, respiratory failure)
- Renal impairment
- Acute fatty liver of pregnancy, cholestasis associated with pregnancy
- Endocrine (thyroid, diabetes - preexisting and gestational, phaeochromocytoma)
- Haematological (sickle cell anemia, idiopathic thrombocytopenic purpura, von Willebrand disease, disseminated intravascular coagulation (DIC), anticoagulant therapy, Rh and ABO incompatibility)
- Autoimmune disorders (lupus, anti-phospholipid syndrome)
- Human immunodeficiency virus infection
- Morbid obesity
- Substance abuse
- Trauma in pregnant patient

#### Problems of term and delivery
- Intrapartum fetal assessment (fetal heart rate monitoring such as cardiotocography and basic interpretation of assuring and non-assuring traces, fetal scalp blood gases, fetal pulse oximetry)
- Preeclampsia, HELLP syndrome and eclampsia
- Supine hypotensive syndrome
- Aspiration of gastric contents
- Embolic disorders (amniotic fluid embolism, pulmonary thromboembolism)
- Antepartum haemorrhage (placenta previa, abruptio placenta, uterine rupture)
- Postpartum haemorrhage (e.g. uterine atony, placenta accreta)
- Cord prolapse
- Uterine rupture
- Retained placenta
- Dystocia, malposition, and malpresentation (breech, transverse lie)
- Fever and infection
- Preterm labor
- Vaginal birth after cesarean section (VBAC)
- Multiple gestation
- Assisted vaginal birth
- Foetal death in utero

### Maternal collapse and resuscitation

#### General principles

#### Diagnosis and specific management
- Thromboembolism
- Amniotic fluid embolism
- Air embolism
- Anaphylaxis
- Local anaesthetic toxicity
- High spinal
- Massive haemorrhage
- Eclampsia
- Maternal sepsis

### Resuscitation of Newborn
- Apgar scoring
- Umbilical cord blood gas measurements
- Techniques and pharmacology of resuscitation

---

## S4 Paediatric Anaesthesia
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.2. PEDIATRIC]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#7. PEDIATRIC ORTHOPEDIC ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#12. SPECIAL POPULATIONS]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#2. PEDIATRIC ENT ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#3. PEDIATRIC AIRWAY EMERGENCIES]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S4 Paediatric Anaesthesia";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Normal anatomy and physiology of neonates, infants and children
(Reference Part A for neonatal aspects)

#### Cardiovascular
- Transitional circulation
- Normal parameters across the different age range

#### Respiratory and airway
- Development, anatomy, surfactant
- Pulmonary function/lung volumes in children vs adults and implications
- Airway differences that occur as a child develops from infancy to adulthood
- Normal respiratory parameters

#### Neurological
- Normal developmental milestones
- Assessment of GCS in children

#### Thermoregulation
- Thermogenesis and heat loss in children
- Thermoneutral zone

#### Renal function development and implications on
- Fluid and electrolyte requirements
- Drug handling

#### Hepatic function development and implications on
- Glucose metabolism
- Drug handling

#### Nutritional requirements

#### Haematological
- Physiological anemia
- Fetal haemoglobin versus adult hemoglobin
- Coagulation

#### Immunological development
- Vaccination

### Pharmacological differences from adults
- Pharmacodynamic and pharmacokinetic profiles
- Drug toxicities preferentially occurring in children
- Effects of anaesthetics on neurodevelopment

### Psychological aspects

### Perioperative Management of neonatal and paediatric patient

#### Specific Medical Issues
- The premature neonate and problems related to prematurity
- The ex-premature infant
- The sick neonate/critically ill child/assessment of the circulatory system: e.g. degree of dehydration
- The syndromic/dysmorphic child: e.g. Trisomy 21
- Paediatric medical problems and implications for anaesthesia:
  - Atopy: Asthma; Allergic rhinitis; Eczema
  - Congenital heart disease
  - Obstructive sleep apnoea
  - Stridor and causes
  - Neuromuscular disease: Cerebral palsy; Epilepsy; Muscle disease (e.g. Duchenne's/Becker's muscular dystrophy, myotonias, Spinal muscular atrophy etc)
  - Developmental delays/autism/learning difficulties
  - Gastrointestinal disease
  - Endocrine/metabolic
  - Oncology: Cancer & Treatment, Immuno-compromised, Anterior mediastinal mass
  - Rheumatology
  - Haematological
  - Primary immune deficiency in childhood (SCID severe combined immune deficiency)
  - Skeletal abnormalities

#### Specific Preoperative Issues
- Medical legal issues relating to paediatric practice in respect of Consent, Assent, Restraint and Research and the concept of 'Gillick competence'
- Fasting guidelines; Preop instructions and Premedication
- Child with the potentially full stomach: Rapid sequence induction/modification
- Management of patients and parents and carers in patients with cognitive, communication or behavioural problems

#### General Intra-operative Issues
- Anaesthetic Agents and Techniques: Induction & induction agents; neuromuscular blockade and RA
- Fluid therapy and blood replacement
- Management of difficult paediatric airway
- Recognition and management of airway obstruction in children
- Equipment for neonatal/paediatrics patients:
  - Breathing circuits
  - Airway equipment
  - Mechanical ventilation
  - Thermal Control
- Clinical Monitoring in Paediatrics

#### Specific Anaesthetic Intraoperative Issues
- Congenital Heart and Major Vascular Disease: impact on and of anaesthesia
- Neonatal Emergencies: types and implications
- Anaesthetic implications and requirements for Common Non-neonatal Paediatric Subspecialty Surgery
- Drowning and near-drowning
- Burns: difference in paediatrics

### Paediatric Resuscitation
(Reference Crisis Management)

#### Basic life support

#### Specific management
- Cardiac arrest
- Respiratory arrest
- Laryngospasm
- Bronchospasm
- Aspiration of gastric contents
- Tension pneumothorax
- Shock
- Anaphylaxis
- Latex allergy
- Sepsis
- Post-tonsillectomy haemorrhage
- Gas embolism
- Fat embolism
- Raised intracranial pressure
- Local anaesthetic systemic toxicity
- Malignant hyperthermia
- Coagulopathy
- Life threatening glucose, electrolyte or acid-base disturbances
- Electrocution
- Poisoning

### Specific Post-operative Issues
- Postoperative agitation
- Postoperative Nausea and Vomiting

### Other Issues
- Paediatric sedation
- Paediatric Pain management
- Outpatient Paediatric Anaesthesia: indications/contraindications; selection; anaesthesia considerations and techniques; postoperative issues and management
- Paediatric Anaesthesia Outside the Operating Theatre

---

## S5 Neurosurgery and Neuroradiology
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#5. NEUROLOGIC MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S5 Neurosurgery and Neuroradiology";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Basic Sciences
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#2. NEUROANATOMY]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#7. NEUROPHYSIOLOGY]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#13. PATHOPHYSIOLOGY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Basic Sciences";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Anatomy, Pathophysiology, Pharmacology, Clinical and Radiological features (Reference Part A)
- Clinical Grading of subarachnoid haemorrhage (WFNS, Hunt and Hess)
- Radiological features of common acute neurosurgical conditions

### Neurosurgical procedures: anaesthetic considerations and management plan

#### Elective Procedures
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#32. ANESTHETIC MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#42. BRAIN TUMOR SURGERY]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#44. PITUITARY SURGERY]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#45. CEREBRAL ANEURYSM SURGERY AND ENDOVASCULAR TREATMENT]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#48. EPILEPSY SURGERY]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#49. AWAKE CRANIOTOMY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Elective Procedures";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Craniotomy for tumor surgery: location of tumor; role of anaesthesia technique; positioning; complications
- Craniotomy for neurovascular surgery: variety and implications of pathology; management of occlusions or rupture/bleeding
- Spine surgery: unstable spine or spinal injury; airway management; monitoring
- Spinal fluid shunt surgery
- Craniotomy for movement disorders/epilepsy: awake craniotomy

#### Emergency Procedures
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#50. TRAUMATIC BRAIN INJURY]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#51. PATHOPHYSIOLOGY AND CLASSIFICATION]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#52. ANESTHETIC MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#53. SPINE TRAUMA AND COMPLEX SURGERY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Emergency Procedures";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Craniotomy/Craniectomy for Traumatic Brain Injury (TBI): ICP management; monitoring of CBF and perfusion; secondary brain injury/cerebral protection; fluid management
- Craniotomy for intracerebral haemorrhage
- Prioritisation of surgery in a polytrauma patient

### Neuro-radiological procedures: implication of location and set-up

#### Elective
- Interventional radiology for intracranial vascular pathology

#### Emergency
- Interventional radiology for emergency clot retrieval

### Neurosurgical specific emergency or crisis
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#26. CEREBRAL PROTECTION]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#43. VENOUS AIR EMBOLISM IN SITTING POSITION]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#45. CEREBRAL ANEURYSM SURGERY AND ENDOVASCULAR TREATMENT]], [[8. CLINICAL ANAESTHESIA/8.8 NEUROSURGERY#50. TRAUMATIC BRAIN INJURY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Neurosurgical specific emergency or crisis";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Venous Air Embolism
- Intraoperative Aneurysm rupture
- Refractory intracranial hypertension in traumatic brain injury

---

## S6 Cardiac Surgery and Interventional Cardiology
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S6 Cardiac Surgery and Interventional Cardiology";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Preoperative Issues

#### Perioperative assessment of
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#2. CORONARY ARTERY DISEASE]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#3. VALVULAR HEART DISEASE]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#7. PREOPERATIVE AND INTRAOPERATIVE MANAGEMENT]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Perioperative assessment of";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Myocardial ischaemia
- Cardiac rhythm
- Preload
- Left ventricular systolic and diastolic function
- Right ventricular function and pulmonary artery pressure
- Valve pathologies
- Intra-cardiac and extra-cardiac shunts
- Congenital heart disease in adult patients

#### Initial medical management of specific conditions
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#4. AORTIC DISEASES]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#5. HEART FAILURE]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#10. POSTOPERATIVE MANAGEMENT AND COMPLICATIONS]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Initial medical management of specific conditions";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Acute thoracic aortic dissection
- Acute myocardial infarction
- Cardiogenic shock
- Cardiac tamponade

#### Other preoperative considerations
- Anxiety management in patients presenting for cardiac surgery
- Management of chronic medications e.g. antiplatelets, anti-coagulation, anti-hypertensive etc
- Cardiac Risk Assessment
- Management: patients with cardiac disease requiring non cardiac surgery

### Intraoperative

#### Monitoring: specific issues
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#7.3. MONITORING]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#13. BASIC PERIOPERATIVE TEE AND CARDIAC POCUS]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Monitoring: specific issues";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Cardiac output estimation
- Invasive lines e.g. Pulmonary artery catheter, interpretation data/waveforms
- Echocardiography

#### Surgical Aspects
- Commonly encountered cardiac procedures e.g.: Coronary artery bypass both on and off pump; Aortic and mitral valve replacement; Repair of aortic dissection including principles of spinal cord protection
- Indications for cardiopulmonary bypass and ECMO in non-cardiac surgery procedures

#### Anaesthesia considerations/technique for cardiac surgical procedures
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#2. CORONARY ARTERY DISEASE]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#3. VALVULAR HEART DISEASE]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#7. PREOPERATIVE AND INTRAOPERATIVE MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#11. MINIMALLY INVASIVE CARDIAC SURGERY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Anaesthesia considerations/technique for cardiac surgical procedures";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

Including haemodynamic goals for:
- Coronary artery bypass
- Aortic and mitral valve replacement
- Cardiac tamponade
- Minimally invasive techniques

#### Cardiopulmonary bypass techniques
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#6. CARDIOPULMONARY BYPASS]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#8. CARDIOPULMONARY BYPASS MANAGEMENT]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Cardiopulmonary bypass techniques";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Components (pump, oxygenator, heat exchanger, filters)
- Mechanisms of gas exchange
- Priming solutions, haemodilution
- Maintenance of anaesthesia during this period
- Cooling and warming, deep hypothermic circulatory arrest
- Intraoperative myocardial protection: physiology, pharmacologic, techniques, complications
- Potential neurocognitive effects and cerebral protection
- Renal protection
- Implications of aortic disease for aortic cannulation
- Reperfusion injury, ischaemic and pharmacologic preconditioning
- Haematological and inflammatory effects of cardiopulmonary bypass

### Circulatory Assist
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#5.4. MECHANICAL CIRCULATORY SUPPORT]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Circulatory Assist";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Principles, rationale, indications, limitations of intra-aortic balloon counterpulsation
- Ventricular assist devices and artificial heart: internal and external
- Veno-Arterial Extracorporeal membrane oxygenation (VA-ECMO)
- Indications and rationale of circulatory arrest

### Haematological issues
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#6.3. ANTICOAGULATION]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#6.4. BLOOD CONSERVATION IN CARDIAC SURGERY]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#10.3. HEMOSTASIS AND BLEEDING MANAGEMENT]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Haematological issues";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Anticoagulation, monitoring, management
- Antifibrinolytics
- Heparin/protamine and issues
- Blood products and transfusion issues

### Defibrillation and Pacing
- External/internal
- Programming of pacemakers

### Postoperative Issues
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#9. SEPARATION FROM CPB AND POST-CPB MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#10. POSTOPERATIVE MANAGEMENT AND COMPLICATIONS]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Postoperative Issues";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Routine and emergent postoperative management
- Recognition and management of common complications including reopening for bleeding
- Ventricular assist devices: management and resuscitation
- 'Fast-track' cardiac surgery
- Postoperative ventilation

### Interventional cardiology
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.2 CARDIAC SURGERY#11.4. PERCUTANEOUS APPROACHES]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Interventional cardiology";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Anaesthesia for acute and elective cardiac revascularisation
- Anaesthesia for other interventional cardiology procedures: including electrophysiological studies, radiofrequency and cryoablation for arrhythmias, pacemaker and defibrillator insertion, insertion of percutaneous closure devices, percutaneous valve repair and replacement and valvuloplasty
- Major complications associated with interventional cardiology procedures
- Anaesthesia for cardioversion

---

## S7 Thoracic Surgery
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S7 Thoracic Surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Anatomy
(Reference Part A)
- Tracheobronchial tree including endoscopic anatomy
- Lung lobes and segments
- Thorax: surface anatomy, intra-thoracic structures and relations
- Innervation of the chest wall and intra-thoracic structures

### Physiology
(Reference Part A)
- Change with positioning, effect of open thorax, positive-pressure ventilation and one-lung ventilation
- Mechanism and effect of hypoxic pulmonary vasoconstriction and the influence of medications, including anaesthetic agents

### Preoperative Issues
- Assessment of the patients with thoracic pathology presenting for thoracic or non-thoracic surgery (Reference Periop Medicine)
- Assessment of the patients for lobectomy and pneumonectomy

#### Specific medical pathologies
- Pulmonary hypertension: factors affecting/management of pulmonary pressures
- Chronic obstructive pulmonary disease and effects of artificial ventilation

#### Specific conditions associated with thoracic trauma
- Pneumothorax/tension pneumothorax Haemothorax
- Flail chest
- Rib/sternal fractures
- Pulmonary contusion
- Traumatic aortic disruption
- Tracheobronchial injury, bronchopleural fistula
- Respiratory failure and artificial ventilation

### Intraoperative: Issues and interventions specific to thoracic surgery
- Positioning
- Lung isolation
- One-lung ventilation: Indications and contraindications; management of issues
- Intermittent apnoea versus spontaneous versus jet ventilation
- Analgesia options: for thoracic surgery and thoracic trauma
- Fluid management following lung resection and thoracic trauma
- Management of chest drains and pleural drainage system

### Specific procedures

#### Endobronchial procedures
- Flexible bronchoscopy
- Diagnostic bronchoscopy
- Bronchoalveolar lavage
- Bronchoscopic ultrasound and biopsy
- Placement of endobronchial stent
- Rigid bronchoscopy
- Removal of foreign body in airway
- Laser of endobronchial tumour

#### Open or thoracoscopic procedures
- Excision or biopsy of mediastinal mass
- Thymectomy, with or without myasthenia gravis
- Mediastinoscopy
- Thoracoscopy and thoracotomy for:
  - Pleurodesis
  - Bleeding
  - Bronchopleural fistula
  - Lobectomy
  - Pneumonectomy
  - Drainage of lung abscess
  - Drainage of empyema and decortication of lung
  - Lung volume reduction surgery
  - Giant bullous emphysema resection
  - Thoracoscopic sympathectomy
  - Mediastinal masses
  - Pectus excavatum surgery

### Complications associated with thoracic surgery
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Complications associated with thoracic surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Bleeding (airway, lung or pleural cavity)
- Pneumothorax
- Arrhythmias
- Bronchopleural fistulae
- Nerve damage (phrenic, recurrent laryngeal)
- Respiratory failure

---

## S8 General Surgical Urological Gynaecological and Endoscopic Procedures
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#2.2. BARIATRIC SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S8 General Surgical Urological Gynaecological and Endoscopic Procedures";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Anaesthesia considerations of conditions seen in surgical patients
(Reference Periop Medicine)
1. Poor nutrition
2. Morbid obesity
3. Disease of the oesophagus including oesophageal carcinoma, gastro-oesophageal reflux disease, hiatus hernia and gastro-oesophageal sphincter abnormalities
4. Disease of the stomach including cancer
5. Gastrointestinal haemorrhage: upper and lower
6. Acute abdomen
7. Abdominal compartment syndrome
8. Intestinal obstruction, malabsorption, diarrhoea, vomiting, ileus
9. Gallbladder and Hepatic Disease: including hepatocellular disease, ascites, portal hypertension
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.4 LIVER SURGERY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Anaesthesia considerations of conditions seen in surgical patients";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

10. Disease of the spleen
11. Renal and urinary tract disease
12. Pancreatic disease
13. Adrenal disease
14. Gynaecological disorders
15. Breast disease

### Anaesthetic considerations for endocrine conditions
1. Hypopituitarism
2. Hyperpituitarism
3. Hyperthyroidism
4. Hypothyroidism
5. Hyperparathyroidism
6. Hypoparathyroidism
7. Adrenal Disease
8. Cushing's syndrome
9. Primary aldosteronism
10. Addison's disease
11. Pheochromocytoma
12. Carcinoid Syndrome
13. Diabetes Mellitus

### Considerations and requirements for specific surgery
1. Bowel preparation
2. Laparoscopic: pneumo-peritoneum
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Considerations and requirements for specific surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

3. Positioning required for surgical access
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES#5.2. PATIENT POSITIONING COMPLICATIONS]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Considerations and requirements for specific surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

4. Hepatectomy
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.4 LIVER SURGERY#37. SPECIFIC PROCEDURES]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Considerations and requirements for specific surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

5. Surgery for major liver trauma
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.4 LIVER SURGERY#37. SPECIFIC PROCEDURES]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Considerations and requirements for specific surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

6. Oesophagectomy
7. Pancreatectomy
8. Adrenalectomy, including phaeochromocytoma
9. Resection of carcinoid tumour
10. Bariatric surgery
11. Breast reconstruction
12. Surgery for gynaecological and urological malignancy
13. Major bowel resection, pelvic exenteration etc
14. Urologic procedures including lithotripsy, transurethral resection of prostate (TURP)/irrigating Fluids/hyponatraemia, robotic surgery in prostatectomy
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES#2.3. ROBOTIC-ASSISTED LAPAROSCOPIC SURGERY]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Considerations and requirements for specific surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

15. Principles and evidence for Enhanced Recovery programmes and Fast Track Surgery
16. Endoscopic procedures including ERCP, PEG insertion, and emergency gastroscopy for upper gastrointestinal bleeding
17. Transplant surgery: renal, hepatic, pancreatic
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.4 LIVER SURGERY]], [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#4. LIVING KIDNEY DONORS]], [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#5. LIVING LIVER DONORS]], [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#8. KIDNEY TRANSPLANTATION]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Considerations and requirements for specific surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

18. Organ donation in a brain-dead patient
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#1. ANESTHETIC MANAGEMENT OF ORGAN DONORS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Considerations and requirements for specific surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Complications of surgical procedures including
1. Venous air embolus
2. Bleeding, including management of severe coagulopathy
3. Aspiration
4. Cardiovascular responses to insufflation of the peritoneal cavity
5. Sepsis
6. Hypo-osmolar syndromes
7. Reperfusion of ischaemic organs
8. Acid base imbalance, temperature control, positioning injuries

---

## S9 Vascular Surgery and Interventional Radiology
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S9 Vascular Surgery and Interventional Radiology";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Pathophysiology, assessment and perioperative management
Of patients presenting for vascular surgery including the following medical conditions:
- Peripheral vascular disease
- Ischaemic heart disease
- Cardiac failure
- Arrhythmia
- Hypertension
- Diabetes mellitus
- Chronic obstructive airways disease
- Renal failure
- Recent cerebrovascular accident
- Concurrent antiplatelet and anticoagulation treatment

### Influence of vascular disease on outcome including
- Wound dehiscence and infection
- Positioning injury
- Perioperative myocardial ischaemia
- Perioperative stroke
- Perioperative renal failure

### Considerations and perioperative management for patients presenting for elective surgery for
- Peripheral arterial occlusive disease
- Carotid artery stenosis/carotid endarterectomy (GA or RA)
- Aortic and aorto-iliac disease
- Vascular access for haemodialysis
- Thoracoscopic sympathectomy

### Considerations and perioperative management for patients presenting for emergent surgery for
- Ruptured aortic aneurysm
- Aortic dissection
- Major vessel occlusion
- Limb ischaemia
- Limb amputation
- Arterial laceration

### Pathophysiology and implications of
- Aortic cross clamping and unclamping at various levels
- Prolonged limb or gut ischaemia
- Carotid clamping and unclamping, and post-op effects of carotid endarterectomy

### Complications seen during vascular surgery
- Major haemorrhage; including strategies to minimize blood loss and transfusion
- Bradycardia associated with carotid artery surgery
- Cerebral ischaemia associated with carotid artery clamping including monitoring of cerebral perfusion
- Reperfusion syndromes
- Spinal cord ischaemia
- Acute renal impairment
- Myocardial ischaemia
- Acute arrhythmia
- Stroke
- Thromboembolism
- Limb ischaemia
- Rhabdomyolysis
- Post-amputation pain (Refer Pain Medicine)

### Implications of vascular interventional procedures in remote locations
E.g. interventional radiological suite including:
- Impact of patient and staff safety
- Requirements for provision of anaesthetic service
- Awareness of space and equipment limitations (e.g. DDI bed not being able to tilt, access to head obstructed by head holder/C-arm)

### Considerations and management of patients presenting in the radiological suite for
- Vascular embolisation
- Insertion of intravascular devices including aortic grafts, e.g. TEVAR (thoracic endovascular stent) etc
- Radiological-guided biopsy under anaesthesia
- Radiofrequency ablation of lesions in lung and liver

### Complications in the context of a radiological based interventional procedures such as
- Reaction to intravenous iodine contrast
- Aortic occlusion
- Acute renal impairment
- Spinal cord ischaemia
- Radiation
- Haemorrhage
- Airway compromise

### Advantages and disadvantages of radiological based procedures compared to open procedures
For the management of:
- Aortic aneurysm
- Aortic dissection
- Carotid artery stenosis

---

## S10 Orthopaedic Surgery
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S10 Orthopaedic Surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Orthopaedic Trauma

#### Assessment, diagnosis and management of patient following trauma including the following injuries
- Suspected cervical spine injury
- Unstable spinal injury
- Acute spinal cord injury and 'neurogenic' shock
- Pelvic fractures
- Long bone fractures
- Geriatric patients with fractures

#### Anaesthetic considerations and management of patient presenting for orthopaedic trauma surgery
Including the following conditions:
- Pelvic fractures
- Shoulder girdle fractures
- Long bone fractures
- Distal limb fractures
- Reduction and fixation of spinal fractures
- Fractures associated with neurovascular compromise
- Compound fractures
- Open fractures
- Geriatric patients with hip fractures

#### Diagnosis and management of complications associated with orthopaedic surgery
- Bone cement implantation syndrome (BCIS)
- Haemorrhage
- Massive transfusion
- Crush injury
- Compartment syndrome
- Re-perfusion injury
- Fat embolism syndrome

#### Considerations specific to orthopaedics surgery
- Issues and management of non-accidental injuries
- Use of preventive therapies such as thrombo-prophylaxis and antibiotic prophylaxis in orthopaedic trauma surgery
- Regional versus general anaesthesia

### Elective and non-traumatic emergency orthopaedic surgery

#### Assessment and perioperative management of comorbidity and patient factors
Commonly found in patients presenting for orthopaedic surgery:
- Geriatrics patient
- Sepsis
- Cerebral palsy
- Obesity
- Arthritis (osteoarthritis, rheumatoid arthritis or ankylosing spondylitis)
- Therapeutic anticoagulation

#### Anaesthetic considerations, assessment and perioperative management of patients presenting for elective orthopaedic surgery
Such as:
- Joint replacement
- Joint arthroscopy
- Shoulder surgery
- Ligament, peripheral nerve and/or artery repair
- Tendon lengthening or transfer
- Compartment syndrome
- Dislocated joint, including prosthesis Joint infections
- Joint infections
- Pathological fractures
- Spine/Scoliosis correction surgery

#### Anaesthetic considerations, assessment and perioperative management of patients presenting for emergency non-traumatic orthopaedic surgery
Such as:
- Necrotising fasciitis
- Amputations and removal of septic foci

#### Diagnosis and management of the possible complications of orthopaedic surgery
- Bone cement implantation syndrome (BCIS)
- Fat embolism syndrome
- Pulmonary embolism
- Compartment syndrome
- Major blood loss
- Neurological injury
- Chronic and persistent pain

#### Considerations specific to orthopaedics surgery
- Safe use of tourniquet
- Regional versus general anaesthesia
- Choice and timing of antibiotic prophylaxis
- Use of thrombo-prophylaxis
- Techniques to reduce blood loss and minimize transfusion of blood products
- Methods of spinal cord monitoring and anaesthetic considerations
- Use of beach chair positioning
- Management of acute and acute-on-chronic pain including the use of NSAIDs, use of regional anaesthesia/analgesia, use of adjuvant agents and prevention of chronic post-surgical pain

---

## S11 Plastic Reconstructive and Burns Surgery
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#12. SPECIAL POPULATIONS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S11 Plastic Reconstructive and Burns Surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Plastics and Reconstructive Surgery

#### Type of surgery that candidates should be familiar with
- Removal of multiple skin lesions
- Cosmetic surgery, including flap surgery and paediatric conditions such as cleft lip/palate
- Split skin graft
- Full thickness graft
- Resection or debridement of tissue (minor and major)
- Liposuction

#### Specific knowledge and skills required of this subspecialty
- Different types of tissue flaps and the implications for flap survival
- Factors affecting blood flow to tissue flaps
- The physiological mechanisms controlling and regulating body temperature and the effects of anaesthesia
- Various techniques of liposuction including the tumescent technique

#### Specific anaesthetic considerations
- Methods of optimising conditions for flap survival
- Issues with prolonged anaesthesia
- Limited access to the patient
- Assessment and management of major occult blood loss
- Safety, risks and management required providing induced hypotension
- Fat embolism, fluid assessment and blood loss during liposuction
- Local anaesthetic toxicity with tumescent technique

### Burns

#### Type of surgery that candidates should be familiar with
- Debridement of burns injuries
- Escharotomy
- Scar revision following burns: especially for facial and neck scarring

#### Specific knowledge and skills required
- Pathophysiology of burns and the multisystem effects
- Temperature homeostasis in burns patients and the implications of hypothermia
- Fluid status and requirement of patients with burns injuries
- Infection control in burns patients and the prevention of secondary sepsis
- Methods and materials used to provide temporary and long-term coverage of burns

#### Specific anaesthetic considerations and management
- Airway management for patients with facial and neck scarring
- Problems associated with monitoring and venous cannulation
- Blood loss during debridement of burns
- Prevention and management of hypothermia, including monitoring techniques and warming
- Pain issues encountered in the burns patient and their management

#### Assessment and management of specific medical conditions candidates should be familiar with
- Airway and facial burns
- Respiratory burns
- Electrical burns
- Chemical burns
- Carbon monoxide poisoning
- Metabolic effects of burns – including electrolyte emergencies such as hyperkalaemia
- Associated trauma
- Management of fluid status and blood transfusion requirements

---

## S12 Head and Neck Ear Nose and Throat Dental Surgery and Electro-Convulsive Therapy
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#1. AIRWAY EVALUATION AND ASSESSMENT]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#2. PEDIATRIC ENT ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#3. PEDIATRIC AIRWAY EMERGENCIES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#4. SPECIALIZED ENT PROCEDURES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#5. ADULT AND COMPLEX ENT CONDITIONS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S12 Head and Neck Ear Nose and Throat Dental Surgery and Electro-Convulsive Therapy";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Head and neck, Ear, Nose and Throat Surgery

#### Specific Knowledge and Skills required
- Anatomy and innervation of the face, external ear, neck, nasal passages, pharynx and larynx
- Regional or topical anaesthesia for head, neck or ear nose and throat procedures: including awake intubation

#### Surgeries that candidate should be familiar with

**Elective surgery:**
- Septo-rhinoplasty
- Functional endoscopic sinus surgery (FESS)
- Tonsillectomy and/or adenoidectomy
- Microlaryngoscopy
- Panendoscopy
- Insertion of grommets
- Myringoplasty or other middle ear surgery
- Mastoidectomy
- Laryngectomy or pharyngo-laryngectomy
- Parotidectomy
- Neck dissection
- Tracheostomy

**Emergent surgeries:**
- Reduction of fractured nose
- Removal of inhaled foreign body
- Removal of foreign body from the oesophagus or pharynx
- Surgical management for obstructing laryngeal and tracheal lesions (also refer to the Airway management clinical fundamental)
- Drainage of oro-pharyngeal cysts or abscess, including quinsy
- Awake tracheostomy

#### Specific equipment candidates should be familiar with

**Special tracheal tubes for these surgeries including:**
- Microlaryngeal surgery
- Laser surgery
- Laryngectomy

**Jet ventilation:**
- Low and high frequency
- Mode of delivery (supraglottic, subglottic and transtracheal)
- Manual and automatic jet ventilators
- Understanding the parameter settings for automatic jet ventilators

**Medical lasers:**
- Nature, biological effects, risks and implications

#### Anaesthesia considerations
- Airway: effects of previous surgery or radiation
- Airway: impact of goitre and large, symptomatic retrosternal goitre
- Positioning for head and neck surgery
- Use of induced hypotension
- Use of local anaesthetic with vasoconstrictive agents
- Methods for the smooth emergence and/or extubation of patients to minimise bleeding following ear nose and throat and head and neck procedures
- Monitoring of nerve function (facial, recurrent laryngeal nerve) during surgery

#### Pathophysiology, assessment and management of medical conditions associated with

**Thyroid or parathyroid surgery:**
- Hypothyroidism and hyperthyroidism
- Use, effects and complications of thyroid hormones or anti-thyroid drugs
- Hypercalcaemia and hypocalcaemia

#### Management of complications
- Postoperative haemorrhage following head and neck and ear nose and throat surgery:
  - Post tonsillectomy
  - Post thyroidectomy
- Airway fire
- Stridor and airway obstruction

### Dental/maxillofacial surgery

#### Specific knowledge and skills
- Innervation of the teeth and regional blocks used for dental procedures (Note that performance of the regional blocks is not required)
- Types of facial, maxillary and mandibular fractures and their surgical management
- Indications for and method of managing the airway during maxillo-facial surgery with a nasal endotracheal tube

#### Surgeries that candidate should be familiar with
- Surgical fixation of facial, maxillary and mandibular fractures
- Maxillary and mandibular osteotomies
- Drainage of dental abscesses and Ludwig's angina

#### Common or important comorbidities found in patients presenting with these surgeries
- Intellectual impairment
- Disorders of haemostasis
- Dental sepsis, dental abscesses and Ludwig's angina

### Electro-convulsive therapy

#### Specific knowledge and skills
- Indications and evidence for the use of electro-convulsive therapy
- Physiological response and management of response to electro-convulsive therapy
- Contra-indications for electro-convulsive therapy

---

## S13 Ophthalmic Procedures
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.5 OPHTHALMOLOGY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S13 Ophthalmic Procedures";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Specific knowledge and skills
- Anatomy of the eye and the contents of the orbit with reference to the performance of regional eye blocks and their complications
- Determinants of ocular perfusion and intra-ocular pressure
- Methods used to decrease or prevent a rise in intra-ocular pressure
- Eye reflexes (oculo-cardiac, oculo-respiratory, oculo-emetic)
- Compare different regional blocks for eye: subtenon block, peri-bulbar block and retrobulbar block; in terms of risks and benefits (not including the technique of performing the block itself)

### Considerations and surgical requirements of specific ophthalmic procedures
- Cataracts
- Glaucoma
- Retinal detachment
- Penetrating eye injury
- Enucleation for infection or tumour
- Examination under anaesthesia
- Strabismus
- Blocked nasolacrimal duct
- Extraocular procedures
- Penetrating keratoplasty (corneal transplant)
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#7. CORNEAL TRANSPLANTATION]] -->
> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Considerations and surgical requirements of specific ophthalmic procedures";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

- Miscellaneous/others (e.g. oculoplastics, pterygium excision, etc.)

### Common physiological and pathophysiological considerations
In patients presenting for these surgeries:
- Geriatric
- Paediatrics
- Cognitive impairment
- Comorbidities requiring anticoagulation

### Anaesthetic considerations and management
- Airway management
- Perioperative use of drugs by eye surgeons; in particular topical local anaesthetic agents, vasoconstrictors, mydriatics, miotics, and intraocular pressure-reducing agents
- Eye reflexes and their management during eye procedures
- Emergency eye surgery and in particular the patient with a penetrating eye injury
- Intra-ocular injection of gas
- Influence of patient factors including:
  - Anticoagulation status
  - Ability to lie flat
  - Ability to cooperate
  - Axial length of the globe
- Choice of patients for sedation and sedation techniques for eye procedures
- Conversion of regional to general anaesthesia during an eye procedure
- Use of Laser

---

## S14 Ambulatory Surgery
<!-- covered-by: [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA#7. OUTCOMES AND PROGNOSIS]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES#2.2. AMBULATORY LAPAROSCOPIC SURGERY]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S14 Ambulatory Surgery";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Benefits of Ambulatory surgery

### Outcome measures of ambulatory surgery
(e.g. delayed discharge, unanticipated readmissions)

### Considerations for procedures in an ambulatory setting

#### Patient selection
- Age
- Implication of ASA status
- Specific medical conditions: Impaired organ reserves, Obesity, Obstructive sleep apnoea etc
- Transport and Social Support

#### Selection of type of surgery

#### Preoperative management
- Fasting guidelines
- Implications of upper respiratory tract infection
- Anxiety reduction (e.g. non pharmacological and pharmacological premedications, etc.)

#### Intraoperative considerations and management
- Wake up time versus discharge time
- Implications of the choice of anaesthetic agents and techniques

#### Perioperative pain management plan
- Multimodal analgesia
- Role of regional anaesthesia

#### Other considerations
- Perioperative prevention & management of postoperative nausea and vomiting
- Discharge criteria
- Postoperative follow-up, including continuous nerve blocks
- Management of cancellations and implications

---

## S15 Non-Operating Room Anaesthesia (Remote)
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY#4. ENDOVASCULAR INTERVENTIONS]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#4. SPECIALIZED ENT PROCEDURES]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "S15 Non-Operating Room Anaesthesia (Remote)";
> let results = [];
>
> // Get all pages in ANAESTHESIA CONTENT folder
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p =>
>     p.file.outlinks &&
>     p.file.outlinks.some(link => link.path.includes("MMed_Anaesthesiology_Part_B_Syllabus"))
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
>             if (line.includes("MMed_Anaesthesiology_Part_B_Syllabus") && line.includes(targetSection)) {
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

### Procedures outside the operating theatre within a hospital setting

#### Considerations for anaesthesia/sedation for adults and children
For procedures outside the operating theatre, but within a hospital setting, either diagnostic or therapeutic for both elective and emergency procedures, including but not exclusively in the following settings: X-Ray, CT scan, Angiography, MRI scan, Radiotherapy

#### Requirements for safe anaesthesia/sedation
- Physical
- Equipment: Awareness of equipment limitations (e.g. DDI bed not being able to tilt, access to head obstructed by head holder/C-arm)
- Monitors
- Staff
- Patient selection

#### Unique safety issues with
- Radiation suite
- Radiotherapy
- MRI suite

#### Other considerations
- Requirements for provision of safe post-anaesthetic care for patients in the out of theatre environment
- Discharge criteria and follow-up

*Note: Refer to Cardiac surgery and interventional cardiology, Vascular Surgery and Interventional radiology and Neurosurgery and Neuroradiology*

### Office-based sedation

#### Considerations for office-based sedation
- Advantages & Disadvantages
- Patient selection
- Surgeon selection (accreditation, etc.)
- Physical requirements and Equipment
- Staff
- Organization of staff and environment
- Safety considerations
- Anaesthetic techniques/Patient Management
- Discharge criteria
