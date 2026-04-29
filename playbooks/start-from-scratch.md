---
name: start-from-scratch
description: >
  Playbook completo para projetos que começam do zero. Define a
  sequência de agentes desde o brief até o handoff, com gates de
  qualidade entre cada fase.
---

# Playbook: Start From Scratch

Use quando: Novo produto, nova feature de médio ou grande porte, ou quando não existe nenhum artefato anterior sobre o problema.

## Visão Geral do Fluxo

```
[Brief / Ideia bruta]
        ↓
   PROJECT FRAMING
   (+ pesquisa e benchmark quando necessário)
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
 (usabilidade + acessibilidade + copy + DS)
        ↓
  [Critique Output] ← gate 3
        ↓
  DELIVERY HANDOFF
  (tracking spec + validação para dev)
        ↓
   [Pronto para dev] ← gate 4
```

---

## Fase 0 — Contexto

Antes de chamar qualquer agente, verifique:

**Globais (mantidos pelo time central):**
- [ ] `context/global/product-principles.md`
- [ ] `context/global/design-system.md`
- [ ] `context/global/brand-voice.md`

**Locais (preencha antes de começar):**
- [ ] `context/local/context.md` ← regras de negócio, terminologia, constraints
- [ ] `context/local/personas.md` ← se relevante
- [ ] `context/local/target-audiences.md` ← se relevante
- [ ] `context/local/brand-voice-local.md` ← se o squad tiver tom específico

---

## Fase 1 — Framing

**Agente:** `agents/project-framing.md`

**Input necessário:**
- Brief, PRD, ou descrição do problema
- Nome do stakeholder que pediu e prazo
- Pesquisa, analytics ou benchmarks disponíveis (opcional)

**Output esperado:** `templates/problem-frame.md`

O agente decide automaticamente se executa as fases de pesquisa e benchmark com base no contexto disponível.

### Gate 1 — Checklist de Aprovação

- [ ] O problem statement está em formato "Como podemos..."?
- [ ] O usuário primário está identificado com contexto de uso?
- [ ] Os critérios de sucesso são mensuráveis?
- [ ] O que está fora do escopo está explícito?
- [ ] As hipóteses são verificáveis?

---

## Fase 2 — Jornada

**Agente:** `agents/journey-builder.md`

**Input necessário:** `templates/problem-frame.md` aprovado

**Output esperado:** `templates/journey-spec.md`

### Gate 2 — Checklist de Aprovação

- [ ] Fluxo principal mapeado do ponto de entrada ao de saída?
- [ ] Todos os estados obrigatórios documentados por tela?
- [ ] Edge cases críticos identificados e priorizados?
- [ ] Dependências de dados/API mapeadas?
- [ ] Dúvidas em aberto documentadas com responsável?

---

## Fase 3 — Design (Figma)

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

O agente cobre heurísticas de usabilidade, acessibilidade, estados, edge cases, copies e consistência com o Copan em um único relatório.

### Gate 3 — Checklist de Aprovação

- [ ] Nenhum problema de severidade 4 (catastrófico)?
- [ ] Problemas de severidade 3 têm plano de endereçamento?
- [ ] O design atende ao problem statement?
- [ ] Nenhum componente novo bloqueando — proposta ao Copan feita?

---

## Fase 4 — Entrega

**Agente:** `agents/delivery-handoff.md`

**Input necessário:**
- `templates/journey-spec.md`
- `templates/critique-output.md` (confirmando que passou pela revisão)
- Ferramenta de analytics do time

**Output esperado:**
- `templates/tracking-spec.md`
- Relatório de handoff com checklist para o dev

### Gate 4 — Checklist Final

- [ ] Nenhum item bloqueante no relatório de handoff?
- [ ] Tracking spec com todos os eventos P0 especificados?
- [ ] Componentes novos comunicados ao time de DS?

**Somente após todos os gates:** Mover frame no Figma para "Pronto para Dev".
