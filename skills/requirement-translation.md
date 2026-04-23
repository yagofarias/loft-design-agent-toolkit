---
name: requirement-translation
description: >
  Framework para traduzir requisitos técnicos e de negócio em
  requisitos de design acionáveis. Converte PRDs, tickets e briefings
  em entradas estruturadas para o processo de design.
---

# Skill: Requirement Translation

## Propósito

Requisitos chegam em formatos diferentes: PRDs formais, conversas no Slack, tickets de Jira. Esta skill ajuda a processar qualquer formato e extrair o que o designer realmente precisa saber.

## Tipos de Requisito e Como Processar

### PRD

Extraia e restructure em:
1. **O que** — O que o produto deve fazer (não como)
2. **Para quem** — Usuário afetado com contexto
3. **Por quê** — Motivação de negócio e do usuário
4. **Critérios de aceite** — Como saberemos que está pronto
5. **Fora do escopo** — O que explicitamente não está incluído

### Ticket de Engenharia

- Ignore detalhes de implementação (APIs, schemas, algoritmos)
- Extraia o comportamento esperado do ponto de vista do usuário
- Identifique constraints que impactam o design

### Brief Informal

```
Do brief informal, extraia:
- O que foi pedido: [literal]
- O que parece ser o objetivo real: [interpretação]
- O que está ambíguo: [lista]
- O que precisa ser confirmado antes de começar: [lista]
```

## Sinais de Requisitos Problemáticos

**Requisito prescritivo de solução:**
> "Adicionar um modal com confirmação de dois passos"
Pergunte: *Qual problema esse modal resolve?*

**Requisito sem critério de sucesso:**
> "Melhorar a experiência do usuário no checkout"
Pergunte: *O que define "melhorar"? Como vamos medir?*

**Requisito contraditório:**
> "Simplificar o fluxo E adicionar mais opções"
Aponte: *Esses objetivos estão em tensão. Qual é prioritário?*

## Formato de Requisito de Design

```
REQUISITO DE DESIGN: [Número]
ORIGEM: [De onde veio este requisito]
DESCRIÇÃO: [O que o design precisa garantir]
CRITÉRIO: [Como verificar se foi atendido]
IMPACTO SE IGNORADO: [O que acontece se não for atendido]
PRIORIDADE: [Essencial / Importante / Desejável]
DÚVIDA ABERTA: [O que ainda precisa ser confirmado]
```
