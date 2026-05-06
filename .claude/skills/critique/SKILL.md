---
name: critique
description: >
  Reviews a design against usability heuristics, accessibility (WCAG), state
  coverage, copy clarity and Copan consistency. Accepts a Figma URL (accessed
  via Figma MCP when available) or screenshots with context. Produces a
  critique-output.md with a gate decision for handoff.
disable-model-invocation: true
allowed-tools: Read, Grep, Glob
---

Antes de iniciar, siga a lógica de gestão de projetos definida no CLAUDE.md — identifique ou crie o projeto em `projects/` e salve os outputs lá.

Start a design critique session by reading and following the protocol in `agents/design-critique.md`.

Before starting, read these files:

**Global context (always):**
- `context/global/product-principles.md`
- `context/global/brand-voice.md`
- `context/global/design-system.md`

**Squad context (load what exists):**
- `context/local/context.md`
- `context/local/personas.md`
- `context/local/target-audiences.md`
- `context/local/brand-voice-local.md`
- `context/local/competitors.md`

**Skills:**
- `skills/heuristics.md`
- `skills/state-coverage.md`
- `skills/edge-cases.md`
- `skills/ux-writing.md`
- `skills/copan-check.md`
- `skills/gut-check.md`

Then follow `agents/design-critique.md` from Phase 1 (intake).

The designer can share:
- A **Figma URL** — access via Figma MCP when available
- **Screenshots or prints** with context about the flow being reviewed

$ARGUMENTS
