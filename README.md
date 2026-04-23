# Loft Design Agent Toolkit

A design agent toolkit for Loft's design team — structured agents, skills, playbooks and templates to frame problems, map journeys, critique solutions, review copy and generate dev-ready specs using Claude.

## Structure

```
/agents      → Orchestrators that run end-to-end tasks
/skills      → Modular knowledge units loaded by agents
/playbooks   → Step-by-step sequences with quality gates
/templates   → Structured outputs accumulated per project
/context     → Product-specific context (fill this first)
/docs        → How to use and how to contribute
```

## Quick Start

1. Fill in the `/context` files with real Loft product data
2. Read `docs/how-to-use.md`
3. Pick a playbook that matches your project type
4. Start with `agents/project-framing.md`

## Agents

| Agent | When to use |
|-------|-------------|
| `project-framing` | Start of any project — turns briefs into structured problem frames |
| `journey-builder` | After framing — maps flows, states, and edge cases |
| `solution-critique` | Before stakeholder review or dev handoff |
| `ds-copy-review` | Before handoff — validates copy and DS consistency |
| `tracking-handoff` | Generates analytics event specs for dev |
| `dev-handoff` | Final gate before marking ready for dev |

## Playbooks

| Playbook | When to use |
|----------|-------------|
| `start-from-scratch` | New product or large feature from zero |
| `quick-product-change` | Small incremental change to existing feature |
| `brief-to-design` | Received a PRD or formal brief to execute |

## Contributing

See `docs/how-to-contribute.md`.
