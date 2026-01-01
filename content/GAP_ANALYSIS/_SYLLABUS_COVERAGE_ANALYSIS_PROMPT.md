# Comprehensive Syllabus Coverage Analysis

## Purpose
Systematically verify that EVERY syllabus learning objective has corresponding:
1. Reference notes content (adequate depth)
2. Anki flashcards (sufficient coverage)

This is the TRUE gap analysis - comparing syllabus requirements line-by-line against existing content.

---

## Session Prompt

```
You are performing a COMPREHENSIVE SYLLABUS COVERAGE ANALYSIS for MMed Anaesthesiology.

## Your Mission
Extract EVERY learning objective from the syllabus and verify each has:
- Corresponding reference notes (with adequate depth)
- Corresponding Anki flashcards (with sufficient coverage)

This is NOT about checking if decks exist or if cards have proper format.
This IS about verifying each syllabus objective is actually covered.

## Read These Files First
1. Full methodology: /Users/jordan/Library/CloudStorage/GoogleDrive-theanonymousjt@gmail.com/My Drive/Medicine/Anaesthesia/flashcard_creation_project/GAP_ANALYSIS_PROMPT.md
2. Previous analysis: /Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/GAP_ANALYSIS/_GAP_ANALYSIS_TRACKER.md

## Syllabus Files (MUST preprocess first)
- Part A: /Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/mmed_anaes_part_a_syllabus.md
- Part B: /Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/mmed_anaes_part_b_syllabus.md
- Part C: /Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/mmed_anaes_part_c_syllabus.md

## Reference Notes Base Path
/Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/

## Anki Decks Base Path
/Users/jordan/Documents/MEDICINE/ANKI/ANAESTHESIA/ANAESTHESIA_PROCESSED/

## Workflow

### STEP 1: Preprocess Syllabus Files
Strip dataview blocks and wiki-links to save tokens:
```bash
# Part A
sed '/> \[!info\]- 📎 Linked Mentions/,/^> ```$/d' "/Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/mmed_anaes_part_a_syllabus.md" | sed 's/\[\[mmed_anaes_part_[abc]_syllabus[^]]*\]\]//g' | sed 's/```dataviewjs/DATAVIEW_BLOCK_START/g' | sed '/DATAVIEW_BLOCK_START/,/```/d' > /tmp/syllabus_a_cleaned.md

# Part B
sed '/> \[!info\]- 📎 Linked Mentions/,/^> ```$/d' "/Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/mmed_anaes_part_b_syllabus.md" | sed 's/\[\[mmed_anaes_part_[abc]_syllabus[^]]*\]\]//g' | sed 's/```dataviewjs/DATAVIEW_BLOCK_START/g' | sed '/DATAVIEW_BLOCK_START/,/```/d' > /tmp/syllabus_b_cleaned.md

# Part C
sed '/> \[!info\]- 📎 Linked Mentions/,/^> ```$/d' "/Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/mmed_anaes_part_c_syllabus.md" | sed 's/\[\[mmed_anaes_part_[abc]_syllabus[^]]*\]\]//g' | sed 's/```dataviewjs/DATAVIEW_BLOCK_START/g' | sed '/DATAVIEW_BLOCK_START/,/```/d' > /tmp/syllabus_c_cleaned.md
```

### STEP 2: Extract ALL Learning Objectives
Read each preprocessed syllabus and extract EVERY bulleted learning objective.

**Part A Structure:**
- Section 1: Physics & Equipment (~15%)
- Section 2: Physiology (~32%)
- Section 3: Pharmacology (~33%)
- Section 4: Clinical Measurement (~20%)

**Part B Structure:**
- C1-C6: Core Clinical Competencies
- S1-S15: Specialty Areas

**Part C Structure:**
- 6 ACGME-I Competencies
- Clinical Governance
- Systems-Based Practice

For each objective, record:
- Objective ID (e.g., A:2.1.3, B:S12.4, C:6.1.2)
- Full objective text
- Key searchable terms

### STEP 3: Verify Coverage for Each Objective

For EACH extracted objective:

1. **Search Reference Notes:**
   ```bash
   # Search for topic in relevant reference notes
   grep -n "search_term" "/path/to/reference_notes.md" | head -10
   ```
   - Record if content found
   - Assess depth: Comprehensive (>500 words) / Adequate (200-500) / Sparse (<200) / Missing

2. **Search Anki Cards:**
   ```bash
   # Search card filenames
   ls "/path/to/anki_deck/" | grep -i "search_term"

   # Search card content
   grep -l "search_term" "/path/to/anki_deck/"*.md 2>/dev/null | wc -l
   ```
   - Record card count
   - Assess: Sufficient (≥3 cards) / Insufficient (1-2) / Missing (0)

3. **Classify Status:**
   - ✅ **COMPLETE**: Comprehensive notes + sufficient cards
   - ⚠️ **PARTIAL**: Notes exist but sparse, OR cards exist but few
   - ❌ **MISSING**: No notes OR no cards

### STEP 4: Create Coverage Matrix

Output file: `/Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/GAP_ANALYSIS/_SYLLABUS_COVERAGE_MATRIX.md`

```markdown
# Syllabus Coverage Matrix
Generated: [DATE]

