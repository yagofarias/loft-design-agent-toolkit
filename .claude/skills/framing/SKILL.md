---
name: framing
description: >
  Starts a project framing session. Transforms any starting point — brief, PRD,
  RFC, SDD, or raw idea — into a structured Design Doc. Use when starting a new
  project or feature, or when translating an existing document into design context.
disable-model-invocation: true
allowed-tools: Read, Grep, Glob, WebFetch, WebSearch
---

Antes de iniciar, siga a lógica de gestão de projetos definida no CLAUDE.md — identifique ou crie o projeto em `projects/` e salve os outputs lá.

Start a project framing session by reading and following the protocol in `agents/project-framing.md`.

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
- `skills/problem-scoping.md`
- `skills/gut-check.md`

Then follow `agents/project-framing.md` from Phase 0 (diagnosing the starting point).

$ARGUMENTS
