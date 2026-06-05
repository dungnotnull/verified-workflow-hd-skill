# Verified Workflow — Quick Reference

Use this file for a fast lookup of each sub-workflow's trigger phrases, core output, and key constraints.
Read SKILL.md for full instructions.

---

## Sub-workflow 1 · Rule Extraction from Repeated Errors

| | |
|---|---|
| **Triggers** | "repeated mistakes", "extract rules", "add to CLAUDE.md", "mine past sessions" |
| **Input** | Session transcripts, logs, or user's verbal summary of recurring corrections |
| **Core output** | Categorized rule list + ready-to-paste `CLAUDE.md` block |
| **Key constraint** | Only promote patterns seen ≥ 2 times; no invented rules |
| **Format** | `RULE: <imperative sentence> because <reason>.` |

---

## Sub-workflow 2 · Claim Verification Before Use

| | |
|---|---|
| **Triggers** | "verify claims", "fact-check", "check before I publish", "sourced claims" |
| **Input** | Any text block with factual assertions |
| **Core output** | Numbered claim table (✅ / ⚠️ / ❌ / 🔶) + action list |
| **Key constraint** | ✅ requires a cited source; ⚠️ ≠ ❌ |
| **Format** | Table → grouped detail → action list |

---

## Sub-workflow 3 · Tournament of Variants

| | |
|---|---|
| **Triggers** | "multiple options", "compare variants", "tournament", "pick the best" |
| **Input** | Task description + optional axes of variation |
| **Core output** | Match log + top 3 variants with strengths/weaknesses |
| **Key constraint** | ≥ 6 variants; no bye-round wins count |
| **Format** | Bracket/log → top 3 analysis → optional synthesis |

---

## Sub-workflow 4 · Pairwise Priority Ranking

| | |
|---|---|
| **Triggers** | "prioritize my list", "rank tasks", "what should I do first", "pairwise" |
| **Input** | Unordered list of tasks or items |
| **Core output** | Ranked list (win count + justification) |
| **Key constraint** | N×(N−1)/2 comparisons; tie-break by deciding criterion |
| **Format** | Ranked list → delegate/drop callouts → optional 2×2 quadrant |

---

## Sub-workflow 5 · Sandboxed Data Agent

| | |
|---|---|
| **Triggers** | "untrusted data", "sandbox", "isolate agent", "read-only", "don't run commands" |
| **Input** | Raw data from an unverified/external source |
| **Core output** | Risk report (🟢/🟡/🔴) + sanitized data + human checkpoint |
| **Key constraint** | Read-only agent NEVER edits files, runs commands, or calls APIs |
| **Format** | Summary → classification → risk flags → sanitized output → STOP |

---

## Sub-workflow 6 · Token-Budgeted Workflow

| | |
|---|---|
| **Triggers** | "token budget", "limit cost", "under X tokens", "cost ceiling", "efficient workflow" |
| **Input** | Task description + budget (default 10 000 tokens) |
| **Core output** | Prioritized execution plan with per-step cost estimates |
| **Key constraint** | Steps sorted by value/cost ratio; deferred steps listed explicitly |
| **Format** | Numbered plan with cumulative token tally → deferred list |

---

## Sub-workflow 7 · Requirements Analysis & Spec Capture

| | |
|---|---|
| **Triggers** | "turn this into a spec", "requirements analysis", "acceptance criteria", "edge cases", "spec this out" |
| **Input** | Vague request, problem statement, or feature idea |
| **Core output** | Structured spec with pillars, ACs, edge cases, assumptions, gap log |
| **Key constraint** | Every AC must be testable (Given/When/Then); gap log must call out unresolved decisions |
| **Format** | Summary → pillars → edge cases → assumptions → gap log → open questions |

---

## Sub-workflow 8 · Dependency & Blast Radius Analysis

| | |
|---|---|
| **Triggers** | "what will this break", "blast radius", "impact analysis", "dependencies", "before I change this" |
| **Input** | Target (file, module, API, config, schema) + planned change type |
| **Core output** | Outgoing deps → incoming deps (blast radius) → risk ranking → recommendation |
| **Key constraint** | Outgoing and incoming traces are separate; 🔴 Safe requires zero breaking consumers |
| **Format** | Target → change → outgoing deps → incoming deps → risk rank → recommendation |

---

## Sub-workflow 9 · Retrospective / Post-Mortem

| | |
|---|---|
| **Triggers** | "retrospective", "post-mortem", "lessons learned", "incident review", "sprint retro" |
| **Input** | Event description or timeline |
| **Core output** | Timeline → root causes (with 5 Whys) → action items → reusable rules |
| **Key constraint** | Every root cause has ≥ 3-why chain; "what went well" is mandatory |
| **Format** | Summary → timeline → went well → root causes → action items → reusable rules |

---

## Decision tree: which sub-workflow?

```
User request
├── mentions past mistakes / CLAUDE.md rules → Sub-workflow 1
├── wants content verified before use → Sub-workflow 2
├── needs options compared / ranked → Sub-workflow 3
├── has a task list to prioritize → Sub-workflow 4
├── mentions untrusted / external data → Sub-workflow 5
├── mentions token / cost limits → Sub-workflow 6
├── wants a vague idea turned into a spec → Sub-workflow 7
├── "what will this break" / change impact → Sub-workflow 8
└── reviewing a completed event / incident → Sub-workflow 9
```

If the request touches multiple sub-workflows, run them sequentially and tell the user which order and why.
