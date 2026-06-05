# Verified Workflow Skill — Project Memory

## What This Is

A **meta-productivity skill** for AI coding agents (Claude). It provides 9 structured sub-workflows that turn vague, ambiguous user requests into verifiable, checkable processes. Each sub-workflow has separation of concerns between analysis/reading and action/mutation.

**Core philosophy:** Ambiguous → Verifiable.

## Project Structure

```
verified-workflow-hd-skill/
├── SKILL.md                     ← Master skill definition (all 9 workflows)
├── CLAUDE.md                    ← This file — project memory for AI agents
├── README.md                    ← Human-facing overview
├── LICENSE                      ← MIT license
├── references/
│   ├── examples.md              ← Example prompts + expected outputs
│   └── quick-reference.md       ← Cheatsheet / decision tree
└── .commandcode/
    └── taste/
        └── taste.md             ← Learned preferences (auto-managed)
```

## The 9 Sub-Workflows

| # | Name | Purpose |
|---|------|---------|
| 1 | **Rule Extraction from Repeated Errors** | Mine past sessions for recurring corrections → output imperative rules with evidence |
| 2 | **Claim Verification Before Use** | Decompose content into factual claims → classify ✅/⚠️/❌/🔶 with sources |
| 3 | **Tournament of Variants** | Generate ≥6 solution variants → pairwise elimination → top 3 with reasoning |
| 4 | **Pairwise Priority Ranking** | N×(N−1)/2 comparisons using Urgency/Impact/Effort → ranked list |
| 5 | **Sandboxed Data Agent** | Read-only agent processes untrusted data → risk report → human checkpoint |
| 6 | **Token-Budgeted Workflow** | Decompose task → sort by value/cost → fit within token ceiling |
| 7 | **Requirements Analysis & Spec Capture** | Turn vague request → structured spec with ACs, edge cases, and gap log |
| 8 | **Dependency & Blast Radius Analysis** | Trace incoming/outgoing deps → risk-ranked impact report before changes |
| 9 | **Retrospective / Post-Mortem** | Structured review of incidents → root causes (5 Whys) → action items → reusable rules |

## Key Design Principles

1. **Evidence-traceable outputs** — every assertion cites its basis (error count, source, comparison win, cost estimate)
2. **Explicit assumptions** — state when filling gaps
3. **Separation of reading and acting** — workflows 5, 6, 8 have mandatory human checkpoints
4. **Fail loudly** — never silently skip; say "couldn't complete" if stuck
5. **Falsifiable rules** — rules must be checkable (you can tell if violated)

## When to Edit Each File

| File | Edit when... |
|------|-------------|
| `SKILL.md` | Adding/removing/modifying a sub-workflow, trigger phrases, or quality checks |
| `references/examples.md` | Adding a new workflow example or updating existing ones |
| `references/quick-reference.md` | Updating trigger phrases, constraints, or the decision tree |
| `CLAUDE.md` | Project structure changes or major version bumps |
| `README.md` | Human-facing audience changes |
| `.commandcode/taste/taste.md` | **Never** — this is auto-managed by CommandCode |

## Conventions

- All workflow instructions follow: **Goal → Steps → Output → Quality checks**
- Output formats use markdown tables, code blocks, and emoji labels where appropriate
- Every rule/claim/comparison/cost estimate must be falsifiable and traced back to evidence
- Use trigger-phrase tables in workflow headers so agents can quickly match user intent

## Version

Current: v1.1.0

See `SKILL.md` changelog for history.
