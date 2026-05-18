# Brief to Design

Use quando: você recebeu um PRD, requisito de stakeholder, ou brief formal e precisa transformar isso em design com qualidade de handoff.

---

## Diagnóstico do brief

| Tipo | Ação |
|------|------|
| PRD completo — tem contexto, métricas, personas, critérios | Ir direto para Fase 1 |
| PRD parcial — tem o quê mas falta o porquê | Fase 0 obrigatória |
| Brief informal — conversa, e-mail ou Slack | Fase 0 obrigatória |
| Requisito técnico — ticket de eng, compliance | Traduzir antes da Fase 0 |

---

## Fase 0 — Validação do brief (quando necessário)

Antes de chamar qualquer agente, produza um documento curto com:

1. O que entendi que foi pedido
2. O que está ambíguo
3. O que estou assumindo
4. Minha recomendação de escopo

Compartilhe com o stakeholder e confirme antes de continuar.

---

## Fase 1 — Framing

**Comando:** `/framing`

Passe o brief original e as confirmações do stakeholder como input. O agente gera o Design Doc e separa o que foi pedido do problema real.

Valide com o stakeholder se o problem statement representa o que foi pedido antes de avançar.

---

## Fase 2 — Pesquisa (quando necessário)

**Comando:** `/research-plan`

Se o Design Doc tiver hipóteses a validar, estruture a pesquisa antes de ir para a solução. Especialmente útil quando o brief assume comportamentos do usuário que não foram confirmados.

---

## Fase 3 — Solução e Design

**Comando:** `/solution-craft`

Consulte o time de engenharia para constraints técnicas antes de mapear os fluxos.

A cada decisão de design que se afasta do brief, documente o motivo na seção Decisões de Design do design-doc.

---

## Fase 4 — Validação com stakeholder (pré-critique)

Apresente o design antes de chamar o critique:

1. "Isso resolve o que foi pedido?"
2. "Há algum requisito que não ficou representado?"

Ajuste com base no feedback antes de continuar.

---

## Fase 5 — Critique e Handoff

**Comandos:** `/critique` → `/handoff`

Siga o fluxo completo descrito em `docs/start-from-scratch.md` a partir da Fase 5.

---

## Armadilhas comuns

**A solução já vem no brief:** stakeholders frequentemente pedem uma feature específica quando o problema real é outro. O `/framing` ajuda a separar os dois — não pule essa etapa.

**Escopo crescente durante o design:** documente o que está fora do escopo no Design Doc e crie tickets separados para o resto.

**Brief desatualizado:** confirme se as premissas ainda são válidas antes de começar.
