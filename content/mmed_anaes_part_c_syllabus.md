# Master of Medicine (Anaesthesiology) Part C Examination Syllabus

**Division of Graduate Medical Studies**  
**Yong Loo Lin School of Medicine, NUS**

## Overview

The Master of Medicine (Anaesthesiology) Part C Examination is the final part to the Master of Medicine (Anaesthesiology) Examination. The 3 parts of the Examination serve to verify that candidate has achieved the 6 ACGME-I core competencies of the Residency program.

To match training with assessment, this syllabus has been written in accordance with the 6 core competencies.

---

## 1. Medical Knowledge
<!-- covered-by: [[1. BASIC SCIENCES/1.1. PHYSICS & MATHEMATICS]], [[1. BASIC SCIENCES/1.2. STATISTICS]], [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES]], [[3. PHARMACOLOGY/3.13. LESS COMMONLY ENCOUNTERED DRUGS]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.1. NEURAXIAL TECHNIQUES]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.3. ACUTE PAIN]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.4. CHRONIC PAIN]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#1. INTRODUCTION AND GENERAL PRINCIPLES]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#3. ANESTHETIC TECHNIQUE SELECTION]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#4. SPINE SURGERY]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#8. SPECIAL CONSIDERATIONS]], [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]], [[8. CLINICAL ANAESTHESIA/8.4 LIVER SURGERY]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#1. INTRODUCTION TO TRAUMA ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#3. PULMONARY MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#4. CARDIOVASCULAR MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#5. NEUROLOGIC MANAGEMENT]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#6. RESUSCITATION STRATEGIES]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#12. SPECIAL POPULATIONS]], [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#1. AIRWAY EVALUATION AND ASSESSMENT]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#2. PEDIATRIC ENT ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#3. PEDIATRIC AIRWAY EMERGENCIES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#4. SPECIALIZED ENT PROCEDURES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#5. ADULT AND COMPLEX ENT CONDITIONS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "1. Medical Knowledge";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_c_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_c_syllabus") && line.includes(targetSection)) {
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

The candidate should demonstrate:

### 1.1 Investigative and Analytical Approach
An investigative and analytical approach to clinical problem solving and knowledge acquisition, and an ability to apply medical knowledge to clinical situation:
- Through the clinical case viva discussion in the part C examination covering the topics in Part A and Part B examination but in greater depth.

### 1.2 Ability to Teach Others
- Through participation of teaching activities as documented on the Logbook (verified during the logbook review).

---

