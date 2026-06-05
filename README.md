<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://img.shields.io/badge/Verified%20Workflow%20Skill-v1.1.0-6b9fff?style=for-the-badge&labelColor=1a1a2e&logo=markdown&logoColor=white" />
    <source media="(prefers-color-scheme: light)" srcset="https://img.shields.io/badge/Verified%20Workflow%20Skill-v1.1.0-4f7dff?style=for-the-badge&labelColor=e8ecf8&logo=markdown&logoColor=333" />
    <img alt="Verified Workflow Skill" src="https://img.shields.io/badge/Verified%20Workflow%20Skill-v1.1.0-4f7dff?style=for-the-badge&labelColor=e8ecf8&logo=markdown&logoColor=333" />
  </picture>
</p>

<p align="center">
  <em>Turn ambiguous requests into verifiable, auditable processes — no code, no dependencies, just structured thinking.</em>
</p>

<p align="center">
  <a href="#-the-9-sub-workflows"><strong>Workflows</strong></a> ·
  <a href="#-quick-start"><strong>Quick Start</strong></a> ·
  <a href="#-design-philosophy"><strong>Philosophy</strong></a> ·
  <a href="#-decision-tree"><strong>Decision Tree</strong></a> ·
  <a href="#-contributing"><strong>Contributing</strong></a> ·
  <a href="#-license"><strong>License</strong></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-stable-22c55e?style=flat-square&labelColor=1a1a2e" />
  <img src="https://img.shields.io/badge/dependencies-none-success?style=flat-square&labelColor=1a1a2e" />
  <img src="https://img.shields.io/badge/language-markdown-blue?style=flat-square&labelColor=1a1a2e" />
  <img src="https://img.shields.io/badge/license-MIT-6b9fff?style=flat-square&labelColor=1a1a2e" />
  <img src="https://img.shields.io/badge/ai-agent%20ready-✓-facc15?style=flat-square&labelColor=1a1a2e" />
</p>

<br/>

---

## 📋 Overview

**Verified Workflow Skill** is a structured prompt library for AI coding agents (Claude, GPT, etc.). It provides **9 reusable sub-workflows** that transform vague, ambiguous requests into checkable, evidence-backed outputs.

Instead of ad-hoc answers, you get:

- **Rule Extraction** — Mine past mistakes into codified rules, never repeat them
- **Claim Verification** — Fact-check before publishing, not after
- **Tournament of Variants** — Compare options systematically, pick the best
- **Pairwise Priority Ranking** — True priority, not arbitrary scores
- **Sandboxed Data Agent** — Process untrusted input safely, with human checkpoints
- **Token-Budgeted Workflow** — Predictable cost, no surprise bills
- **Requirements Analysis** — Vague idea → structured spec with acceptance criteria
- **Blast Radius Analysis** — Know what breaks before you change it
- **Retrospective** — Learn from incidents, prevent recurrence

**Zero dependencies. Zero code.** Just well-organized markdown that any LLM agent can read and execute at runtime.

<br/>

---

## 🧩 The 9 Sub-Workflows

### Phase 1: Understand & Plan

| # | Workflow | Trigger Phrases | What It Produces |
|---|----------|----------------|------------------|
| **7** | **Requirements Analysis & Spec Capture** | "turn this into a spec", "acceptance criteria", "edge cases", "spec this out" | Functional pillars with MoSCoW priorities, Given/When/Then ACs, edge case table, risky assumptions surfaced, open questions gap log |
| **4** | **Pairwise Priority Ranking** | "prioritize", "rank tasks", "what should I do first", "compare tasks" | Ranked task list from N×(N−1)/2 comparisons using Urgency/Impact/Effort, with win counts and 2×2 quadrant |
| **3** | **Tournament of Variants** | "multiple options", "compare variants", "tournament", "pick the best", "head-to-head" | ≥6 solution variants → elimination bracket → top 3 with strengths/weaknesses per variant |

