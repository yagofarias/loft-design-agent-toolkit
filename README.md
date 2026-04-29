# Loft Design Agent Toolkit

A design agent toolkit for Loft's design team — structured agents, skills, playbooks and templates to frame problems, map journeys, critique solutions, review copy and generate dev-ready specs using Claude.

## Structure

```
/agents      → Orchestrators that run end-to-end tasks
/skills      → Modular knowledge units loaded by agents
/playbooks   → Step-by-step sequences with quality gates
/templates   → Structured outputs accumulated per project
/context
  /global    → Loft-wide context (maintained by central design team)
  /local     → Your local context (maintained by you — fill this first)
/docs        → How to use and how to contribute
```

## Quick Start

1. Fill in `context/local/context.md` with your domain knowledge
2. Check that `context/global/` files are up to date
3. Read `docs/how-to-use.md`
4. Pick a playbook that matches your project type

## Agents

| Agent | When to use |
|-------|-------------|
| `benchmark-research` | Before framing — maps how the market solves the same problem |
| `ux-research-primer` | Before framing — synthesizes existing research and surfaces gaps |
| `project-framing` | Start of any project — turns briefs into structured problem frames |
| `journey-builder` | After framing — maps flows, states, and edge cases |
| `solution-critique` | Before stakeholder review or dev handoff |
| `ds-copy-review` | Before handoff — validates copy and DS (Copan) consistency |
| `tracking-handoff` | Generates analytics event specs for dev |
| `dev-handoff` | Final gate before marking ready for dev |
| `ux-research-primer` | Before framing — synthesizes existing research and maps knowledge gaps |
| `benchmark-research` | Before framing — maps how competitors solve a design problem |

> Not every project needs every agent. Use only what makes sense for your scope.

## Playbooks

| Playbook | When to use |
|----------|-------------|
| `start-from-scratch` | New product or large feature from zero |
| `quick-product-change` | Small incremental change to existing feature |
| `brief-to-design` | Received a PRD or formal brief to execute |

## Context Structure

```
context/
  global/                  ← maintained by central design team
    product-principles.md
    design-system.md       ← links and quick reference for Copan
    brand-voice.md

  local/                   ← maintained by you, specific to your domain
    README.md              ← instructions for this folder
    context.md             ← domain rules, terminology, constraints (fill this first)
    personas.md            ← optional
    target-audiences.md    ← optional
    brand-voice-local.md   ← optional
```

## Contributing

See `docs/how-to-contribute.md`.
