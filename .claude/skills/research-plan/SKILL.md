---
name: research-plan
description: >
  Starts a research planning session. Transforms hypotheses and uncertainties
  into an executable research plan — with objectives, research questions,
  method, participants, interview scripts and analysis plan. Works from an
  existing design-doc (extracting [A VALIDAR:] items) or as standalone
  research planning. Use before /solution-craft when critical hypotheses
  need validation.
  💡 Recommended model: Opus 4.6 (qualitative judgment on method selection).
disable-model-invocation: true
allowed-tools: Read, Grep, Glob, WebSearch
---

Antes de iniciar, siga a lógica de gestão de projetos definida no CLAUDE.md — identifique ou crie o projeto em `projects/` e salve os outputs lá.

Start a research planning session by reading and following the protocol in `agents/research-plan.md`.

Before starting, read these files:

**Global context (always):**
- `context/global/product-principles.md`

**Squad context (load what exists):**
- `context/local/context.md`
- `context/local/personas.md`
- `context/local/research-archive.md` *(se existir — acervo de pesquisas anteriores)*

**Skills:**
- `skills/research-archive.md`
- `skills/interview-script.md`
- `skills/summarize-interview.md`

Then follow `agents/research-plan.md` from Phase 0 (triagem).
