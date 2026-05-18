# Start From Scratch

Use quando: novo produto, nova feature de médio ou grande porte, ou quando não existe nenhum artefato anterior sobre o problema.

## Fluxo completo

```
[Brief / Ideia bruta]
        ↓
    /framing
        ↓
  [Design Doc] ← gate 1
        ↓
  /research-plan  ← se houver hipóteses a validar
        ↓
  /solution-craft
        ↓
    (design no Figma)
        ↓
    /critique
        ↓
    /handoff
        ↓
  [Pronto para dev] ← gate final
```

---

## Fase 0 — Contexto do squad

Antes de qualquer agente, confirme que o contexto local está preenchido:

- [ ] `context/local/context.md` — regras de negócio, terminologia, constraints
- [ ] `context/local/personas.md` — perfis de usuário e jobs-to-be-done
- [ ] `context/local/competitors.md` — mapeamento competitivo

Se não estiver preenchido, rode `/context-setup` primeiro.

---

## Fase 1 — Framing

**Comando:** `/framing`

Passe como input o brief, PRD, RFC ou descrição do problema. O agente transforma em um Design Doc estruturado.

**Gate 1 — antes de avançar:**
- [ ] O problema descreve quem sente a dor, o quanto custa e por que resolver agora?
- [ ] O objetivo está em termos de impacto — não de entregável?
- [ ] As métricas de sucesso são mensuráveis e têm baseline?

---

## Fase 2 — Pesquisa (quando necessário)

**Comando:** `/research-plan`

Use quando o Design Doc tiver hipóteses críticas que precisam ser validadas antes de ir para a solução. O agente extrai os `[A VALIDAR:]` do design-doc e monta um plano de pesquisa executável.

Pule esta fase se as hipóteses já estiverem validadas ou o prazo não comportar pesquisa.

---

## Fase 3 — Solução

**Comando:** `/solution-craft`

Mapeia fluxos, estados, edge cases e artefatos de tangibilização a partir do Design Doc.

---

## Fase 4 — Design (Figma)

Use o output do `/solution-craft` como referência. Para cada tela:

- Consulte `context/global/design-system.md` para componentes do Copan
- Implemente todos os estados mapeados
- Documente no Figma decisões que não sejam óbvias

---

## Fase 5 — Critique

**Comando:** `/critique`

Aceita link do Figma ou prints. Cobre usabilidade, composição visual, acessibilidade, estados, copy e Copan em um único relatório.

**Gate final — antes de passar para dev:**
- [ ] Nenhum problema de severidade 4?
- [ ] Problemas de severidade 3 têm plano de resolução?
- [ ] O design resolve o problema declarado no Design Doc?

---

## Fase 6 — Handoff

**Comando:** `/handoff`

Gera a spec de analytics e valida se o design está completamente documentado para o dev.
