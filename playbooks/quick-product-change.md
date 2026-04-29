---
name: quick-product-change
description: >
  Playbook acelerado para mudanças pequenas e incrementais em produto
  existente. Foco em critique e handoff simplificado.
---

# Playbook: Quick Product Change

Use quando: Mudança pontual em feature existente, ajuste de copy, correção de UX, ou melhoria incremental com escopo bem definido.

**Não use quando:** A mudança afeta fluxos inteiros, muda a arquitetura de informação, ou envolve componentes novos significativos — use `start-from-scratch.md`.

## Decisão Rápida de Escopo

1. A mudança afeta mais de 3 telas? → `start-from-scratch`
2. Muda como o usuário completa uma tarefa principal? → `start-from-scratch`
3. Precisa de componentes novos que não existem no Copan? → Consulte o time de DS antes

---

## Fluxo Comprimido

```
[Mudança identificada]
        ↓
  MINI FRAMING (você mesmo)
        ↓
      (design)
        ↓
  SOLUTION CRITIQUE
        ↓
   DELIVERY HANDOFF (simplificado)
```

---

## Fase 1 — Mini Framing (sem agente)

**O que está mudando?** [Uma frase]

**Por que?**
- [ ] Bug de UX reportado
- [ ] Dado de analytics mostrando problema
- [ ] Pedido de stakeholder com justificativa
- [ ] Melhoria identificada internamente

**Quem é afetado?** [Usuário e contexto]

**Como saberemos que melhorou?** [Métrica ou evidência]

**O que NÃO vai mudar?** [Explícito — evita escopo crescente]

---

## Fase 2 — Design

- `context/global/design-system.md` — uso correto do Copan
- `context/global/brand-voice.md` — se houver copy nova
- `context/local/context.md` — regras específicas do squad

---

## Fase 3 — Critique

**Agente:** `agents/solution-critique.md`

Peça ao agente para focar em:
1. A mudança endereça o problema declarado?
2. Introduz novos problemas de heurística, acessibilidade ou copy?
3. É consistente com o padrão existente no produto e no Copan?

---

## Fase 4 — Handoff Simplificado

Para mudanças pequenas, documente no ticket ou comentário do Figma:

```
MUDANÇA: [O que foi alterado]
MOTIVO: [Por que foi feito assim]
ESTADOS AFETADOS: [Quais estados foram mudados]
COMPORTAMENTO: [Como deve funcionar]
COPY NOVA: [Se houver, o texto final]
TRACKING: [Evento novo ou modificado, se houver]
```

Use `agents/delivery-handoff.md` apenas se a mudança tiver ambiguidade ou novos eventos de analytics.
