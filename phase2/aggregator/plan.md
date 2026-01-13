# Plan: Aggregate Phase 1 Research Findings

## Agent
- Name: aggregator
- Role: aggregator
- Model: MiniMax-M2.1 (thinking enabled)
- Tools: read, write, bash

## Objective
Synthesize findings from all 6 Phase 1 scouts into a coherent, structured analysis of Earth's magnetic field research.

## Scope
### In Scope
- Reading all Phase 1 outputs
- Identifying consensus across scouts
- Identifying contradictions or debates
- Organizing by theme
- Flagging key uncertainties
- Creating structured synthesis

### Out of Scope
- New research (already done by scouts)
- Final user-facing answer (Phase 3)
- Opinions beyond source synthesis

## Input Files
Read these files from Phase 1 scouts:
- ../../phase1/scout-pole-reversal/output/findings.md
- ../../phase1/scout-field-strength/output/findings.md
- ../../phase1/scout-south-atlantic-anomaly/output/findings.md
- ../../phase1/scout-recent-papers/output/findings.md
- ../../phase1/scout-prediction-models/output/findings.md
- ../../phase1/scout-historical-data/output/findings.md

## Success Criteria
- [ ] Read all 6 scout outputs
- [ ] Identified consensus points
- [ ] Identified contradictions/debates
- [ ] Organized thematically
- [ ] Created output/synthesis.md
- [ ] Created output/key-questions.md

## Steps

### STEP-01: Read All Scout Outputs
**Objective**: Ingest all Phase 1 findings
**Target**: All 6 findings.md files
**Actions**:
1. Read each scout's output/findings.md
2. Note key points from each
3. Track source quality per scout
**Success criteria**: All 6 outputs ingested
**Output**: Summary notes in log.md

### STEP-02: Identify Consensus
**Objective**: Find areas of agreement
**Target**: Cross-scout analysis
**Actions**:
1. What do multiple scouts agree on?
2. What's the mainstream scientific view?
3. What's well-established vs uncertain?
**Success criteria**: Clear consensus points listed
**Output**: Consensus section

### STEP-03: Identify Debates/Contradictions
**Objective**: Find areas of disagreement
**Target**: Cross-scout comparison
**Actions**:
1. Any contradictions between scouts?
2. Any ongoing scientific debates?
3. Any surprising or controversial findings?
**Success criteria**: Debates clearly articulated
**Output**: Debates section

### STEP-04: Thematic Organization
**Objective**: Organize by theme, not by scout
**Target**: All findings
**Actions**:
1. Group findings by theme:
   - Current state of the field
   - Rate of change
   - Reversal likelihood
   - Predictions/forecasts
   - Unknowns and uncertainties
**Success criteria**: Thematic structure
**Output**: Organized synthesis

### STEP-05: Final Output
**Objective**: Compile deliverables
**Actions**:
1. Write output/synthesis.md - full thematic synthesis
2. Write output/key-questions.md - unanswered questions
3. Write output/summary.txt - one paragraph overview
**Output**: output/synthesis.md, output/key-questions.md, output/summary.txt

## Logging Requirements
Create and maintain append-only `log.md`. NEVER edit previous entries.
