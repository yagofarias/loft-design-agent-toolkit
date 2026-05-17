# Design System — Copan

> **Biblioteca ativa:** `@loft/react-loft` · Tokens: `@loft/tokens-loft` · Ícones: `@loft/react-icons` · Fonte: Inter (CDN própria Loft)

---

## Como usar este arquivo em critiques

Este arquivo é a referência offline do Copan. Use-o para entender conceitos, identificar o componente certo e checar tokens — especialmente em critiques baseadas em imagens.

**Quando o Figma MCP estiver conectado**, consulte também a biblioteca do DS diretamente antes de iniciar qualquer critique:

```
figma_get_library_components   → lista todos os componentes disponíveis hoje (fonte de verdade para novos componentes)
figma_get_design_system_summary → visão geral do estado atual da biblioteca
figma_audit_design_system       → auditoria técnica de uso de componentes no arquivo
figma_check_design_parity       → verifica divergências entre design e implementação
```

**Por quê:** este documento pode estar desatualizado. Novos componentes são criados. Os conceitos, tokens e regras documentados aqui permanecem válidos — mas sempre use `figma_get_library_components` para confirmar se existe um componente mais recente que resolve o problema antes de apontar ausência.

---

## Componentes — Uso e Decisão

> Referência de decisão de design: *qual componente usar e quando não usar*. Para props de implementação, consulte a documentação oficial do Copan.

### Accordion / Collapse
- **Accordion:** Expandir/recolher conteúdo em FAQs e menus. Header fixo com estilo pré-definido.
- **Collapse:** Versão genérica quando o header precisa ser um ReactNode customizado (logo, componente composto).
- **Regra:** use Accordion por padrão; use Collapse quando o trigger precisa de estrutura própria.

### ActionButton
- Ações contextuais sem chamar atenção — tabelas, cards, listas. Leva ícone sem label visível.
- **Modifiers:** `none` (default) / `inverted` (fundo colorido) / `fill` (fundo sólido, sobreposição).
- **Não usar quando:** a ação precisa de destaque → usar Button.

### Avatar
- Representação de pessoa, empresa ou produto. Suporta imagem, ícone ou iniciais geradas automaticamente.
- **Tamanhos:** `sm` / `md` / `lg` / `xl`.

### Button
- Ação principal de qualquer fluxo. `primary` chama mais atenção; `secondary` para ações de apoio.
- **Variantes:** `primary` / `secondary` — referem-se à importância, não a cor.
- **Modifiers:** `none` / `inverted` (sobre fundo colorido) / `premium`.
- **Regras de design:** Sentence case, máx. 40 chars, máx. 4 palavras.
- **Não usar quando:** a ação não requer destaque → usar ActionButton.
- **Ver também:** Regras de Composição → hierarquia de botões.

### Card
- Container para agrupar conteúdo relacionado. Pode ser clicável.
- Suporta title, subtitle, overline (Tag/Typography/Icon), imagem e ação.

### Checkbox / Radio / Switch
- **Checkbox:** seleção múltipla e independente. Suporta `indeterminate`.
- **Radio:** seleção única mutuamente exclusiva. Exige `name` para agrupamento.
- **Switch:** toggle boolean (ativar/desativar). **Não usar em formulários de submissão** → usar Checkbox.

### Chip / Tag
- **Chip:** interativo — seleção, filtros, ativar/desativar. Suporta `selected`, `disabled`.
- **Tag:** apenas informativa, sem interação. Usa `state` semântico (positive/warning/negative/informative/neutral) ou `modifier` decorativo.

### Dialog / Modal / Drawer
- **Dialog:** confirmações rápidas e bloqueantes. Conteúdo simples, ações explícitas (primary/secondary/tertiary).
- **Modal:** conteúdo extenso ou complexo (formulários, imagens). Não bloqueante por padrão.
- **Drawer:** conteúdo contextual deslizante. Menos invasivo — o usuário não precisa sair da tarefa.
- **Ver também:** Regras de Composição → quando usar cada um.

### FeedbackBanner / Snackbar
- **FeedbackBanner:** mensagem persistente e proeminente. Para estados que o usuário precisa notar.
- **Snackbar:** notificação efêmera sobre resultado de ação. Mínimo 5s de timeout.
- **Ver também:** Regras de Composição → hierarquia de feedback.