### Phase 2: Verify & Build

| # | Workflow | Trigger Phrases | What It Produces |
|---|----------|----------------|------------------|
| **2** | **Claim Verification Before Use** | "verify claims", "fact-check", "check before I publish", "sourced claims" | Numbered claim table classified ✅/⚠️/❌/🔶 with sources, actionable fix list |
| **8** | **Dependency & Blast Radius Analysis** | "what will this break", "blast radius", "impact analysis", "dependencies", "before I change this" | Outgoing deps + incoming deps (blast radius) + risk ranking + 🟢/🟡/🔴 go/no-go recommendation |
| **5** | **Sandboxed Data Agent** | "untrusted data", "sandbox", "suspicious input", "isolate agent", "read-only", "don't run commands" | Read-only agent report: summary → 🟢/🟡/🔴 classification → risk flags → sanitized output → STOP at human checkpoint |

### Phase 3: Execute & Learn

| # | Workflow | Trigger Phrases | What It Produces |
|---|----------|----------------|------------------|
| **6** | **Token-Budgeted Workflow** | "token budget", "limit cost", "under X tokens", "cost ceiling", "efficient workflow" | Prioritized execution plan sorted by value/cost ratio, deferred steps listed, ~10% buffer |
| **1** | **Rule Extraction from Repeated Errors** | "repeated mistakes", "extract rules", "add to CLAUDE.md", "mine past sessions" | Categorized rules in `RULE: … because …` format with error-cluster citations, ready-to-paste `CLAUDE.md` block |
| **9** | **Retrospective / Post-Mortem** | "retrospective", "post-mortem", "lessons learned", "incident review", "sprint retro", "why did this fail" | Timeline → what went well (mandatory) → root causes via 5 Whys → checkable action items → reusable rules |

<br/>

---

## 🚀 Quick Start

### For AI Agents

1. **Load the SKILL.md** into your agent's context (or include it via your agent's skill system).
2. **Watch for trigger phrases** — each workflow has natural-language triggers listed in its header.
3. **Jump to the matching section** — each workflow is self-contained, no need to read all 9.
4. **Follow the steps** — every workflow follows: *Goal → Steps → Output → Quality checks*.

### For Humans

Read [`SKILL.md`](./SKILL.md) to understand the full instructions. Use [`references/quick-reference.md`](./references/quick-reference.md) as a cheatsheet, and [`references/examples.md`](./references/examples.md) to see worked examples before running your own.

```
# Minimal usage — tell your agent:
"I need a spec for my dark mode feature"        → triggers workflow 7
"What will break if I rename send_email?"        → triggers workflow 8
"Run a retro on last night's deploy failure"     → triggers workflow 9
```

<br/>

---

## 🎯 Design Philosophy

### Ambiguous → Verifiable

Every workflow is built on five principles that ensure outputs are trustworthy:

| Principle | What It Means | Example |
|-----------|---------------|---------|
| **Evidence-traceable** | Every assertion cites its basis | Rules cite error clusters. Verifications cite sources. Rankings cite comparison wins. |
| **Explicit over implicit** | State assumptions, don't hide them | "Assumed Tailwind v3 — **risky**: confirm `darkMode: 'class'` is configured" |
| **Separation of concerns** | Reading and acting are always separate | Workflows 5, 6, and 8 require a human checkpoint before any action is taken. |
| **Fail loudly** | Say "couldn't complete" — never silently skip | "Step 3: Fact-checking claims — 3/5 done, 2 claims had no source found. Flagged in gap log." |
| **Falsifiable** | You can tell if a rule/claim/comparison was violated | `RULE: Use prose, not bullets` — checking is trivial: "did I use prose?" |

### Why markdown?

Because LLMs speak markdown natively. No parser, no interpreter, no build step — the agent reads the `##` headers, matches the trigger phrase, and executes the bullet list under the matching section. It's the lowest-friction instruction format for AI.

<br/>

---

