---
name: user-flows
description: >
  Framework para estruturar e documentar fluxos de design em texto.
  Cobre happy path, fluxos alternativos, fluxos de erro e fluxos com
  múltiplos atores. Produz input direto para o journey-spec.md.
---

# Skill: User Flows

## Propósito

Um fluxo bem estruturado em texto resolve mais problemas do que um diagrama visual sem documentação. Forçar o fluxo para texto expõe gaps que o Figma esconde — passos implícitos, decisões não documentadas, estados não tratados.

**Output desta skill:** input estruturado para `templates/journey-spec.md`

---

## Os Três Tipos de Fluxo

Todo fluxo completo precisa dos três. Documente em sequência.

### 1. Happy Path
O caminho ideal — sem erros, sem desvios, usuário faz o que foi previsto.
Documente este primeiro. Sem happy path claro, os outros não fazem sentido.

### 2. Fluxos Alternativos
Caminhos válidos que divergem do happy path sem serem erros. O usuário faz escolhas diferentes ou chega sem as condições ideais.

Exemplos:
- Usuário cancela no meio do processo
- Usuário não tem permissão suficiente e é redirecionado
- Usuário escolhe uma opção diferente no passo 3
- Usuário retorna ao passo anterior via "voltar"

### 3. Fluxos de Erro
O que acontece quando algo falha — API, validação, timeout, sessão expirada.

Exemplos:
- Análise de crédito retorna erro do sistema
- Upload de documento falha
- Sessão expira durante preenchimento de formulário
- Usuário tenta submeter com dados inválidos

> Para cada passo do happy path, pergunte: *o que acontece se o usuário fizer algo errado aqui?* Essa pergunta no nível do fluxo custa nada. No nível da implementação custa muito.

---

## Anatomia de um Fluxo

- **Ponto de entrada** — De onde o usuário chega (notificação, menu, link, redirect)
- **Ator(es)** — Quem executa o fluxo. Em B2B pode ser mais de um perfil
- **Pré-condição** — O que precisa ser verdade para o fluxo começar
- **Passos** — Sequência de telas, ações e estados
- **Decisões** — Pontos onde o fluxo se bifurca com base em input ou estado
- **Transições** — O gatilho que move de um passo para outro
- **Ponto de saída** — Onde o fluxo termina (sucesso, abandono, redirecionamento)

---

## Formato de Documentação

### Happy Path

```
FLUXO: [Nome descritivo — ex: "Gestor analisa proposta de fiança"]
ATOR: [Quem executa — ex: "Gestor da imobiliária"]
ENTRADA: [De onde chega — ex: "Notificação de nova proposta"]
PRÉ-CONDIÇÃO: [O que precisa ser verdade — ex: "Usuário autenticado como gestor"]

PASSO 1: [Nome pelo que o usuário faz, não pelo que o sistema mostra]
  O usuário vê: [Conteúdo principal]
  Pode fazer: [Ações disponíveis]
  Para avançar: [O gatilho explícito]
  → PASSO 2

PASSO 2: [Nome]
  O usuário vê: [...]
  Pode fazer: [...]
  → SE [condição A]: PASSO 3A
  → SE [condição B]: PASSO 3B

SAÍDA SUCESSO: [Estado final — o que aconteceu no sistema + o que o usuário vê]
```

### Fluxos Alternativos

```
FLUXO ALTERNATIVO: [Nome — ex: "Gestor cancela análise"]
GATILHO: [O que leva o usuário para este caminho — ex: "Clica em 'Cancelar' no PASSO 2"]
DIVERGE DO HAPPY PATH EM: [Passo N]

PASSO N → [O que acontece]
  → SAÍDA ALTERNATIVA: [Estado final]

DADOS: [O que foi salvo / perdido / descartado]
```

### Fluxos de Erro

```
FLUXO DE ERRO: [Nome — ex: "API de crédito indisponível"]
GATILHO: [Condição técnica ou de validação]
OCORRE EM: [Passo N do happy path]

PASSO N (erro) →
  O usuário vê: [Mensagem de erro — não deixar genérico]
  Pode fazer: [Retry / Sair / Alternativa]
  → SE retry bem-sucedido: retorna ao PASSO N do happy path
  → SE retry falha: [próximo tratamento]
```

---

## Fluxos com Múltiplos Atores

Comum em produtos B2B da Loft — um ator inicia, outro aprova, sistema notifica.

```
FLUXO: [Nome]
ATORES:
  - Corretor: inicia a proposta
  - Gestor: aprova ou reprova
  - Sistema: notifica e processa

PASSO 1 [CORRETOR]: [O que o corretor faz]
  → Notifica o sistema

PASSO 2 [SISTEMA]: [O que acontece automaticamente]
  → Notifica o gestor

PASSO 3 [GESTOR]: [O que o gestor faz]
  → SE aprovado: PASSO 4A
  → SE reprovado: PASSO 4B

PASSO 4A [SISTEMA]: [Processamento pós-aprovação]
  → Notifica o corretor

SAÍDA: [Estado final para cada ator]
```

---

## Princípios de Estruturação

- **Um passo = uma decisão ou ação significativa** — não granularize cada clique
- **Nomeie pelo que o usuário faz**, não pelo que o sistema mostra — "Gestor aprova fiança", não "Tela de aprovação"
- **Documente o gatilho de cada transição** — "clica em X" ou "sistema retorna Y"
- **Navegação de volta é um fluxo alternativo** — documente o que acontece com dados parciais
- **Não assuma estados** — se o passo 3 depende do resultado do passo 1, documente explicitamente

---

## Níveis de Detalhe

| Momento | Nível | O que incluir |
|---------|-------|---------------|
| Alinhamento inicial | Alto nível | Happy path apenas, passos principais |
| Alinhamento com time | Médio | Happy path + alternativas principais + atores |
| Spec para dev | Detalhado | Todos os fluxos + estados + gatilhos + dados |

Mova para o próximo nível quando o time fizer perguntas que o nível atual não responde.

---

## Convenção de Nomenclatura

`[Ator] + [Verbo] + [Objeto]` — do ponto de vista de quem executa

| ✅ | ❌ |
|----|-----|
| "Gestor analisa proposta de fiança" | "Fluxo de aprovação" |
| "Corretor cadastra imóvel" | "Tela de cadastro" |
| "Inquilino assina contrato" | "Processo de assinatura" |
| "Sistema processa garantia" | "Backend de garantia" |