### FloatingActionButton (FAB)
- Atalho para ação principal da interface. Sempre primário, sempre canto inferior direito.
- **Não usar quando:** há múltiplos botões primários na mesma tela.

### Icon
- Ícones da `@loft/react-icons` (Material Symbols).
- **Tamanhos:** `sm` (apoio) / `md` (default) / `lg` / `xl` (warnings, empty states).
- **Regra:** ícone sem label visível exige `title` (vira tooltip + a11y).

### Link
- Navegação para outro local. `primary` / `secondary`. `quiet` remove sublinhado — evitar em links essenciais.

### Popover
- Elemento flutuante posicionado relativo a um trigger. Usado para menus, tooltips ricos, sub-painéis.
- Diferença do Tooltip: aceita conteúdo arbitrário (não só texto).

### Select / TextField / TextArea
- **Select:** quando o espaço é limitado e as opções são fixas.
- **TextField:** entrada de texto de linha única. Inclui PatternField (máscaras) e NumericField (decimais).
- **TextArea:** entrada multi-linhas para conteúdo extenso.
- **Regra de forms:** label sempre acima do campo. Estado de erro substitui o helper text — nunca empilhe os dois.

### Slider
- Ajuste de valor contínuo em intervalo (preço, m², porcentagem). Modo único ou range.

### StatusLight
- **`state`** (semântico): neutral / informative / positive / warning / negative.
- **`modifier`** (decorativo, até 9 categorias): para visualização de dados categóricos.
- **Regra:** `state` para significado; `modifier` para categorias visuais sem peso semântico.

### Table
- Organização eficiente de dados tabulares. Suporta `stickyHeader`, `sortable`, `loading`.

### Tabs
- Organiza conteúdo em seções relacionadas. Não usar para navegação entre páginas — usar MenuItem/Submenu.

### Tooltip
- Informações opcionais e simples sobre um elemento.
- **Não usar quando:** a informação é essencial → incorporar no layout ou usar Popover.

### Typography
- Estilos: `hero`, `h1`–`h4`, `subtitle`, `paragraph-lg/bold`, `paragraph-md/bold` (default), `paragraph-sm/bold`, `caption`, `overline`, `label-sm`, `label-md`.
- Cor por `variant` (primary/secondary/inherit) e `modifier` (highlight/placeholder/inverted/premium).

---

## Foundation — Tokens

### Cores

#### Background
| Token | Cor | Uso |
|---|---|---|
| `color.background.primary` | `#FFFFFF` | Fundo base de todas as superfícies |
| `color.background.secondary` | `#F2F4F8` | Destaque leve |
| `color.background.tertiary` | `#DDE1E6` | Ainda mais destaque |
| `color.background.inverted` | `#191F23` | Alto contraste |
| `color.background.backdrop` | `#191F2380` (50%) | Modais / Dialogs |
| `color.background.brand` | `#FF774A` | Cor primária da marca (laranja) |
| `color.background.premium` | `#BD7B00` | Produtos premium |

#### Feedback
| Token | Cor | Uso |
|---|---|---|
| `color.feedback.positive.main` | `#20A483` | Aprovado, sucesso |
| `color.feedback.warning.main` | `#FFA600` | Ação necessária, pendente |
| `color.feedback.negative.main` | `#CE4242` | Erros, ações destrutivas |
| `color.feedback.informative.main` | `#387BA8` | Informativo, ativo |
| `color.feedback.neutral.main` | `#697077` | Arquivado, pausado, encerrado |
| `.light` de cada estado | — | Apenas para fundos de badges/tags |

#### Texto
| Token | Cor | Uso |
|---|---|---|
| `color.text.primary` | `#191F23` | Conteúdo principal |
| `color.text.secondary` | `#697077` | Textos de apoio |
| `color.text.placeholder` | `#878D96` | Apenas placeholders de form |
| `color.text.highlight` | `#FF774A` | Destaque, cor da marca |
| `color.text.inverted` | `#FFFFFF` | Sobre fundos escuros |
| `color.text.premium` | `#BD7B00` | Títulos premium |

