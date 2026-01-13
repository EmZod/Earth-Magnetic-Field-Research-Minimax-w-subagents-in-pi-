# Earth's Magnetic Field Research: MiniMax-M2.1 Subagent Orchestration

## Executive Summary

This repository documents a comprehensive multi-agent research project investigating Earth's magnetic field changes and the scientific consensus on pole reversals. Using **MiniMax-M2.1**, we orchestrated **8 sub-agents across 3 phases** to produce a definitive 9.9KB research synthesis answering the core question:

> **Is Earth's magnetic field deteriorating, and is there evidence for significant events (like pole reversals) in our lifetime?**

**Key Findings:**
- ✅ YES: The field IS measurably changing (weakened ~10-15% since 1800s, pole accelerating toward Siberia at 55 km/year, South Atlantic Anomaly growing)
- ❌ NO: No credible evidence of imminent reversal—reversals are fundamentally unpredictable (Poisson process)

---

## Architecture Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                    ORCHESTRATION WORKSPACE                       │
│                   (Logging & Coordination)                       │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  ┌─────────────────┐                                            │
│  │     PHASE 1     │   6 PARALLEL SCOUTS (MiniMax-M2.1)         │
│  │   Research      │   Each with distinct research focus        │
│  │   Scouts        │                                            │
│  └────────┬────────┘                                            │
│           │                                                     │
│           ├─ scout-pole-reversal/output/findings.md             │
│           ├─ scout-field-strength/output/findings.md            │
│           ├─ scout-south-atlantic-anomaly/output/findings.md    │
│           ├─ scout-recent-papers/output/findings.md             │
│           ├─ scout-prediction-models/output/findings.md         │
│           └─ scout-historical-data/output/findings.md           │
│                                                                  │
│           ▼                                                     │
│  ┌─────────────────┐                                            │
│  │     PHASE 2     │   1 AGGREGATOR (MiniMax-M2.1)              │
│  │   Synthesis     │   Synthesizes all Phase 1 findings         │
│  └────────┬────────┘                                            │
│           │                                                     │
│           ├─ output/synthesis.md (9.9 KB)                       │
│           ├─ output/key-questions.md                            │
│           └─ output/summary.txt                                 │
│                                                                  │
│           ▼                                                     │
│  ┌─────────────────┐                                            │
│  │     PHASE 3     │   1 SYNTHESIZER (MiniMax-M2.1)             │
│  │   Final Answer  │   Produces user-facing conclusion          │
│  └────────┬────────┘                                            │
│           │                                                     │
│           ├─ output/final-answer.md (9.9 KB) ◄── FINAL OUTPUT   │
│           └─ output/executive-summary.md                        │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Methodology

### Phase 1: Distributed Research (6 Parallel Scouts)

Each scout operated independently with:
- **Model:** MiniMax-M2.1 (thinking enabled)
- **Max Turns:** 25 per agent
- **Tools:** browser, bash, read, write
- **Logging:** Append-only `log.md` per agent (following logging protocol)

**Scout Assignments:**

| Scout | Research Focus | Key Questions |
|-------|---------------|---------------|
| scout-pole-reversal | Pole flip mechanics & predictions | When might reversal occur? What triggers it? |
| scout-field-strength | Field decay measurements | How fast is field weakening? Accelerating? |
| scout-south-atlantic-anomaly | SAA & regional anomalies | What's happening in SAA? Implications? |
| scout-recent-papers | 2024-2026 publications | What's cutting-edge research saying? |
| scout-prediction-models | Computational forecasts | What do models forecast for coming decades? |
| scout-historical-data | Paleomagnetic records | What does geological history tell us? |

**Research Protocol:**
1. Each scout read its `plan.md` for clear objectives and success criteria
2. Scouts maintained append-only execution logs following the logging protocol
3. Each scout produced `output/findings.md` with full citations and source URLs
4. All outputs captured to `output/` directory

### Phase 2: Synthesis (1 Aggregator)

The aggregator synthesized all Phase 1 outputs:
- **Read:** All 6 scout findings.md files
- **Process:** Identified consensus points and debates
- **Output:** `synthesis.md` (thematic organization) and `key-questions.md`

### Phase 3: Final Deliverable (1 Synthesizer)

