# Pre-Flight Decisions

## Task
Research the current scientific understanding of Earth's magnetic field changes, pole reversals, and whether recent research updates the consensus view about events in our lifetime.

## Execution Mode
- Mode: Multi-phase pipeline
- Phase 1: Non-blocking parallel (6 scouts)
- Phase 2: Sequential (aggregator waits for Phase 1)
- Phase 3: Sequential (synthesizer waits for Phase 2)

## Environment Strategy
- Strategy: Separate directories per agent
- Rationale: Read-only research, no file conflicts

## Output Aggregation
- Phase 1 → Phase 2: Aggregator reads all scout outputs
- Phase 2 → Phase 3: Synthesizer refines aggregated content
- Phase 3 → Final: User-facing answer

## Model Configuration
- Provider: minimax
- Model: MiniMax-M1
- Thinking: high (reasoning enabled)

## Agents

### Phase 1: Research Scouts
| Name | Focus Area | Key Questions |
|------|------------|---------------|
| scout-pole-reversal | Pole flip mechanics & timeline | When might a reversal occur? What triggers it? |
| scout-field-strength | Field decay measurements | How fast is field weakening? Is it accelerating? |
| scout-south-atlantic-anomaly | SAA and regional variations | What's happening in the SAA? Implications? |
| scout-recent-papers | 2024-2026 publications | What's the cutting-edge research saying? |
| scout-prediction-models | Computational predictions | What do models forecast for coming decades? |
| scout-historical-data | Paleomagnetic records | What does geological history tell us? |

### Phase 2: Aggregator
- Synthesizes all Phase 1 findings
- Identifies consensus vs controversy
- Flags key uncertainties

### Phase 3: Synthesizer
- Produces final cohesive answer
- Addresses user's core question directly
- Provides nuanced, well-sourced conclusion