#### Interação
| Token | Cor | Uso |
|---|---|---|
| `color.interaction.primary.main` | `#F56738` | Fundo botão primário |
| `color.interaction.primary.hover` | `#D94616` | Hover / pressed |
| `color.interaction.disabled` | `#A2A9B0` | Estado disabled universal |
| `color.interaction.selectors` | `#20A483` | Checkbox, radio, switch |
| `color.interaction.link` | `#20A483` | Links |

#### Separadores
| Token | Cor |
|---|---|
| `color.separator.main` | `#697077` |
| `color.separator.light` | `#C1C7CD` |
| `color.separator.heavy` | `#191F23` |

---

### Tipografia

**Fonte:** Inter (fallback Arial, sans-serif)

| Estilo | Desktop | Mobile | Peso |
|---|---|---|---|
| `hero` | 64px / lh 80px | 48px / lh 60px | 700 |
| `h1` | 56px / lh 68px | 40px / lh 48px | 700 |
| `h2` | 48px / lh 60px | 32px / lh 40px | 700 |
| `h3` | 32px / lh 40px | 24px / lh 32px | 700 |
| `h4` | 24px / lh 32px | 18px / lh 28px | 700 |
| `subtitle` | 18px / lh 28px | 16px / lh 24px | 700 |
| `paragraph-lg` | 18px / lh 28px | 16px / lh 24px | 400 |
| `paragraph-md` (default) | 16px / lh 24px | 14px / lh 24px | 400 |
| `paragraph-sm` | 14px / lh 24px | 12px / lh 20px | 400 |
| `caption` | 12px / lh 20px | 12px / lh 20px | 400 |
| `overline` | 10px / lh 16px, UPPERCASE | idem | 700 |
| `label-md` | 16px / lh 24px | idem | 400 |
| `label-sm` | 14px / lh 24px | idem | 400 |

---

### Espaçamento

Escala base de 8px. Dois grupos:

- **Inner** (internos de componentes): `base` 4px → `base14` 56px
- **Layout** (entre componentes/seções): `base` 8px → `base15` 120px

Nunca use valores manuais de pixel — sempre use um token de spacing.

---

### Grid Responsivo

| Breakpoint | Colunas | Margin | Gutters |
|---|---|---|---|
| `xs` (320–575px) | 4 | 24px | 16px |
| `sm` (576–767px) | 8 | 24px | 16px |
| `md` (768–959px) | 8 | 40px | 16px |
| `lg` (960–1199px) | 12 | 40px | 16px |
| `xl` (1200–1439px) | 12 | 40px | 32px |
| `xxl` (1440px+) | 12 | 64px | 32px |

---

### Z-Index (camadas)

| Token | Valor | Elemento |
|---|---|---|
| `zindex.fab` | 100 | FloatingActionButton |
| `zindex.navigation` | 200 | Header/Nav |
| `zindex.popover` | 300 | Popover, DropdownMenu |
| `zindex.backdrop` | 500 | Backdrop de modal/drawer |
| `zindex.drawer` | 510 | Drawer |
| `zindex.modal` | 520 | Modal |
| `zindex.dialog` | 530 | Dialog |
| `zindex.snackbar` | 600 | Snackbar |
| `zindex.tooltip` | 700 | Tooltip |

---

## Sistemas Legados

> ⚠️ CHL, CredPago e Vista foram descontinuados e não recebem atualizações. Marcar com **[LEGADO]** em qualquer critique que identifique uso desses sistemas.

### Tabela Comparativa — Identidade de Marca

| Aspecto | **Loft (ativo)** | CHL [legado] | CredPago [legado] | Vista [legado] |
|---|---|---|---|---|
| **Biblioteca** | `@loft/react-loft` | `@loft/react-chl` | `@loft/react-credpago` | `@loft/react-vista` |
| **Fonte headings** | Inter 700 | **Aeonik 400** | **Uni Neue 700** | Inter 700 |
| **Fonte body** | Inter | Inter | **Roboto** | Inter |
| **Cor da marca** | 🟠 `#FF774A` laranja | ⚫ `#262626` preto | 🔵 `#003863` azul escuro | 🟢 `#1A846A` verde escuro |
| **Botão primário** | 🟠 `#F56738` | ⚫ `#262626` | 🔵 `#003863` | 🟢 `#1A846A` |
| **Selectors** | 🟢 `#20A483` | ⚫ `#262626` | 🔵 `#0084B4` | 🟢 `#1A846A` |
| **Links** | 🟢 `#20A483` | ⚫ `#262626` | 🔵 `#0084B4` | 🟢 `#1A846A` |
| **Background secundário** | Frio `#F2F4F8` | **Quente `#F9F3EA`** | Frio `#F2F4F8` | Frio `#F2F4F8` |
| **Estilo h0** | ❌ não existe | ❌ | ✅ só em hero/marketing | ❌ |

