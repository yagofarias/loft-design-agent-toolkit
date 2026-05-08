---
name: handoff
description: >
  Prepares the complete dev spec: generates the analytics event spec and
  validates the design is fully documented for implementation. Use as the
  last step before marking a journey as ready for dev.
  💡 Recommended model: Sonnet 4.6 (balanced reasoning/cost).
disable-model-invocation: true
allowed-tools: Read, Grep, Glob
---

Antes de iniciar, siga a lógica de gestão de projetos definida no CLAUDE.md — identifique ou crie o projeto em `projects/` e salve os outputs lá.

Start a delivery handoff session by reading and following the protocol in `agents/delivery-handoff.md`.

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
- `skills/analytics-events.md`
- `skills/user-flows.md`
- `skills/state-coverage.md`
- `skills/copan-check.md`
- `skills/edge-cases.md`
- `skills/gut-check.md`

Then follow `agents/delivery-handoff.md` from Phase 1 (intake).

$ARGUMENTS
