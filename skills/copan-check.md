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

**Referência:** `context/global/design-system.md` — use para verificar uso correto de componentes, tokens e regras de composição.

**Distinção com `state-coverage`:**
- `copan-check` → os componentes usados são os certos? (validação)
- `state-coverage` → quais estados precisam ser desenhados? (identificação)

---

## Passo 0 — Detectar o sistema em uso

Antes de validar qualquer coisa, identifique qual DS está sendo usado. Elementos de pista:
- Cor do botão primário (laranja → Loft, preto → CHL, azul escuro → CredPago, verde → Vista)
- Fonte dos headings (Inter → Loft/Vista, Aeonik → CHL, Uni Neue → CredPago)
- Tom do background secundário (frio `#F2F4F8` → Loft/CredPago/Vista, quente `#F9F3EA` → CHL)

Se for um sistema legado (CHL, CredPago, Vista), aplicar as regras do sistema correspondente em `context/global/design-system.md` → seção *Regras para Critique por Sistema*. Não criticar tokens corretos de um sistema legado como se fossem erros Loft.

---

## Passo 1 — Acessar o design

**Com link do Figma e MCP conectado**, chamar em sequência:

```
figma_get_library_components    → confirmar lista atual de componentes disponíveis
figma_audit_design_system       → auditoria técnica: componentes, tokens, instâncias
figma_check_design_parity       → divergências entre design e implementação
```

> Se `figma_get_library_components` retornar componentes não documentados em `context/global/design-system.md`, eles são provavelmente adições recentes — não marcar como erro. Validar uso com base no nome e contexto.

**Com prints ou descrição:** validar com base no que o designer compartilha, usando `context/global/design-system.md` como referência. Avisar que a validação técnica (tokens, instâncias vinculadas) não é possível sem acesso ao Figma.

---

## Passo 2 — Checklist de validação

### Componentes
- [ ] O componente existe no Copan com este nome? *(se Figma MCP: verificado via `figma_get_library_components`)*
- [ ] A variante/modifier usada está disponível?
- [ ] O componente está sendo usado para o propósito correto? *(ver seção Uso e Decisão em `context/global/design-system.md`)*
- [ ] A instância está vinculada à biblioteca — não foi desvinculada (detached)? *(se Figma MCP: verificado via `figma_audit_design_system`)*
- [ ] O componente não está marcado como deprecated?

Casos de decisão que merecem atenção especial:
- **Dialog vs. Modal vs. Drawer** — o mais comum de ser trocado
- **Chip vs. Tag** — Chip é interativo, Tag é estático
- **Switch vs. Checkbox** — Switch não é para forms de submissão
- **ActionButton vs. Button** — ActionButton para ações sem destaque
- **Tooltip vs. Popover** — Tooltip só para texto simples e não-essencial

### Tokens
- [ ] Cores usam tokens do Copan, não valores hex diretos? *(referência: tabelas de cor em `context/global/design-system.md`)*
- [ ] Tipografia usa estilos de texto do Copan, não fonte/tamanho manual?
- [ ] Espaçamentos seguem a escala do Copan (múltiplos de 8px via tokens inner/layout)?
- [ ] Border-radius, sombras e z-index seguem os tokens — não valores arbitrários?

### Regras de composição
- [ ] Máximo 1 botão primário por viewport?
- [ ] Label de botão em Sentence case, máx. 40 chars, máx. 4 palavras?
- [ ] Labels de formulário estão acima dos campos — não substituídas por placeholder?
- [ ] Erro de formulário substitui o helper text — não empilhados?
- [ ] Ícones sem label têm `title` (aria-label / tooltip)?
- [ ] Todo empty state tem título + ação sugerida?

*(Para regras completas: seção Regras de Composição em `context/global/design-system.md`)*

### Nomenclatura (Figma)
- [ ] Os nomes de layers são descritivos — não "Frame 47" ou "Group 12"?

---

## Quando um componente não existe no Copan

Se o design usar algo que não existe no Copan (confirmado via `figma_get_library_components` ou pela documentação), registrar como proposta antes do handoff:

```
COMPONENTE NOVO: [Nome proposto]
PROPÓSITO: [Para que serve]
BASEADO EM: [Componente existente mais próximo, se houver]
DIFERENÇA: [O que o existente não cobre]
PRIORIDADE: [Antes do dev / Pós-lançamento]
```
