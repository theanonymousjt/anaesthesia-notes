# Prompt Engineering for Anaesthesia NGEMR

## Project Overview

**Goal:** Integrate Claude into NGEMR to generate comprehensive pre-anaesthetic evaluation notes by extracting, synthesizing, and inferring from multiple patient documents.

**Core Challenges:**
1. Context preservation across large document sets
2. Targeted fact-finding from scattered sources
3. Risk calculations and clinical inference
4. Zero-miss requirement for critical red flags (allergies, difficult airway, anticoagulation)
5. Producing succinct yet comprehensive output

---

## Architecture Options

### Option 1: Monolithic Single-Pass
A single prompt attempts to extract all information and generate the note in one pass.

**Pros:**
- Simple implementation
- No orchestration overhead
- Single API call

**Cons:**
- Context window limitations with large document sets
- High risk of missing critical information
- Difficult to validate individual extractions
- No redundancy for safety-critical items
- Hard to debug failures

**Verdict:** ❌ Not recommended for clinical use

---

### Option 2: Sequential Domain-Specific Agents (Recommended)

A pipeline of specialized agents, each focused on specific clinical domains.

```
┌─────────────────────────────────────────────────────────────────┐
│                    DOCUMENT INTAKE                               │
│         (All available NGEMR records for patient)                │
└─────────────────────────┬───────────────────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────────────┐
│              AGENT 0: RED FLAG EXTRACTION (FIRST)                │
│  • Drug allergies (with reaction type)                           │
│  • Latex allergy                                                 │
│  • Previous difficult airway                                     │
│  • MH susceptibility                                             │
│  • Anticoagulation status                                        │
│  • CIEDs (pacemaker/ICD)                                         │
│  • Recent coronary stents                                        │
│  OUTPUT: Structured red flag summary with source citations       │
└─────────────────────────┬───────────────────────────────────────┘
                          │
          ┌───────────────┼───────────────┐
          ▼               ▼               ▼
┌─────────────┐   ┌─────────────┐   ┌─────────────┐
│  AGENT 1    │   │  AGENT 2    │   │  AGENT 3    │
│ Demographics│   │ Medications │   │  Surgical   │
│ & Baseline  │   │ & Allergies │   │   Info      │
│             │   │ (detailed)  │   │             │
└──────┬──────┘   └──────┬──────┘   └──────┬──────┘
       │                 │                 │
       └────────────┬────┴─────────────────┘
                    ▼
┌─────────────────────────────────────────────────────────────────┐
│                    SYSTEMS-BASED AGENTS                          │
├─────────────┬─────────────┬─────────────┬─────────────┬─────────┤
│  AGENT 4    │  AGENT 5    │  AGENT 6    │  AGENT 7    │AGENT 8  │
│  Airway     │  Cardio     │  Pulmonary  │  Neuro/     │ Renal/  │
│  Assessment │  vascular   │             │  Endocrine  │ Hepatic │
└──────┬──────┴──────┬──────┴──────┬──────┴──────┬──────┴────┬────┘
       │             │             │             │           │
       └─────────────┴─────────────┼─────────────┴───────────┘
                                   ▼
┌─────────────────────────────────────────────────────────────────┐
│              AGENT 9: INVESTIGATIONS & LABS                      │
│  • Recent bloods (FBC, U&E, LFT, Coags, Group & Screen)         │
│  • ECG findings                                                  │
│  • Imaging (CXR, Echo if available)                             │
│  • Flag missing essential investigations                         │
└─────────────────────────┬───────────────────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────────────┐
│              AGENT 10: RISK CALCULATION                          │
│  • ASA Physical Status (with justification)                      │
│  • Revised Cardiac Risk Index (RCRI)                            │
│  • Surgical risk category (ESC 2022)                            │
│  • OSA risk (STOP-BANG if applicable)                           │
│  • Bleeding risk assessment                                      │
└─────────────────────────┬───────────────────────────────────────┘
                          │
                          ▼
┌─────────────────────────────────────────────────────────────────┐
│              AGENT 11: SYNTHESIS & NOTE GENERATION               │
│  • Compile all agent outputs                                     │
│  • Cross-verify red flags appear in final note                   │
│  • Generate structured pre-anaesthetic evaluation                │
│  • Propose anaesthetic plan considerations                       │
│  • Flag uncertainties requiring clarification                    │
└─────────────────────────────────────────────────────────────────┘
```

**Pros:**
- Domain expertise in each agent's prompt
- Context preserved within each extraction task
- Red flag agent runs first → hard stop if allergies missing
- Easier debugging (which agent failed?)
- Natural parallelization possible for agents 1-8

**Cons:**
- More complex orchestration
- Multiple API calls (cost/latency)
- Need to handle inter-agent data passing

**Verdict:** ✅ Recommended for clinical safety

---

### Option 3: Parallel Extraction with Redundant Safety Checks