The synthesizer produced the user-facing answer:
- **Read:** Phase 2 aggregation outputs
- **Output:** `final-answer.md` with direct answer to the core question

---

## Logging Protocol

This project strictly followed the **Logging Protocol** (see `/Users/jay/.claude/skills/logging-protocol/`):

### Key Principles:
1. **Append-Only Log:** Never edit previous entries. History is immutable.
2. **Forward-Only Fixes:** Backtracking = new step that fixes forward
3. **Atomic Steps:** Each step has Pre-Execution → Execution → Post-Execution
4. **Linear Readability:** Any agent can read logs top-to-bottom without graph traversal

### Log Structure Used:
```markdown
# STATE
## Current
step_id: STEP-XX
status: IN_PROGRESS
objective: [current objective]

## Decisions (append-only)
- STEP-01: [decision made]

## Blockers (append-only, mark resolved inline)
- STEP-03: [blocker] → RESOLVED: [how]

---

# STEP LOG (append-only)

## STEP-01
### Pre-Execution
Objective: [what to accomplish]
Beliefs: [what we believe]
Assumptions: [what we're assuming]

### Execution
- [x] Action taken
- Finding: [what discovered]

### Post-Execution
Outcome: PASS | PARTIAL | FAIL
Belief updates: [any changes]
```

### Where Logs Are Located:

**Orchestrator Logs:**
- `orchestrator/log.md` - Master orchestration execution log
- `orchestrator/decisions.md` - Pre-flight architectural decisions

**Agent Logs:**
- `phase1/scout-*/log.md` - Individual scout execution traces
- `phase2/aggregator/log.md` - Aggregator execution trace
- `phase3/synthesizer/log.md` - Synthesizer execution trace

---

## Subagent Orchestration Framework

This project used the **Pi Subagent Orchestration** skill (see `/Users/jay/.claude/skills/pi-subagent-orchestration/`):

### Design Principles:
- **Auditability over convenience:** Every action traceable
- **Git as source of truth:** All commits form canonical record
- **Subagents are expensive:** Spawn deliberately
- **Cleanup is mandatory:** Kill what you spawn
- **Simple over clever:** Boring solutions that work

### Resource Management:
- Each agent had `--max-turns 25` to prevent runaway execution
- tmux sessions used for observability (or `--print-last` for background)
- All processes tracked and cleaned up after completion

### Validation Criterion:
Before spawning any agent, we ensured:
> "Would a blank agent with only plan.md understand this task as self-evident?"

If not, the plan was improved until it was.

---

## Model Configuration

**Critical Note:** The `--model` CLI flag is IGNORED by Pi. Configuration must be set in `~/.pi/agent/settings.json`:

```json
{
  "defaultProvider": "minimax",
  "defaultModel": "MiniMax-M2.1",
  "defaultThinkingLevel": "thinking"
}
```

This was set before any agent spawning to ensure all 8 sub-agents used:
- **Provider:** minimax
- **Model:** MiniMax-M2.1
- **Thinking:** enabled

---

## Project Timeline

```
2026-01-13 21:15 - Workspace initialized, git repo created
2026-01-13 21:18 - Phase 1 spawned (6 scouts, parallel)
2026-01-13 21:26 - Phase 1 complete (48.5 KB findings)
2026-01-13 21:26 - Phase 2 spawned (aggregator)
2026-01-13 21:30 - Phase 2 complete (9.9 KB synthesis)
2026-01-13 21:30 - Phase 3 spawned (synthesizer)
2026-01-13 21:35 - Phase 3 complete (9.9 KB final answer)

Total Duration: ~20 minutes
Total Research: 48.5 KB Phase 1 + 9.9 KB Phase 2 + 9.9 KB Phase 3
Sources Cited: 48+ scientific sources (NASA, ESA Swarm, peer-reviewed journals)
```

---

## File Structure

