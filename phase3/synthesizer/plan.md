# Plan: Synthesize Final Answer

## Agent
- Name: synthesizer
- Role: synthesizer
- Model: MiniMax-M2.1 (thinking enabled)
- Tools: read, write

## Objective
Produce the final, cohesive answer to the user's core question: What is the current scientific understanding of Earth's magnetic field changes, and is there any credible evidence for significant events (like pole reversals) occurring in our lifetime?

## Scope
### In Scope
- Reading Phase 2 aggregator output
- Crafting clear, authoritative answer
- Addressing user's specific concerns
- Providing nuanced, sourced conclusions
- Being honest about uncertainties

### Out of Scope
- New research (already done)
- Re-aggregating Phase 1 (already done)

## Input Files
- ../phase2/aggregator/output/synthesis.md
- ../phase2/aggregator/output/key-questions.md

## Success Criteria
- [ ] Read aggregator outputs
- [ ] Directly answered user's question
- [ ] Provided nuanced, well-sourced conclusion
- [ ] Acknowledged uncertainties appropriately
- [ ] Created output/final-answer.md

## Steps

### STEP-01: Read Aggregator Output
**Objective**: Understand synthesized findings
**Target**: Phase 2 outputs
**Actions**:
1. Read synthesis.md thoroughly
2. Read key-questions.md
3. Identify core themes for answer
**Success criteria**: Full understanding of findings
**Output**: Notes in log.md

### STEP-02: Draft Answer
**Objective**: Create comprehensive answer
**Target**: User's core questions
**Actions**:
1. Address: Is the field deteriorating?
2. Address: Are pole reversals imminent?
3. Address: What does latest research say?
4. Address: What should we believe?
5. Provide clear, honest conclusions
**Success criteria**: All questions addressed
**Output**: Draft answer

### STEP-03: Polish and Finalize
**Objective**: Create final deliverable
**Actions**:
1. Write output/final-answer.md - the complete answer
2. Write output/executive-summary.md - 2-3 paragraph summary
3. Write output/sources.md - key sources cited
**Output**: All final files

## Logging Requirements
Create and maintain append-only `log.md`. NEVER edit previous entries.
