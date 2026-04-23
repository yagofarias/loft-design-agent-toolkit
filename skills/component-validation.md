---
name: component-validation
description: >
  Framework para validar se componentes de uma tela ou jornada estão
  alinhados com o design system: nomenclatura, variantes, tokens e
  padrões de uso.
---

# Skill: Component Validation

## Propósito

Componentes mal especificados são uma das principais causas de divergência entre design e implementação. Esta skill garante que o que foi desenhado pode ser implementado com o que existe no sistema.

## Checklist de Validação por Componente

### 1. Existência no Design System
- [ ] O componente existe no design system com este nome?
- [ ] A variante usada está documentada?
- [ ] O estado usado existe?

### 2. Tokens de Design
- [ ] Cores estão usando tokens (não valores hexadecimais diretos)?
- [ ] Tipografia usa estilos do sistema?
- [ ] Espaçamentos usam tokens de spacing?

### 3. Uso Correto
- [ ] O componente está sendo usado para o propósito que foi criado?
- [ ] O contexto de uso é consistente com outros usos do mesmo componente?

### 4. Nomenclatura
- [ ] O nome usado no Figma bate com o nome no código?
- [ ] Layers e grupos têm nomenclatura descritiva (não "Frame 47")?

## Identificando Componentes Novos

```
COMPONENTE NOVO: [Nome proposto]
PROPÓSITO: [Para que serve]
BASEADO EM: [Componente existente mais próximo, se houver]
DIFERENÇA: [O que este componente faz que o existente não faz]
PRIORIDADE: [Precisa existir antes do dev / Pode ser adaptado por hora]
RESPONSÁVEL: [Quem vai criar no DS]
```

## Regra de Decisão

1. **Existe um componente que faz exatamente isso?** → Use-o sem modificação
2. **Existe um componente próximo com uma variante faltando?** → Proponha a variante
3. **Existe um componente próximo mas com uso diferente?** → Componente novo
4. **Não existe nada parecido?** → Componente novo + proposta para o DS

## Auditoria em uma Jornada

| Componente usado | Nome no Figma | Nome no DS | Variante | Tokens corretos | Status |
|-----------------|---------------|------------|----------|-----------------|--------|
| | | | | Sim/Não | ✅ OK / ⚠️ Ajustar / ❌ Problema |
