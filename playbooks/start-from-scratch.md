---
name: start-from-scratch
description: >
  Playbook completo para projetos que começam do zero. Define a
  sequência de agentes e artefatos necessários desde o brief até
  o handoff, com gates de qualidade entre cada fase.
---

# Playbook: Start From Scratch

Use quando: Novo produto, nova feature de médio ou grande porte, ou quando não existe nenhum artefato anterior sobre o problema.

## Visão Geral do Fluxo

```
[Brief / Ideia bruta]
        ↓
   PROJECT FRAMING
        ↓
  [Problem Frame] ← gate 1
        ↓
  JOURNEY BUILDER
        ↓
  [Journey Spec] ← gate 2
        ↓
      (design no Figma)
        ↓
 SOLUTION CRITIQUE
        ↓
  [Critique Output] ← gate 3
        ↓
  DS COPY REVIEW
        ↓
TRACKING HANDOFF + DEV HANDOFF
        ↓
   [Specs prontas] ← gate 4
```

---

## Fase 0 — Contexto

Antes de chamar qualquer agente, verifique se os arquivos de contexto estão prontos:

**Globais (obrigatórios — mantidos pelo time central):**
- [ ] `context/global/product-principles.md`
- [ ] `context/global/design-system.md`
- [ ] `context/global/brand-voice.md`

**Do seu squad (preencha antes de começar):**
- [ ] `context/local/context.md` ← regras de negócio, terminologia, constraints
- [ ] `context/local/personas.md` ← se relevante para este projeto
- [ ] `context/local/target-audiences.md` ← se relevante para este projeto
- [ ] `context/local/brand-voice-local.md` ← se o squad tiver tom específico

> Quanto mais rico o contexto do squad, mais específicos e úteis serão os outputs dos agentes.

---

## Fase 1 — Framing

**Agente:** `agents/project-framing.md`

**Input necessário:**
- Brief, PRD, ou descrição do problema
- Nome do stakeholder que pediu
- Prazo esperado

**Output esperado:** `templates/problem-frame.md`

### Gate 1 — Checklist de Aprovação

- [ ] O problem statement está em formato "Como podemos..."?
- [ ] O usuário primário está identificado?
- [ ] Os critérios de sucesso são mensuráveis?
- [ ] O que está fora do escopo está explícito?
- [ ] As hipóteses são verificáveis?

**Se algum item falhar:** Retorne ao agente `project-framing` para refinamento.

---

## Fase 2 — Estruturação da Jornada

**Agente:** `agents/journey-builder.md`

**Input necessário:** `templates/problem-frame.md` aprovado

**Output esperado:** `templates/journey-spec.md`

### Gate 2 — Checklist de Aprovação

- [ ] Fluxo principal mapeado do ponto de entrada ao de saída?
- [ ] Todos os estados obrigatórios documentados por tela?
- [ ] Edge cases críticos identificados e priorizados?
- [ ] Dependências de dados/API mapeadas?
- [ ] Dúvidas em aberto documentadas com responsável?

**Se algum item falhar:** Retorne ao agente `journey-builder`.

---

## Fase 3 — Design (Figma)

Esta é a fase de design visual. O toolkit não substitui o trabalho no Figma — ele o informa.

Use o `templates/journey-spec.md` como referência constante. Para cada tela:

1. Consulte `context/global/design-system.md` para componentes disponíveis no Copan
2. Implemente todos os estados mapeados no journey spec
3. Documente nos layers do Figma qualquer decisão que não seja óbvia

---

## Fase 4 — Critique

**Agente:** `agents/solution-critique.md`

**Input necessário:**
- Link do Figma ou descrição detalhada da jornada
- `templates/problem-frame.md`
- `templates/journey-spec.md`

**Output esperado:** `templates/critique-output.md`

### Gate 3 — Checklist de Aprovação

- [ ] Nenhum problema de severidade catastrófica (nível 4)?
- [ ] Problemas de severidade 3 têm plano de endereçamento?
- [ ] O design atende ao problem statement?
- [ ] O usuário primário consegue completar o fluxo sem ambiguidade?

**Se houver bloqueantes:** Corrija no Figma e repita a critique.

---

## Fase 5 — DS Copy Review

**Agente:** `agents/ds-copy-review.md`

**Input necessário:** Inventário de copies da jornada + link do Figma

**Output esperado:** `templates/ds-audit-output.md`

---

## Fase 6 — Tracking e Handoff

Execute os dois agentes em paralelo:

**Agente:** `agents/tracking-handoff.md` → `templates/tracking-spec.md`
**Agente:** `agents/dev-handoff.md` → Relatório de prontidão

### Gate 4 — Checklist Final

- [ ] Nenhum item bloqueante no relatório do `dev-handoff`?
- [ ] Tracking spec aprovado pelo time de dados?
- [ ] Copies finalizados?
- [ ] Componentes novos documentados e comunicados ao time de DS (Copan)?

**Somente após todos os gates:** Mover frame no Figma para "Pronto para Dev".

---

## Tempo Estimado por Fase

| Fase | Pequena | Média | Grande |
|------|---------|-------|--------|
| Framing | 30 min | 1h | 2h |
| Journey | 1h | 2-3h | 4-8h |
| Design | Variável | Variável | Variável |
| Critique | 30 min | 1h | 2h |
| DS Review | 30 min | 1h | 2h |
| Handoff | 1h | 2h | 4h |
