---
name: quick-product-change
description: >
  Playbook acelerado para mudanças pequenas e incrementais em produto
  existente. Pula fases de framing extenso e foca em critique e handoff.
---

# Playbook: Quick Product Change

Use quando: Mudança pontual em feature existente, ajuste de copy, correção de UX, ou melhoria incremental com escopo bem definido.

**Não use quando:** A mudança afeta fluxos inteiros, muda a arquitetura de informação, ou envolve componentes novos significativos.

## Decisão Rápida de Escopo

Responda:

1. A mudança afeta mais de 3 telas? → Se sim, use `start-from-scratch`
2. A mudança muda como o usuário completa uma tarefa principal? → Se sim, use `start-from-scratch`
3. Precisa de componentes novos que não existem no DS? → Se sim, consulte o time de DS

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
  DS COPY REVIEW (se houver copy nova)
        ↓
   DEV HANDOFF
```

---

## Fase 1 — Mini Framing (sem agente)

**O que está mudando?**
[Uma frase]

**Por que está mudando?**
- [ ] Bug de UX reportado por usuário
- [ ] Dado de analytics mostrando problema
- [ ] Pedido de stakeholder com justificativa clara
- [ ] Melhoria identificada internamente

**Quem é afetado?** [Usuário e contexto]

**Como saberemos que melhorou?** [Métrica ou evidência]

**O que NÃO vai mudar?** [Explícito — evita escopo crescente]

---

## Fase 2 — Design

Referências obrigatórias:
- `context/design-system-tokens.md`
- `context/brand-voice.md` (se houver copy nova)

---

## Fase 3 — Critique Focado

**Agente:** `agents/solution-critique.md`

Peça ao agente para focar em:
1. A mudança endereça o problema declarado?
2. Introduz novos problemas de heurística?
3. É consistente com o padrão existente no produto?

---

## Fase 4 — Handoff Simplificado

Documente no ticket ou comentário do Figma:

```
MUDANÇA: [O que foi alterado]
MOTIVO: [Por que foi feito assim]
ESTADOS AFETADOS: [Quais estados foram mudados]
COMPORTAMENTO: [Como deve funcionar]
COPY NOVA: [Se houver, o texto final]
TRACKING: [Se algum evento precisa ser adicionado ou modificado]
```
