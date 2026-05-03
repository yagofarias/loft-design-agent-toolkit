---
version: "2.0"
agent: journey-builder
status: "[Rascunho | Em revisão | Aprovado]"
---

# Journey Spec

**Projeto:** [Nome]
**Jornada:** [Nome descritivo — ex: "Análise de fiança pelo gestor da imobiliária"]
**Designer:** [Nome]
**Data:** [DD/MM/AAAA]
**Figma:** [Link — frame ou página específica]
**Design Doc:** [Link para templates/design-doc.md]

---

## Sumário

*O que esta jornada entrega no contexto do projeto.*

| Campo | Valor |
|-------|-------|
| Objetivo desta jornada | [O que o usuário consegue fazer ao completar este fluxo — conecte com o objetivo do design-doc] |
| Usuário primário | [Persona — quem executa este fluxo] |
| Ponto de entrada | [De onde o usuário chega — tela anterior, notificação, link direto] |
| Ponto de saída | [O que define que a jornada foi concluída com sucesso] |
| Plataformas | [Mobile / Web / Ambos — e se há diferença de comportamento] |
| Telas no happy path | [N telas] |
| Total de estados mapeados | [N estados] |

---

## Pré-condições

*O que precisa ser verdade para o usuário chegar ao ponto de entrada desta jornada.*

- [ex: usuário autenticado com perfil de gestor]
- [ex: ao menos uma proposta de locação com status "aguardando análise"]
- [ex: imobiliária com Loft/Fiança Aluguel ativo]

*Se uma pré-condição não for satisfeita, o que acontece? Descreva o estado de bloqueio ou redirecionamento.*

---

## Fluxo Principal (Happy Path)

*O caminho ideal sem erros, desvios ou interrupções. Documente do ponto de entrada ao ponto de saída.*

```
ENTRADA: [Como o usuário chega — ex: clica em "Analisar" na listagem de propostas]

PASSO 1: [Nome descritivo da tela ou etapa]
  Usuário vê: [Conteúdo principal exibido]
  Pode fazer: [Ações disponíveis]
  Para avançar: [O que dispara o próximo passo]
  → PASSO 2

PASSO 2: [Nome]
  Usuário vê: [...]
  Pode fazer: [...]
  Para avançar: [...]
  → SE [condição A]: PASSO 3A
  → SE [condição B]: PASSO 3B

PASSO 3A: [Nome — ramo A]
  ...
  → SAÍDA

PASSO 3B: [Nome — ramo B]
  ...
  → SAÍDA

SAÍDA: [Estado final — o que o usuário vê e o que acontece no sistema]
```

---

## Fluxos Alternativos

*Caminhos válidos que divergem do happy path sem serem erros — o usuário faz escolhas diferentes ou chega sem as condições ideais. Estes NÃO são edge cases: são fluxos que o design precisa contemplar explicitamente.*

### [Nome do fluxo alternativo — ex: Usuário cancela a análise no meio]

**Gatilho:** [O que leva o usuário para este caminho]
**Fluxo:**
```
PASSO X do happy path
  → Usuário clica em [Cancelar / Voltar / Sair]
  → [O que acontece — confirmação? dados salvos? redirecionamento?]
  → SAÍDA ALTERNATIVA: [Estado final]
```
**Estado de saída:** [Onde o usuário termina e o que o sistema fez com os dados parciais]

---

### [Nome do fluxo alternativo — ex: Usuário sem permissão suficiente]

**Gatilho:** [Condição que gera este caminho]
**Fluxo:**
```
[Descrição do que o usuário vê e pode fazer]
```

---

## Inventário de Telas e Estados

*Todos os estados que precisam ser desenhados. P0 = obrigatório antes do handoff. P1 = necessário antes do lançamento. P2 = pode ser iterado depois.*

*Para cada tela, cubra no mínimo: Default, Loading, Erro e Vazio (quando aplicável).*