```
Earth magnetic field research/
├── README.md                          ◄── This file
├── dashboard.html                     ◄── Visual dashboard (45 KB, Three.js)
│
├── orchestrator/
│   ├── log.md                         ◄── Master execution log
│   └── decisions.md                   ◄── Architectural decisions
│
├── phase1/                            ◄── 6 Research Scouts
│   ├── scout-pole-reversal/
│   │   ├── plan.md                    ◄── Scout objectives & steps
│   │   ├── log.md                     ◄── Execution trace
│   │   └── output/
│   │       ├── findings.md            ◄── Research findings (10.4 KB)
│   │       └── run.log
│   │
│   ├── scout-field-strength/
│   │   ├── plan.md
│   │   ├── log.md
│   │   └── output/
│   │       ├── findings.md            ◄── Research findings (5.4 KB)
│   │       └── run.log
│   │
│   ├── scout-south-atlantic-anomaly/
│   │   ├── plan.md
│   │   ├── log.md
│   │   └── output/
│   │       ├── findings.md            ◄── Research findings (5.9 KB)
│   │       └── run.log
│   │
│   ├── scout-recent-papers/
│   │   ├── plan.md
│   │   ├── log.md
│   │   └── output/
│   │       ├── findings.md            ◄── Research findings (10.6 KB)
│   │       └── run.log
│   │
│   ├── scout-prediction-models/
│   │   ├── plan.md
│   │   ├── log.md
│   │   └── output/
│   │       ├── findings.md            ◄── Research findings (7.8 KB)
│   │       └── run.log
│   │
│   └── scout-historical-data/
│       ├── plan.md
│       ├── log.md
│       └── output/
│           ├── findings.md            ◄── Research findings (8.4 KB)
│           └── run.log
│
├── phase2/                            ◄── 1 Aggregator
│   └── aggregator/
│       ├── plan.md
│       ├── log.md
│       └── output/
│           ├── synthesis.md           ◄── Thematic synthesis (9.9 KB)
│           ├── key-questions.md       ◄── Unanswered questions
│           └── summary.txt            ◄── Executive summary
│
└── phase3/                            ◄── 1 Synthesizer
    └── synthesizer/
        ├── plan.md
        ├── log.md
        └── output/
            ├── final-answer.md        ◄── FINAL DELIVERABLE (9.9 KB)
            └── executive-summary.md   ◄── Quick read version
```

---

## Research Findings Summary

### Direct Answer

**Yes, the field IS measurably changing:**
- Weakened ~10-15% since the 1800s
- North Magnetic Pole accelerating toward Siberia at ~55 km/year
- South Atlantic Anomaly grown significantly since 2014

**No, there is no credible evidence of imminent reversal:**
- Reversals are fundamentally unpredictable (Poisson process)
- Last reversal ~780,000 years ago (much longer than average ~450,000 year interval)
- Models can only predict ~5 years ahead; cannot predict reversals

### Key Statistics

| Metric | Value |
|--------|-------|
| Field weakening rate | ~6.3% per century |
| Surface field strength | 25-65 microteslas |
| Pole migration speed | ~55 km/year (accelerating from ~10 km/year in 1900s) |
| SAA growth | ~½ continental Europe since 2014 |
| Reversals in 83M years | 183+ |
| Last full reversal | ~780,000 years ago |
| Reversal duration | 1,000-22,000 years |
| Reversal interval (average) | ~450,000 years |
| Prediction horizon | 5 years (operational models) |

### Scientific Consensus

**Agreed Upon (all scouts):**
1. Field is weakening (~10-15% since 1800s)
2. North pole accelerating toward Siberia
3. SAA is real, growing, deepening
4. Reversals are statistically random—no prediction possible
5. Last full reversal ~780,000 years ago
6. Reversal duration: 1,000-22,000 years
7. Field never disappears completely
8. WMM/IGRF reliable ~5 years ahead

**Debated Among Scientists:**
1. Current change significance (normal vs. unusual precursor)
2. Laschamp event causal links
3. Reversal probability after long Brunhes period
4. Duration estimates for past reversals

### Key Uncertainties

1. **Is current behavior "normal" or "unusual"?** — Open scientific question
2. **When will the next reversal occur?** — Fundamentally unpredictable
3. **How fast will future reversals be?** — Estimates vary by orders of magnitude
4. **What will be the effects?** — Some impacts known, others uncertain

---

## Source References