All domain agents run in parallel with dedicated redundancy for critical items.

```
                    ┌─────────────────────┐
                    │   DOCUMENT POOL     │
                    └──────────┬──────────┘
                               │
       ┌───────────────────────┼───────────────────────┐
       │                       │                       │
       ▼                       ▼                       ▼
┌──────────────┐       ┌──────────────┐       ┌──────────────┐
│ RED FLAG     │       │ SYSTEMS      │       │ ADMIN/       │
│ EXTRACTOR A  │       │ EXTRACTORS   │       │ PROCEDURAL   │
│              │       │ (parallel)   │       │              │
└──────┬───────┘       └──────┬───────┘       └──────┬───────┘
       │                      │                      │
       │               ┌──────┴──────┐               │
       │               │             │               │
       ▼               ▼             ▼               ▼
┌──────────────┐ ┌───────────┐ ┌───────────┐ ┌──────────────┐

│ RED FLAG     │ │  CVS      │ │  Resp     │ │ Demographics │
│ EXTRACTOR B  │ │  Agent    │ │  Agent    │ │    Agent     │
│ (redundant)  │ │           │ │           │ │              │
└──────┬───────┘ └─────┬─────┘ └─────┬─────┘ └──────┬───────┘
       │               │             │               │
       └───────────────┴─────────────┴───────────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   FUSION AGENT      │
                    │ • Resolve conflicts │
                    │ • Verify red flags  │
                    │   match A and B     │
                    │ • Generate note     │
                    └─────────────────────┘
```

**Key Feature:** Two independent agents extract red flags. If they disagree → human review required.

**Pros:**
- Fastest execution (parallel)
- Built-in redundancy for safety-critical items
- Conflict detection = quality check

**Cons:**
- Most expensive (more API calls)
- Conflict resolution logic needed
- May have contradictory extractions

**Verdict:** ✅ Good for high-throughput with safety requirements

---

## Recommended Architecture: Hybrid Sequential-Parallel

Combine the safety of sequential red flag checking with parallel efficiency:

```
PHASE 1: Red Flag Extraction (BLOCKING)
    │
    ├── Must complete before proceeding
    ├── Hard stop if allergy field empty/uncertain
    └── Output: Verified critical safety data

PHASE 2: Parallel Domain Extraction
    │
    ├── Demographics, Surgical, Medications
    ├── CVS, Respiratory, Airway
    ├── Neuro, Endocrine, Renal, Hepatic
    └── Labs & Investigations

PHASE 3: Risk Calculation (requires Phase 2)
    │
    └── ASA, RCRI, Surgical Risk, STOP-BANG

PHASE 4: Synthesis & Note Generation
    │
    ├── Compile all outputs
    ├── Cross-reference red flags
    └── Generate final note with confidence flags
```

---

## Red Flag Extraction Strategy

### Must-Not-Miss Items (Zero Tolerance)

| Category | Items | Consequence if Missed |
|----------|-------|----------------------|
| **Allergies** | Drug allergies, latex, contrast | Anaphylaxis, death |
| **Airway** | Previous difficult intubation, MH | CICV, death |
| **Cardiac** | Recent MI (<3mo), unstable angina, severe AS | Perioperative MI, death |
| **Devices** | Pacemaker, ICD, cochlear implant | Device malfunction |
| **Bleeding** | Anticoagulants, antiplatelets, coagulopathy | Hemorrhage |
| **Stents** | DES <12mo, BMS <1mo | Stent thrombosis |

### Prompt Strategy for Red Flags

```markdown
## RED FLAG EXTRACTION PROMPT

You are a senior anaesthesia registrar reviewing patient records before a pre-operative assessment.

CRITICAL INSTRUCTION: You must extract ALL of the following with ZERO TOLERANCE for omission:

### 1. DRUG ALLERGIES
- Extract EVERY documented drug allergy
- Include: drug name, reaction type, severity, date if available
- If NO allergies documented, explicitly state "NKDA documented in [source]"
- If allergy status UNCLEAR, flag as "⚠️ ALLERGY STATUS REQUIRES VERIFICATION"

### 2. PREVIOUS ANAESTHETIC HISTORY
- Any documented difficult airway (grade of view, technique used)
- Malignant hyperthermia history (personal or family)
- Previous anaesthetic complications
- PONV history

### 3. CARDIAC RED FLAGS
- MI within last 3 months
- Unstable angina
- Decompensated heart failure
- Severe valvular disease (especially AS)
- Recent coronary stents (type and date)

### 4. IMPLANTABLE DEVICES
- Pacemaker (type, indication, pacing mode)
- ICD
- Other implants (cochlear, spinal cord stimulator)

### 5. ANTICOAGULATION STATUS
- Current anticoagulants (drug, dose, last taken)
- Antiplatelets (including dual antiplatelet therapy)
- Indication for anticoagulation
- Bridging requirements

OUTPUT FORMAT:
Return a structured JSON with confidence scores (0-1) for each field.
If confidence < 0.8, flag for human verification.
```

