---
name: copan-check
description: >
  Valida se componentes e tokens usados no design estão alinhados com o
  Copan (design system da Loft). O designer pode compartilhar um link do
  Figma ou prints com contexto para a validação.
---

# Skill: Copan Check

## Propósito

Garantir que o design usa os componentes e tokens corretos do Copan antes do handoff. Divergências aqui causam retrabalho na implementação.

**Como o agente valida:**
- Com **link do Figma**: acessa o design via Figma MCP quando disponível e verifica diretamente
- Com **prints ou descrição**: valida com base no que o designer compartilha

**Distinção com `state-coverage`:**
- `copan-check` → os componentes usados são os certos? (validação)
- `state-coverage` → quais estados precisam ser desenhados? (identificação)

---

## O que verificar

### Componentes
- [ ] O componente existe no Copan com este nome?
- [ ] A variante usada está disponível no Copan?
- [ ] O componente está sendo usado para o propósito correto?
- [ ] A instância está vinculada à biblioteca — não foi desvinculada (detached)?
- [ ] O componente não está marcado como deprecated?

### Tokens
- [ ] Cores usam tokens do Copan, não valores hex diretos?
- [ ] Tipografia usa estilos de texto do Copan, não fonte/tamanho manual?
- [ ] Espaçamentos seguem a escala do Copan, não valores arbitrários?
- [ ] Border-radius, sombras e outros tokens visuais seguem o Copan?

### Nomenclatura
- [ ] Os nomes de layers são descritivos — não "Frame 47" ou "Group 12"?

---

## Quando um componente não existe no Copan

Se o design usar algo que não existe no Copan, registrar como proposta antes do handoff:

```
COMPONENTE NOVO: [Nome proposto]
PROPÓSITO: [Para que serve]
BASEADO EM: [Componente existente mais próximo, se houver]
DIFERENÇA: [O que o existente não cobre]
PRIORIDADE: [Antes do dev / Pós-lançamento]
```