## 2. Patient Care and Procedural Skills
<!-- covered-by: [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#electrical-shock-and-safety]], [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#operating-room-fires]], [[6. SPECIAL POPULATIONS/6.2. PEDIATRIC]], [[6. SPECIAL POPULATIONS/6.4. BARIATRIC ANAESTHESIA]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.1. NEURAXIAL TECHNIQUES]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.2. PERIPHERAL NERVE BLOCKS]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.3. ACUTE PAIN]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.4. CHRONIC PAIN]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#1. INTRODUCTION AND GENERAL PRINCIPLES]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#2. PREOPERATIVE ASSESSMENT]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#5. UPPER EXTREMITY SURGERY]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#6. LOWER EXTREMITY SURGERY]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#7. PEDIATRIC ORTHOPEDIC ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]], [[8. CLINICAL ANAESTHESIA/8.4 LIVER SURGERY]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#1. INTRODUCTION TO TRAUMA ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#2. AIRWAY MANAGEMENT IN TRAUMA]], [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY#3. CEREBROVASCULAR AND CAROTID PROCEDURES]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#1. AIRWAY EVALUATION AND ASSESSMENT]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#2. PEDIATRIC ENT ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#3. PEDIATRIC AIRWAY EMERGENCIES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#4. SPECIALIZED ENT PROCEDURES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#5. ADULT AND COMPLEX ENT CONDITIONS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "2. Patient Care and Procedural Skills";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_c_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_c_syllabus") && line.includes(targetSection)) {
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

The candidate should demonstrate:

### 2.1 Clinical Decision-Making and Procedures
Ability to gather essential and accurate information about the patient, make informed diagnostic and therapeutic decisions, prescribe, and perform essential medical procedures:
- Through the case logs and reflections documented on the Logbook (verified during the logbook review).
- Through the clinical case viva discussion in the part C examination covering topics Part A and B examination but in greater depth.

---

## 3. Professionalism
<!-- covered-by: [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.1. NEURAXIAL TECHNIQUES]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.3. ACUTE PAIN]], [[8. CLINICAL ANAESTHESIA/8.3 THORACIC SURGERY]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "3. Professionalism";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_c_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_c_syllabus") && line.includes(targetSection)) {
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

The candidate should demonstrate:

### 3.1 Professional Conduct and Accountability
Professional Conduct and Accountability, and Humanism and Cultural Proficiency during the case discussion in the part C examination by showing:

#### Medical Ethics
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#3.1. ETHICAL FRAMEWORK FOR DCD]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "Medical Ethics";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_c_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_c_syllabus") && line.includes(targetSection)) {
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

- An understanding and appreciation of the principles of medical ethics in accordance with the Singapore Medical Council's Ethical code and guidelines.

#### Legal Knowledge
- An awareness and knowledge of the laws and regulations that are relevant to the practice of anaesthesia and current legal guidelines such as providing medical advice, taking or giving consent and duty of care etc.

#### Cultural Sensitivity
- An awareness and appropriate sensitivity to the different ethnic groups and cultures present locally.

### 3.2 Personal and Professional Well-being
Ability to maintaining emotional, physical, and mental health, and pursuing continual personal and professional growth during the case discussion in the part C examination by showing:

#### Personal Health Strategies
- Strategies for personal health.

#### Workplace Safety
Knowledge necessary to ensure personal and staff safety at the workplace from hazards such as:

**Biohazards:**
- Infection Control and Prevention in contagious diseases (eg. COVID), and contact infections (E.g., EBOLA):
  - Personal protection – PPE, use, processes
  - Protecting others – process, training juniors, non-clinical areas
  - OT / ICU processes, e.g., air exchange vs washing out of aerosol, Aerosol generating procedures, high risk processes, preventive measures, organization.

**Other Hazards:**
- Electrical; Radiological; Fire, Explosions, LASERs etc
- Reference to Part A Syllabus Equipment and Safety and Part B Syllabus S15 Non-Operating Room Anaesthesia (Remote)

#### Mental Health Awareness
- Knowledge of the signs and symptoms of mental health issues and management strategies in self and colleagues, e.g., conditions such as depression, anxiety, substance abuse, burn-out.

#### Teaching Knowledge
- Understanding of basic concepts on adult learning and teaching.

---

## 4. Interpersonal and Communication Skills

The candidate should demonstrate:

### 4.1 Therapeutic Relationships and Team Leadership
Ability to create and sustain a therapeutic relationship with patients and families and work effectively as a member or leader of a health care team, through:

#### Assessment and Documentation
- Workplace-based assessment: reviewed and verified by the Clinical Competency Committee before recommendation for the Part C Exam.
- Documentation any administrative or leadership roles during residency in the Logbook.

#### Staff Management Strategies
Demonstrating ability to formulate strategies, during case discussion in the Part C exam, in managing staff with issues such as:

**Poor Performance or Behavior:**
- Poor performance or undesirable behaviour including impairment in colleague, disruptive behaviour, bully and harassment, sexual misconduct, adjustment or coping issues.

**Support and Counseling:**
- Support or counselling in stressful conditions such as critical incidents or adverse events support, mentoring and coaching.

**Mental Health Issues:**
- Mental issues such as depression, anxiety, substance abuse, burn-out etc.

---

## 5. Practice-Based Learning and Improvement
<!-- covered-by: [[1. BASIC SCIENCES/1.2. STATISTICS#research-design-and-methodology]], [[1. BASIC SCIENCES/1.2. STATISTICS#critical-appraisal-and-interpretation]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.1. NEURAXIAL TECHNIQUES]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.3. ACUTE PAIN]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.4. CHRONIC PAIN]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#9. COAGULATION MONITORING]], [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY#4. ENDOVASCULAR INTERVENTIONS]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "5. Practice-Based Learning and Improvement";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_c_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_c_syllabus") && line.includes(targetSection)) {
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

The candidate should demonstrate the ability to appraise and assimilate scientific evidence at the Paper Critique discussion in the Part C examination. They should be able to:

### 5.1 Biostatistical Knowledge
- Apply the biostatistical knowledge covered in the Part A syllabus

### 5.2 Critical Appraisal
- Critically appraise and apply evidence from published papers to daily clinical practice.

### 5.3 Research Design
- Discuss the stages involved in the design of a clinical study, including ethical or legal aspects of research (e.g., Human Biomedical Research Act).

### 5.4 Study Quality Assessment
- Discuss what constitute a good study design and identify study design flaws.
- Understand commonly used statistical tests in clinical studies and their application.

### 5.5 Clinical Application
- Discuss findings of presented paper and considerations for applying study findings in clinical practice.

---

## 6. Systems-Based Practice
<!-- covered-by: [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#electrical-power-systems]], [[1. BASIC SCIENCES/1.3. ELECTRICAL PRINCIPLES#electrical-safety-in-healthcare]], [[6. SPECIAL POPULATIONS/6.3. GERIATRIC#1.1. DEMOGRAPHICS AND ECONOMICS OF AGING]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.2. PERIPHERAL NERVE BLOCKS]], [[7. REGIONAL ANAESTHESIA & PAIN MANAGEMENT/7.3. ACUTE PAIN]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#6. LOWER EXTREMITY SURGERY]], [[8. CLINICAL ANAESTHESIA/8.1 ORTHOPAEDIC SURGERY#8. SPECIAL CONSIDERATIONS]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#1. INTRODUCTION TO TRAUMA ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.7 TRAUMA SURGERY#11. FUTURE DIRECTIONS]], [[8. CLINICAL ANAESTHESIA/8.9 ENDOVASCULAR SURGERY#5. COMPLICATIONS AND QUALITY IMPROVEMENT]], [[8. CLINICAL ANAESTHESIA/8.10 LAPAROSCOPIC AND ROBOTIC SURGERIES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#2. PEDIATRIC ENT ANESTHESIA]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#3. PEDIATRIC AIRWAY EMERGENCIES]], [[8. CLINICAL ANAESTHESIA/8.11 ENT SURGERY#4. SPECIALIZED ENT PROCEDURES]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "6. Systems-Based Practice";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_c_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_c_syllabus") && line.includes(targetSection)) {
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

### 6.1 Clinical Governance
<!-- covered-by: [[8. CLINICAL ANAESTHESIA/8.6 TRANSPLANT SURGERY#3. DONATION AFTER CIRCULATORY DETERMINATION OF DEATH (DCD)]] -->

> [!info]- 📎 Linked Mentions
> ```dataviewjs
> let targetSection = "6.1 Clinical Governance";
> let results = [];
> let pages = dv.pages('"ANAESTHESIA CONTENT"').where(p => p.file.outlinks && p.file.outlinks.some(link => link.path.includes("mmed_anaes_part_c_syllabus")));
> for (let page of pages) {
>     let file = app.vault.getAbstractFileByPath(page.file.path);
>     if (file) {
>         let content = await app.vault.read(file);
>         let lines = content.split('\n');
>         for (let i = 0; i < lines.length; i++) {
>             let line = lines[i];
>             if (line.includes("mmed_anaes_part_c_syllabus") && line.includes(targetSection)) {
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

As an advocate for quality patient care and optimal patient care systems, the candidate should demonstrate the knowledge and ability to apply principles of the 3 aspects of clinical governance during the case discussion in Part C exam:

#### A. Safety / Risk Management

**Based on Events or Cause:**

*Risk Identification:*
- System for events reporting: Sentinel events, Incident or near-misses; morbidity and mortality; complaints.

*Detection and Quantification:*
- Tools for detecting and quantifying events risks e.g., Healthcare Failure Mode & Effect Analysis

*Response & Mitigation:*
- Adverse events management
- Patient relations/ complaints management
- Documentations
- Root cause analysis
- Medicolegal management
- Follow-up remedial actions and system/ staff improvement

**Staff Management:**

*Training:*
- Clinical/Non-clinical (e.g., communications, adverse events management; staff self-management)
- Orientation of new staff
- Accreditation/ credentialing
- Registration

*Health (Including Mental Health):*
- Stress management
- Fatigue
- Burnout
- Second victim
- Counselling and psychological management
- (Cross reference to Personal and Staff wellbeing and Management)

*Fitness for Practice:*
- Time off work
- Health/mental health issues
- Physiological aging etc.
- Levels of supervision
- System and workflow issues that predispose to errors

**Service, Institutional, Healthcare System Level - Contingency Planning / Crisis Preparedness:**

*Service/Hospital Level:*
- Mass causality incidents

*System Wide Failures:*
- Malfunctioning electronic medical records
- Security breaches
- Terrorists attacks
- Cyber-attacks

*Hospital/Healthcare System/National Level:*
- Infection control (e.g. SARS; COVID etc)

*Communications:*
- Communications of plans

#### B. Effectiveness of Healthcare Service

**Quality Improvement Process:**
- Model for improvement
- Planning tools: process mapping; cause and effect [fishbone], affinity diagram, pareto chart
- Data collection methodology (qualitative, quantitative data)
- Interventions (change concepts, hierarchy of interventions)
- PDSA (Plan-Do-Study-Act)
- Measurement and analysis (types of measures, run charts)
- Performance improvement plan (spread and sustainability)
- Quality improvement outcomes and initiatives e.g., Value driven quality care/ outcomes initiatives

**Guidelines and Protocols:**
- Review of evidence
- Drawing of guidelines
- Implementations process

#### C. Patient and Family Communications, Experience, Feedback and Complaints

**Consent:**
- Consent taking and documentation

**Difficult Communications:**
- Difficult topics/ situations/ communications:
  - Poor prognosis
  - Poor outcome or unexpected adverse outcomes or complications
  - Risks and complaints mitigation

**Complaints and Feedback:**
- Complaints
- Communications/ Comments
- Request for waiver of charges etc.

**Support Systems:**
- Support system within the healthcare systems: patient relations, experience or liaison department

### 6.2 Singapore Healthcare Environment

To work effectively in current Singapore and world environment, the candidate should, during the case discussion at the Part C exams, show an understanding:

#### Legal and Regulatory Framework
- Of the laws and regulations that are relevant to the practice of anaesthesia and current legal guidelines such as providing medical advice, taking or giving consent and duty of care etc.

#### Healthcare Funding Model
Of the healthcare funding model in Singapore, including but not limited to:
- Various subsidies provided by MOH
- Medisave
- Medishield, life and integrated shield plans
- Medifund
- CareShield, Life/ ElderShield
- Private insurance
- Corporate Healthcare Benefits and Insurance

#### Socioeconomic Challenges
- Of the challenges of providing healthcare in the evolving socioeconomic and demographic landscape in Singapore.

#### Environmental Impact
Of the environmental impact of the anaesthetic practice including but not limited to:
- Environmental impact of various pharmacological agents
- Equipment
- Process of administering medical care
- Evolving solutions for these problems