---

## Risk Calculation Agent

### Calculations Required

1. **ASA Physical Status** (I-VI, with E modifier)
2. **Revised Cardiac Risk Index (RCRI)**
   - High-risk surgery
   - History of IHD
   - History of CHF
   - History of CVA/TIA
   - Insulin-dependent DM
   - Preop creatinine >177 μmol/L
3. **Surgical Risk Category** (ESC 2022: Low/Intermediate/High)
4. **STOP-BANG** (if OSA suspected)
5. **Bleeding Risk** (procedure-specific)
6. **Functional Capacity** (METs)

### Risk Calculation Prompt

```markdown
## RISK CALCULATION PROMPT

Given the extracted patient data, calculate the following risk scores:

### ASA PHYSICAL STATUS
Based on the 2020 ASA classification with examples.
Provide: Score (I-VI) + E if emergency + justification

### RCRI (Revised Cardiac Risk Index)
Count applicable criteria (0-6):
□ High-risk surgery (intraperitoneal, intrathoracic, suprainguinal vascular)
□ History of ischemic heart disease
□ History of congestive heart failure
□ History of cerebrovascular disease
□ Preoperative insulin treatment
□ Preoperative creatinine >2.0 mg/dL (177 μmol/L)

Score: [X]/6
Risk of MACE: [interpret based on score]

### ESC 2022 SURGICAL RISK CATEGORY
Based on procedure type, assign: Low (<1%) / Intermediate (1-5%) / High (>5%)

### FUNCTIONAL CAPACITY
Estimated METs based on documented exercise tolerance:
- Can climb 2 flights of stairs = ≥4 METs
- Can walk 4 blocks = ≥4 METs
If unable to assess → flag as "unknown functional capacity"

OUTPUT: Structured risk summary with all scores and interpretations
```

---

## Final Note Structure

The synthesis agent should produce a note following this structure:

```
PRE-ANAESTHETIC EVALUATION

Patient: [Name] | Age: [X] | Sex: [M/F] | Weight: [X]kg | Height: [X]cm
MRN: [X] | Eval Date: [X] | Evaluator: AI-assisted (verified by Dr. [X])

PROCEDURE: [Planned surgery]
SURGEON: [Name]
PROPOSED DATE: [X]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

⚠️ CRITICAL ALERTS
• Allergies: [List with reaction types]
• Difficult airway: [Yes/No - details]
• Anticoagulation: [Status]
• Cardiac devices: [List]
• Other red flags: [List]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MEDICAL HISTORY
[Concise problem list with relevant details]

SURGICAL HISTORY
[Relevant previous surgeries]

MEDICATIONS
[Current medications with doses]

ANAESTHETIC HISTORY
[Previous anaesthetics, any complications]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

SYSTEMS REVIEW
CVS: [Summary]
RESP: [Summary]
AIRWAY: [Mallampati, predictors of difficulty]
NEURO: [Summary]
ENDO: [Summary including fasting status for DM]
RENAL: [Summary]
HAEM: [Summary]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

INVESTIGATIONS
[Recent relevant results with dates]
[Flag any missing essential investigations]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

RISK ASSESSMENT
ASA: [Score + justification]
RCRI: [Score/6] → [% MACE risk]
Surgical Risk: [Low/Intermediate/High]
Functional Capacity: [X METs / Unable to assess]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

ANAESTHETIC CONSIDERATIONS
[Key points for anaesthetic planning]

PLAN
[Proposed anaesthetic approach]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

⚠️ ITEMS REQUIRING VERIFICATION
[List any uncertainties or missing information]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

AI Confidence Score: [X]%
Sources reviewed: [List of NGEMR documents accessed]
```

---

## Implementation Considerations

### 1. Context Management
- Each agent receives only relevant document sections
- Use document chunking with overlap for large records
- Maintain source citations for traceability

### 2. Validation Layer
- Red flag outputs must be human-verified before proceeding
- Risk calculations should show working
- Uncertain extractions flagged explicitly

### 3. Error Handling
- If allergy extraction fails → HARD STOP
- If any agent returns low confidence → flag for review
- Missing data explicitly stated, not assumed absent

### 4. Audit Trail
- Log all agent inputs/outputs
- Record confidence scores
- Timestamp all extractions

---

## Next Steps

1. [ ] Define exact NGEMR document types available as input
2. [ ] Create sample prompts for each agent
3. [ ] Test on de-identified cases
4. [ ] Define validation workflow
5. [ ] Plan human-in-the-loop integration
6. [ ] Consider PDPA/data governance requirements

---

*Last updated: January 2026*
*Reference: 5.1. PREOPERATIVE ASSESSMENT.md*