## 🌳 Decision Tree

```
User request
├── "set it" / "turn vague idea into spec"
│   └── requirements, edge cases, ACs needed → Workflow 7 (Requirements Analysis)
│
├── "prioritize" / "what should I do first"
│   └── unordered task list needs ranking → Workflow 4 (Pairwise Priority)
│
├── "compare" / "multiple options" / "pick the best"
│   └── needs head-to-head variant comparison → Workflow 3 (Tournament)
│
├── "verify" / "fact-check" / "check before publish"
│   └── content with factual claims to verify → Workflow 2 (Claim Verification)
│
├── "what will break" / "before I change"
│   └── modify something, need impact analysis → Workflow 8 (Blast Radius)
│
├── "untrusted" / "suspicious" / "sandbox"
│   └── process external data without risk → Workflow 5 (Sandboxed Data Agent)
│
├── "token budget" / "cost ceiling" / "limit cost"
│   └── multi-step plan with hard cost ceiling → Workflow 6 (Token-Budgeted)
│
├── "repeated mistakes" / "extract rules"
│   └── codify recurring corrections → Workflow 1 (Rule Extraction)
│
└── "retro" / "post-mortem" / "lessons learned"
    └── review a completed event → Workflow 9 (Retrospective)

If multiple match → run sequentially, tell the user the order and why.
```

<br/>

---

## 📁 Repository Structure

```
verified-workflow-hd-skill/
│
├── SKILL.md                         ← Master skill definition (all 9 workflows)
│   Header: name, version, trigger phrases
│   9 sub-workflows, each with:
│     ├── Trigger phrases
│     ├── Goal
│     ├── Steps (numbered)
│     ├── Output format
│     └── Quality checks
│   General principles
│   Changelog
│
├── CLAUDE.md                        ← Project memory for AI agents
│   Architecture overview, file edit guide, conventions
│
├── README.md                        ← This file
│
├── LICENSE                          ← MIT
│
├── .gitignore
│
└── references/
    ├── quick-reference.md           ← Cheatsheet: triggers, output, constraints per workflow
    │   Decision tree for choosing the right workflow
    └── examples.md                  ← 9 worked examples, one per workflow
        Input → expected output skeleton
```

<br/>

---

## 🧠 Extending the Skill

Adding a new sub-workflow is straightforward:

1. **Append to `SKILL.md`** — follow the pattern: *Trigger phrases → Goal → Steps → Output → Quality checks*
2. **Update `references/quick-reference.md`** — add the new workflow table + decision tree entry
3. **Update `references/examples.md`** — add one worked example
4. **Update `CLAUDE.md` and `README.md`** — reflect new count in tables and structur

Every workflow must preserve the five design principles (see [Design Philosophy](#-design-philosophy)).

<br/>

---

## 🤝 Contributing

Contributions are welcome! This is an open-source skill designed to grow.

- **Bug report / improvement idea** — open an issue
- **New sub-workflow** — follow the [extending guide](#-extending-the-skill) above and submit a PR
- **Better examples** — update `references/examples.md` with real-world scenarios you've found useful

### Guidelines

- Every new workflow must include **quality checks** that are falsifiable — someone must be able to audit the output and say "this rule was violated" or "this AC is untestable"
- **Zero code** — this is a markdown project. No scripts, no build tools, no dependencies.
- **Trigger phrases** must be natural language — what a user would actually say, not what an engineer would type.

<br/>

---

## 📄 License

[MIT](./LICENSE) — do whatever you want with it. We'd love a star if you find it useful.

<br/>

---

<p align="center">
  <sub>Built with structured thinking · Designed for AI agents · Free for everyone</sub>
  <br/>
  <sub>
    <a href="https://github.com/dungnotnull/verified-workflow-hd-skill">GitHub</a> ·
    <a href="./SKILL.md">SKILL.md</a> ·
    <a href="./references/quick-reference.md">Quick Reference</a>
  </sub>
</p>