---

## Regras para Critique por Sistema

**Copan Loft (ativo):**
- Botões primários: laranja `#F56738` — não verde, azul ou preto
- Headings: Inter 700 — não Aeonik, Uni Neue ou Roboto
- Background secundário: frio `#F2F4F8` — não quente
- Selectors (checkbox/radio/switch): verdes `#20A483`
- Destaque/highlight: laranja `#FF774A`
- Labels de botão: Sentence case, máx. 40 chars, máx. 4 palavras

**CHL [legado]:**
- Headings: Aeonik peso 400 — não bold, não Inter
- Botão primário: preto `#262626`
- Background secundário: quente `#F9F3EA`
- Mistura de tokens Loft em interface CHL = inconsistência de tema

**CredPago [legado]:**
- Headings: Uni Neue — não Inter, não Roboto
- Body: Roboto — não Inter
- Marca: azul cerulean `#003863`
- `h0` só em páginas de marketing/hero

**Vista [legado]:**
- Marca: verde `#1A846A` — qualquer elemento laranja = inconsistência
- Tipografia idêntica ao Loft em tamanhos — diferença só na cor

---

## Regras de Composição

Convenções de indústria que o Copan não documenta explicitamente, mas cuja violação aparece com frequência em critiques.

### Hierarquia de botões
- **Máximo 1 botão primário por viewport.** Múltiplos primários anulan a hierarquia visual.
- Exceção legítima: hero sections com CTA duplicado (acima e abaixo do fold) — mas devem ser idênticos.
- Botão `full-width` em mobile não quebra essa regra — contexto muda, não a hierarquia.

### Modal vs. Dialog vs. Drawer
| Situação | Componente correto |
|---|---|
| Confirmação de ação destrutiva ou crítica (curta, bloqueante) | Dialog |
| Formulário, imagem, conteúdo longo que precisa de foco total | Modal |
| Informações contextuais sem interromper a tarefa principal | Drawer |
| Informação adicional sobre um item específico na tela | Drawer ou Popover |

### Formulários
- Label sempre **acima** do campo — nunca dentro (placeholder) como substituto do label.
- Estado de erro **substitui** o helper text — nunca empilhe mensagem de erro + helper text.
- Campos obrigatórios: marcar com `*` e explicar a convenção uma vez no topo do form.
- Desabilitar o botão de submit não é substituto de validação com feedback de erro.

### Hierarquia de feedback
Do mais ao menos invasivo:
1. **Dialog** — para erros que bloqueiam o fluxo e exigem decisão do usuário
2. **FeedbackBanner** — para estados que persistem e o usuário precisa notar antes de continuar
3. **Snackbar** — para confirmações efêmeras de ações já concluídas (mín. 5s)
4. **Inline** (erro no campo) — para erros de validação de formulário

Não use Snackbar para erros críticos — o usuário pode não ver antes de fechar.

### Tipografia
- **1 H1 por página** — sem exceção.
- Não pule níveis hierárquicos (H1 → H3 sem H2 intermediário).
- Caption e overline nunca são o único texto em uma seção — sempre texto de apoio.
- Não use overline em mais de 2 ocorrências por tela — perde valor de destaque.

### Ícones sem label
- Todo ícone sem texto visível exige `title` no Copan (equivale a aria-label + tooltip).
- Em contextos críticos (ação destrutiva, navegação principal), prefira ícone + label textual.

### Empty states
- Todo estado vazio precisa de: ilustração ou ícone, título explicativo, e ação sugerida (quando aplicável).
- Não deixe uma tela em branco sem orientação — é o pior cenário para o usuário.