| Tela / Componente | Estado | Gatilho | Conteúdo principal | Ação disponível | Prioridade |
|-------------------|--------|---------|-------------------|-----------------|-----------|
| [Nome da tela] | Default | — | [O que aparece] | [O que o usuário pode fazer] | P0 |
| [Nome da tela] | Loading | Aguardando resposta da API | Skeleton / spinner | Nenhuma | P0 |
| [Nome da tela] | Erro — sistema | API retorna 4xx/5xx | [Mensagem + CTA de retry] | Tentar novamente | P0 |
| [Nome da tela] | Erro — validação | Usuário envia dados inválidos | [Mensagem inline no campo] | Corrigir e reenviar | P0 |
| [Nome da tela] | Vazio | Nenhum dado disponível | [Empty state com orientação] | [CTA contextual] | P0 |
| [Nome da tela] | Sucesso / Confirmação | Ação concluída com sucesso | [Feedback claro] | [Próximo passo] | P0 |
| [Nome da tela] | Permissão negada | Usuário sem acesso | [Explicação + alternativa] | — | P1 |
| [Nome da tela] | Offline | Sem conexão | [Mensagem + o que foi salvo] | Recarregar | P1 |

*Adicione ou remova linhas conforme a jornada. Para telas críticas ou complexas, adicione notas inline abaixo da tabela descrevendo o comportamento específico.*

---

## Copies e Conteúdo

*Todos os textos finalizados da jornada. Copies não finalizadas no spec são a principal causa de perguntas durante o desenvolvimento.*

*Se um texto ainda não foi definido, escreva `[A DEFINIR]` — não deixe em branco.*

### Textos de interface

| Elemento | Tela | Copy final |
|---------|------|-----------|
| Título da página | [Tela] | [Texto exato] |
| Subtítulo / descrição | [Tela] | [Texto exato] |
| Label do campo [X] | [Tela] | [Texto exato] |
| Placeholder do campo [X] | [Tela] | [Texto exato] |
| Texto de ajuda / hint | [Tela] | [Texto exato] |
| CTA primário | [Tela] | [Texto exato] |
| CTA secundário | [Tela] | [Texto exato] |
| Mensagem de confirmação | [Tela] | [Texto exato] |

### Mensagens de erro

*Uma linha por regra de validação. O dev não deve inventar mensagens de erro.*

| Campo / Situação | Regra | Mensagem para o usuário |
|-----------------|-------|------------------------|
| [Campo ou situação] | [Ex: campo obrigatório vazio] | [Texto exato da mensagem] |
| [Campo ou situação] | [Ex: formato inválido] | [Texto exato da mensagem] |
| [Erro de sistema] | [Ex: timeout da API] | [Texto exato da mensagem] |

### Empty states

| Tela | Situação | Título | Descrição | CTA |
|------|---------|--------|-----------|-----|
| [Tela] | [Quando aparece] | [Título do empty state] | [Descrição opcional] | [Botão ou link — se houver] |

---

## Comportamentos Especiais

*Documente apenas o que não é óbvio olhando os mockups. Animações vagas ("fazer smooth") causam implementações inconsistentes.*

### Animações e Transições

| Elemento | Tipo | Duração | Easing | Gatilho | Comportamento |
|---------|------|---------|--------|---------|--------------|
| [Ex: modal de confirmação] | Fade in | 200ms | ease-out | Click no CTA | Aparece com opacity 0→1 |
| [Ex: toast de sucesso] | Slide + fade | 300ms | ease-in-out | Ação concluída | Desliza de baixo, some após 3s |
| [Ex: skeleton loading] | Pulse | 1.5s loop | ease-in-out | Estado loading | Pulso de opacidade 0.4→0.8 |

*Se não há animações especiais além do padrão do Copan, escreva: "Usar padrões de animação do Copan — sem comportamentos customizados."*

### Comportamento Mobile

*Documente apenas onde mobile diverge de desktop. Se o comportamento é idêntico, não precisa repetir.*

- [Ex: "Na tela X, o CTA fica fixo no bottom no mobile, mas inline no desktop"]
- [Ex: "Swipe left na listagem abre o menu de ações no mobile"]
- [Ex: "Nenhuma divergência mobile/desktop nesta jornada"]

### Gestos

*Preencha apenas se há gestos customizados além de tap/scroll.*