Research synthesized from 48+ scientific sources including:
- NASA Geomagnetism
- ESA Swarm Mission Data
- NOAA National Geophysical Data Center
- World Magnetic Model (WMM2025)
- International Geomagnetic Reference Field (IGRF-14)
- Peer-reviewed journals: Nature, Science, JGR, Earth and Planetary Science Letters
- Recent publications (2024-2026)

---

## Technical Stack

- **Orchestration Framework:** Claude Code + Pi Subagent Orchestration skill
- **Language Model:** MiniMax-M2.1
- **Logging Protocol:** Custom append-only execution logging
- **Dashboard:** Three.js for 3D Earth visualization
- **Research Duration:** ~20 minutes for 8 agents
- **Total Output:** ~70 KB of research documents

---

## How to Reproduce

1. Configure MiniMax-M2.1 in `~/.pi/agent/settings.json`
2. Create workspace directory
3. Copy plan.md files for each agent
4. Spawn agents in parallel (Phase 1), then sequential (Phase 2, 3)
5. Monitor via tmux sessions or run logs
6. Collect outputs from each phase

---

## Key Learnings

1. **MiniMax-M2.1** produces high-quality research with reasoning traces
2. **Parallel scouting** dramatically reduces total execution time
3. **Append-only logging** enables perfect audit trails and agent handoffs
4. **Phase-based architecture** ensures clear separation of concerns
5. **Explicit logging protocol** prevents confusion during multi-agent coordination

---

## License

This research is provided for educational and scientific purposes.

---

## Repository Info

- **Repository:** Earth-Magnetic-Field-Research-Minimax-w-subagents-in-pi-
- **Created:** January 13, 2026
- **Model Used:** MiniMax-M2.1
- **Total Agents:** 8 sub-agents across 3 phases
- **Final Output:** `phase3/synthesizer/output/final-answer.md`

---

*Generated through multi-agent orchestration using MiniMax-M2.1 and the Pi subagent framework.*

---

## 🤖 AI-Generated Repository

This entire repository was conceptualized, architected, and implemented by **MiniMax-M2.1** - the reasoning model explicitly specified for this project.

### AI Identity & Configuration

**Model:** MiniMax-M2.1  
**Thinking Level:** Enabled  
**Provider:** Minimax (official API)  
**Framework:** Claude Code + Pi Subagent Orchestration

The model configuration was detected and inferred from the official Minimax provider API settings:

```json
{
  "defaultProvider": "minimax",
  "defaultModel": "MiniMax-M2.1",
  "defaultThinkingLevel": "thinking"
}
```

### What MiniMax-M2.1 Did:

1. **Read and understood** the Pi Subagent Orchestration skill documentation
2. **Read and understood** the Logging Protocol skill documentation
3. **Designed the architecture** - 3-phase pipeline with 8 sub-agents
4. **Created all plans** - Detailed plan.md files for each agent
5. **Configured the model** - Set up MiniMax-M2.1 with thinking enabled (inferred from provider API)
6. **Spawned all agents** - Orchestrated parallel and sequential execution
7. **Monitored progress** - Tracked all 8 agents through completion
8. **Compiled findings** - Synthesized 48.5 KB of research into final answer
9. **Built the dashboard** - Created visual Three.js presentation
10. **Documented everything** - Wrote comprehensive README with methodology
11. **Pushed to GitHub** - Set up repository with description and topics

### Key Decisions Made by MiniMax-M2.1:

- **Model Selection:** Used MiniMax-M2.1 as detected from official provider API
- **Architecture:** Designed 3-phase pipeline (parallel scouts → aggregator → synthesizer)
- **Logging Strategy:** Used append-only logging protocol for perfect auditability
- **Phase Distribution:** 6 parallel scouts for breadth, 1 aggregator for synthesis, 1 synthesizer for final output
- **Research Focus:** Identified 6 distinct research angles to cover comprehensively
- **Dashboard Design:** Created visual presentation with 3D Earth animation

### Transparency:

All execution logs are preserved in this repository, showing:
- Pre-execution assumptions and objectives
- Real-time execution progress
- Findings and discoveries
- Post-execution outcomes
- Belief updates and hypotheses

This demonstrates complete transparency into MiniMax-M2.1's decision-making process with thinking enabled.

---

*Repository created by MiniMax-M2.1 via Pi harness - January 13, 2026*
