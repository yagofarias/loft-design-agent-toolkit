---
name: brief-to-design
description: >
  Playbook para transformar um brief de negócio, PRD, ou requisito
  de stakeholder em design pronto para desenvolvimento.
---

# Playbook: Brief to Design

Use quando: Você recebeu um PRD, um requisito de stakeholder, ou um brief formal e precisa transformar isso em design com qualidade de handoff.

---

## Antes de Começar: Diagnóstico do Brief

| Tipo | Características | Ação |
|------|----------------|------|
| **PRD completo** | Tem contexto, métricas, personas, critérios de aceite | Ir direto para Fase 1 |
| **PRD parcial** | Tem o quê mas falta o porquê ou os critérios | Fase 0 obrigatória |
| **Brief informal** | Conversa, e-mail, ou Slack com requisito vago | Fase 0 obrigatória |
| **Requisito técnico** | Ticket de eng, requisito de compliance | Traduzir antes da Fase 0 |

---

## Fase 0 — Validação do Brief (quando necessário)

Use a skill `requirement-translation` para processar o input.

Produza um documento de alinhamento com:
1. **O que entendi que foi pedido**
2. **O que está ambíguo**
3. **O que estou assumindo**
4. **Minha recomendação de escopo**

**Compartilhe com o stakeholder antes de continuar.**

---

## Fase 1 — Framing

**Agente:** `agents/project-framing.md`

Passe como input:
- O brief original
- O documento de validação (Fase 0)
- Confirmações recebidas do stakeholder

Ao final, valide com o stakeholder se o problem statement representa o que foi pedido.

---

## Fase 2 — Jornada

**Agente:** `agents/journey-builder.md`

Consulte o time de engenharia para constraints técnicas antes de mapear.

---

## Fase 3 — Design

Referências obrigatórias:
- `templates/journey-spec.md`
- `templates/problem-frame.md`
- `context/design-system-tokens.md`
- `context/brand-voice.md`

---

## Fase 4 — Validação com Stakeholder (pré-critique)

Apresente para o stakeholder com foco em:
1. "Isso resolve o que foi pedido?"
2. "Há algum requisito que não ficou representado?"

Registre o feedback e ajuste antes da critique.

---

## Fase 5 — Critique, DS Review e Handoff

Siga as fases 4, 5 e 6 do `start-from-scratch.md`.

---

## Armadilhas Comuns em Brief-to-Design

**A solução já vem no brief:**
Stakeholders frequentemente pedem uma feature específica quando o problema real é outro. Sempre questione.

**O escopo cresce durante o design:**
Documente o que está fora do escopo e resista à expansão — crie tickets separados.

**O brief está desatualizado:**
Confirme se as premissas ainda são válidas antes de começar.
