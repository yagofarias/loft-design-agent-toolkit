---
name: copan-check
description: >
  Valida se componentes de uma tela ou jornada estão alinhados com o
  Copan (design system da Loft): existência, variantes, tokens, uso correto,
  nomenclatura e instâncias desvinculadas.
---

# Skill: Copan Check

## Propósito

Componentes mal especificados são uma das principais causas de divergência entre design e implementação. Esta skill garante que o que foi desenhado pode ser implementado com o que existe no Copan.

**Fonte de referência:** `context/global/design-system.md` — contém links e referência rápida do Copan. Consulte antes de marcar um componente como inexistente.

**Distinção com `state-coverage`:**
- `copan-check` → o que você *criou* usa os componentes certos? (validação)
- `state-coverage` → quais estados você precisa *criar*? (identificação)

---

## Checklist de Validação por Componente

### 1. Existência no Copan
- [ ] O componente existe no Copan com este nome exato?
- [ ] A variante usada está documentada no Copan?
- [ ] O estado usado (hover, error, disabled) existe no Copan?
- [ ] O componente não está marcado como **deprecated** no Copan?

### 2. Tokens de Design

Tokens cobrem mais do que cor e tipografia — verifique todos:

- [ ] **Cores** — usando tokens de cor, não hex direto?
- [ ] **Tipografia** — usando estilos de texto do Copan, não fonte/tamanho manual?
- [ ] **Espaçamentos** — usando tokens de spacing (4, 8, 12, 16, 24...), não valores arbitrários?
- [ ] **Border-radius** — usando tokens de radius, não px manual?
- [ ] **Sombras/Elevation** — usando tokens de shadow quando aplicável?
- [ ] **Motion/Animação** — usando tokens de duração e easing quando aplicável?

### 3. Instâncias Desvinculadas

Instâncias desvinculadas (detached) são a principal fonte de divergência entre Figma e código.

- [ ] O componente é uma instância do Copan ou foi desvinculado?
- [ ] Se desvinculado: foi necessário? O motivo está documentado?
- [ ] Componentes desvinculados com propriedades modificadas manualmente devem ser tratados como componentes novos — seguir o fluxo de proposta ao time de DS

### 4. Uso Correto

- [ ] O componente está sendo usado para o propósito que foi criado?
- [ ] O contexto de uso é consistente com outros usos do mesmo componente no produto?
- [ ] Um componente de formulário não está sendo usado como elemento de navegação e vice-versa?

### 5. Nomenclatura e Organização

- [ ] O nome do componente no Figma bate com o nome no Copan e no código?
- [ ] Layers e grupos têm nomes descritivos — não "Frame 47" ou "Group 12"?
- [ ] Nomenclatura de variantes segue o padrão do Copan (ex: `size/large`, `state/error`)?

### 6. Responsividade

- [ ] O componente se comporta corretamente nos breakpoints suportados?
- [ ] Variantes mobile existem quando o comportamento difere do desktop?

---

## Identificando Componentes Novos

Quando o Copan não tem o que precisa, documente antes de criar:

```
COMPONENTE NOVO: [Nome proposto]
PROPÓSITO: [Para que serve — em 1 frase]
BASEADO EM: [Componente existente mais próximo, se houver]
DIFERENÇA: [O que este componente faz que o existente não faz]
PRIORIDADE: [Antes do dev / Pode ser adaptado por hora / Pós-lançamento]
RESPONSÁVEL: [Quem propõe ao time de DS]
```

---

## Regra de Decisão

1. **Existe um componente que faz exatamente isso?** → Use-o sem modificação
2. **Existe um componente próximo com uma variante faltando?** → Proponha a variante ao time de DS
3. **Existe um componente próximo mas com uso diferente?** → Componente novo — proponha ao DS
4. **Não existe nada parecido?** → Componente novo + proposta formal ao DS
5. **O componente existe mas está deprecated?** → Use o substituto indicado na documentação do Copan

---

## Auditoria em uma Jornada

| Componente | Nome no Figma | Nome no Copan | Variante | Tokens ok? | Desvinculado? | Status |
|-----------|---------------|---------------|----------|------------|---------------|--------|
| | | | | Sim/Não | Sim/Não | ✅ / ⚠️ / ❌ |
