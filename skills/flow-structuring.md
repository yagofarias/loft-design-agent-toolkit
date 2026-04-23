---
name: flow-structuring
description: >
  Framework para estruturar e documentar fluxos de design em texto,
  identificando passos, decisões, gatilhos e pontos de saída de forma
  que sirvam como base para especificação e handoff.
---

# Skill: Flow Structuring

## Propósito

Um fluxo bem estruturado em texto é mais útil do que um fluxo visual sem documentação. Esta skill define como mapear e documentar jornadas de forma clara, completa e referenciável.

## Anatomia de um Fluxo

- **Ponto de entrada** — De onde o usuário chega (notificação, menu, link externo)
- **Pré-condição** — O que precisa ser verdade para o usuário chegar aqui
- **Passos** — Sequência de telas, ações e estados
- **Decisões** — Pontos onde o fluxo se bifurca com base em input ou estado
- **Ponto de saída** — Onde o fluxo termina (sucesso, abandono, redirecionamento)

## Formato de Documentação

```
FLUXO: [Nome do fluxo]
ENTRADA: [De onde o usuário chega]
PRÉ-CONDIÇÃO: [O que precisa ser verdade]

PASSO 1: [Nome da tela ou momento]
  - O usuário vê: [Conteúdo principal]
  - Ação disponível: [O que pode fazer]
  - Gatilho de avanço: [O que faz avançar]

  → SE [condição A]: vai para PASSO 2A
  → SE [condição B]: vai para PASSO 2B

SAÍDA SUCESSO: [Estado final]
SAÍDA ALTERNATIVA: [Outros estados finais possíveis]
```

## Princípios de Estruturação

- Um passo = uma decisão ou ação significativa
- Nomeie passos pelo que o usuário faz, não pelo que o sistema mostra
- Documente o gatilho de cada transição explicitamente

## Níveis de Detalhe

| Momento | Nível | Inclui |
|---------|-------|--------|
| Exploração inicial | Alto nível | Passos principais, sem variantes |
| Alinhamento com time | Médio | Passos + decisões principais |
| Spec para dev | Detalhado | Passos + decisões + estados + edge cases |
