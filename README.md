# Loft Design Agent Toolkit

A design agent toolkit for Loft's design team — structured agents, skills, playbooks and templates to frame problems, map journeys, critique solutions, and generate dev-ready specs using Claude.

---

## Agents

Five agents covering the full design process. Each can be used standalone or sequenced via a playbook.

### Context
> Use before designing when user context or market approach is unclear.

| Agent | What it does |
|-------|-------------|
| `project-framing` | Transforms a brief or PRD into a structured problem statement. Includes optional research synthesis and competitive benchmark phases when context is missing. |

### Design Core
> The heart of the process — frame, map, critique.

| Agent | What it does |
|-------|-------------|
| `project-framing` | ↑ also the entry point for design core |
| `journey-builder` | Maps flows, states, edge cases and dependencies from the problem frame. |
| `solution-critique` | Evaluates the design in one pass: usability heuristics, WCAG accessibility, state completeness, copy clarity, and DS consistency. Single consolidated report. |

### Delivery
> Last step before handing off to dev.

| Agent | What it does |
|-------|-------------|
| `delivery-handoff` | Generates the analytics event spec and validates the design is fully documented for dev — no ambiguity, no missing states. |

---

## Skills

Modular knowledge units loaded by agents. Can also be used directly in a conversation.

| Skill | Loaded by |
|-------|-----------|
| `problem-definition` | project-framing |
| `flow-structuring` | journey-builder, delivery-handoff |
| `state-mapping` | journey-builder, solution-critique, delivery-handoff |
| `edge-case-detection` | journey-builder, solution-critique, delivery-handoff |
| `heuristic-evaluation` | solution-critique |
| `copy-review` | solution-critique |
| `component-validation` | solution-critique, delivery-handoff |
| `event-modeling` | delivery-handoff |

---

## Playbooks

Step-by-step sequences with quality gates between phases.

| Playbook | When to use |
|----------|-------------|
| `start-from-scratch` | New product or large feature from zero |
| `brief-to-design` | Received a PRD or formal brief to execute |
| `quick-product-change` | Small incremental change to existing feature |

---

## Context Structure

```
context/
  global/                  ← maintained by central design team
    product-principles.md
    design-system.md       ← links and quick reference for Copan
    brand-voice.md

  local/                   ← maintained by your squad (fill this first)
    README.md              ← instructions
    context.md             ← business rules, terminology, constraints
    personas.md            ← optional
    target-audiences.md    ← optional
    brand-voice-local.md   ← optional
```

---

## Quick Start

1. Fill in `context/local/context.md` with your squad's domain knowledge
2. Check that `context/global/` files are up to date
3. Read `docs/how-to-use.md`
4. Start with `agents/project-framing.md`

## Contributing

See `docs/how-to-contribute.md`.
