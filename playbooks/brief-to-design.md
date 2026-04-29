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
- O brief original e o documento de validação (Fase 0)
- Confirmações recebidas do stakeholder

O agente vai decidir se executa pesquisa ou benchmark com base no contexto disponível.

Valide com o stakeholder se o problem statement representa o que foi pedido antes de avançar.

---

## Fase 2 — Jornada

**Agente:** `agents/journey-builder.md`

Consulte o time de engenharia para constraints técnicas antes de mapear.

---

## Fase 3 — Design

Referências obrigatórias:
- `templates/journey-spec.md`
- `templates/problem-frame.md`
- `context/global/design-system.md`
- `context/local/context.md`

A cada decisão de design que se afasta do brief, documente o motivo.

---

## Fase 4 — Validação com Stakeholder (pré-critique)

Apresente o design para o stakeholder:
1. "Isso resolve o que foi pedido?"
2. "Há algum requisito que não ficou representado?"

Ajuste antes de chamar o critique.

---

## Fase 5 — Critique e Entrega

Siga as fases 4 e 5 do `start-from-scratch.md`.

---

## Armadilhas Comuns

**A solução já vem no brief:** Stakeholders frequentemente pedem uma feature específica quando o problema real é outro. Sempre questione.

**O escopo cresce durante o design:** Documente o que está fora do escopo e crie tickets separados para o resto.

**O brief está desatualizado:** Confirme se as premissas ainda são válidas antes de começar.