| Gesto | Elemento | Comportamento |
|-------|---------|--------------|
| [Ex: swipe left] | [Item da lista] | [Revela ações rápidas] |

---

## Acessibilidade

*O que o dev precisa saber além de "seguir WCAG". Foco no que não é óbvio nos mockups.*

### Ordem de foco (Tab order)

*Liste a ordem em que os elementos devem receber foco por teclado na tela principal. Essencial para formulários e modais.*

| Posição | Elemento | Tela |
|---------|---------|------|
| 1 | [Ex: campo Nome completo] | [Tela de formulário] |
| 2 | [Ex: campo CPF] | [Tela de formulário] |
| 3 | [Ex: botão Continuar] | [Tela de formulário] |

### Navegação por teclado

*Componentes complexos que precisam de especificação de keyboard behavior.*

| Componente | Tecla | Comportamento esperado |
|-----------|-------|----------------------|
| [Ex: dropdown de status] | Enter / Space | Abre o dropdown |
| [Ex: dropdown de status] | Esc | Fecha sem selecionar |
| [Ex: dropdown de status] | ↑ / ↓ | Navega entre opções |
| [Ex: modal] | Esc | Fecha o modal |
| [Ex: modal] | Tab | Foco restrito dentro do modal (focus trap) |

### Anotações para screen reader

*O que deve ser anunciado em elementos que não têm texto visível ou cujo texto visual não é suficiente.*

| Elemento | O que o screen reader anuncia | Nota |
|---------|------------------------------|------|
| [Ex: ícone de status "aprovado"] | "Proposta aprovada" | aria-label no ícone |
| [Ex: loading spinner] | "Carregando análise, aguarde" | aria-live region |
| [Ex: campo com contador de caracteres] | "[N] de 200 caracteres" | aria-describedby |

*Se não há casos especiais, escreva: "Usar marcação semântica padrão do Copan — sem ARIA customizado."*

---

## Edge Cases

*Situações incomuns, técnicas ou de baixa probabilidade que ainda precisam de tratamento. Diferente dos fluxos alternativos, estes são cenários que o usuário não controla.*

| # | Situação | Probabilidade | Impacto | Tratamento proposto | Prioridade |
|---|----------|--------------|---------|---------------------|-----------|
| 1 | [Ex: sessão expira no meio do formulário] | Baixa | Alto | [Salvar rascunho + redirecionar para login com mensagem] | P0 |
| 2 | [Ex: upload de documento excede o limite] | Média | Médio | [Mensagem de erro inline com limite e formatos aceitos] | P0 |
| 3 | [Ex: usuário submete formulário duplo-clicando] | Média | Médio | [Desabilitar botão após primeiro click + loading state] | P1 |

---

## Dados e Dependências

*O que cada tela precisa do backend e o que depende de outro squad ou sistema.*

### Requisitos de dados

| Tela / Componente | Dado necessário | Origem | Comportamento quando indisponível |
|------------------|----------------|--------|----------------------------------|
| [Nome da tela] | [Ex: dados do inquilino] | API /locacao/inquilinos | [Loading → erro com retry] |
| [Nome da tela] | [Ex: histórico de análises] | API /fianca/historico | [Campo oculto — não é bloqueante] |

### Dependências externas

| Dependência | Tipo | Responsável | Bloqueante para handoff? | Status |
|-------------|------|-------------|--------------------------|--------|
| [Ex: endpoint de análise de crédito] | API Backend | Squad Crédito | ✅ Sim | [Confirmado / A confirmar] |
| [Ex: componente de upload do Copan] | Design System | Time DS | ⚠️ Não | [Existe mas precisa nova variante] |
| [Ex: permissões de gestor vs. corretor] | Auth / Backend | Squad Plataforma | ✅ Sim | [A confirmar] |

---

## Dúvidas em Aberto

*O que ainda precisa ser respondido antes que o dev possa implementar sem adivinhar.*

| # | Dúvida | Impacto se não respondida | Responsável | Prazo |
|---|--------|--------------------------|-------------|-------|
| 1 | [Pergunta específica] | [O que o dev vai precisar adivinhar] | [Nome] | [Data] |