## Executive Summary
| Part | Total Objectives | Complete | Partial | Missing | Coverage % |
|------|------------------|----------|---------|---------|------------|
| Part A | XXX | XXX | XXX | XXX | XX% |
| Part B | XXX | XXX | XXX | XXX | XX% |
| Part C | XXX | XXX | XXX | XXX | XX% |
| **TOTAL** | **XXX** | **XXX** | **XXX** | **XXX** | **XX%** |

## Part A: Detailed Coverage

### Section 1: Physics & Equipment
| ID | Objective | Notes Status | Cards Status | Overall |
|----|-----------|--------------|--------------|---------|
| A:1.1.1 | SI units | ✅ Comprehensive | ✅ 4 cards | ✅ |
| A:1.1.2 | Gas laws | ✅ Comprehensive | ✅ 9 cards | ✅ |
[... continue for ALL Part A objectives]

### Section 2: Physiology
[... continue]

### Section 3: Pharmacology
[... continue]

### Section 4: Clinical Measurement
[... continue]

## Part B: Detailed Coverage

### C1-C6: Core Competencies
[... continue]

### S1-S15: Specialty Areas
[... continue]

## Part C: Detailed Coverage
[... continue]

## GAP SUMMARY

### Missing Objectives (Highest Priority)
| ID | Objective | Notes Gap | Cards Gap | Action |
|----|-----------|-----------|-----------|--------|
| A:2.3.7 | Topic | Missing | Missing | Create notes + cards |
[list all MISSING objectives]

### Partial Coverage (Medium Priority)
| ID | Objective | Notes Gap | Cards Gap | Action |
|----|-----------|-----------|-----------|--------|
| A:2.1.5 | Topic | Sparse | 2 cards | Expand notes, add cards |
[list all PARTIAL objectives]

### Complete (No Action)
[count by section]
```

### STEP 5: Token Management

**Check tokens after each syllabus section:**
- >70k remaining: Continue to next section
- 50-70k remaining: Complete current section, then stop
- <50k remaining: Stop immediately, generate continuation prompt

**When stopping, generate:**
```markdown
## Continuation Prompt

Resume SYLLABUS COVERAGE ANALYSIS.

## Previous Session
- Date: [DATE]
- Completed: Part A Sections 1-2, Part B C1-C3
- Remaining: Part A Sections 3-4, Part B C4-C6, S1-S15, Part C

## Resume From
Next section: [SECTION NAME]

## Files
- Methodology: /Users/jordan/Library/CloudStorage/GoogleDrive-theanonymousjt@gmail.com/My Drive/Medicine/Anaesthesia/flashcard_creation_project/GAP_ANALYSIS_PROMPT.md
- Coverage Matrix: /Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/GAP_ANALYSIS/_SYLLABUS_COVERAGE_MATRIX.md
- Syllabus files: [paths]

Continue from [specific section] and complete the coverage matrix.
```

## Expected Output

1. **_SYLLABUS_COVERAGE_MATRIX.md** - Complete line-by-line verification
2. Updated **_GAP_ANALYSIS_TRACKER.md** - With syllabus coverage results
3. **Priority Action List** - Ranked gaps to address

## Key Principles

1. **Be EXHAUSTIVE** - Extract EVERY objective, don't skip any
2. **Be RIGOROUS** - Actually search for content, don't assume
3. **Be SPECIFIC** - Record exact matches, line numbers, card counts
4. **Prioritize by exam weight** - Part A topics have higher weight
5. **Track progress** - This may take multiple sessions

## Start

Begin by preprocessing the syllabus files, then systematically extract and verify objectives starting with Part A Section 1.
```

---

## Quick Start Command

Copy this to start the analysis:

```
Perform COMPREHENSIVE SYLLABUS COVERAGE ANALYSIS.

Read methodology first:
/Users/jordan/Library/CloudStorage/GoogleDrive-theanonymousjt@gmail.com/My Drive/Medicine/Anaesthesia/flashcard_creation_project/GAP_ANALYSIS_PROMPT.md

Then:
1. Preprocess all 3 syllabus files to /tmp/
2. Extract ALL learning objectives from Part A
3. For EACH objective, verify:
   - Reference notes exist (grep search)
   - Anki cards exist (ls + grep search)
4. Create coverage matrix at:
   /Users/jordan/Documents/MEDICINE/ANAESTHESIA CONTENT/GAP_ANALYSIS/_SYLLABUS_COVERAGE_MATRIX.md
5. Track progress, generate continuation prompt when needed

Start with Part A Section 1: Physics & Equipment.
```
