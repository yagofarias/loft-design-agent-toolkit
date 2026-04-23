---
name: hypothesis-generation
description: >
  Técnicas para gerar, estruturar e priorizar hipóteses verificáveis
  sobre problemas de design. Transforma suposições implícitas em
  declarações testáveis.
---

# Skill: Hypothesis Generation

## Propósito

Hipóteses tornam suposições explícitas e testáveis. Sem hipóteses, decisões de design são baseadas em opinião. Com hipóteses bem formuladas, cada decisão pode ser validada ou refutada.

## Estrutura de Hipótese

> "Acreditamos que **[usuário]** tem dificuldade com **[situação específica]** porque **[razão hipotética]**. Se **[mudança de design]**, então **[outcome esperado]**, o que verificaremos através de **[método de validação]**."

## Tipos de Hipótese em Design

**Hipótese de problema:**
> "Acreditamos que usuários novos abandonam o onboarding na etapa de configuração de perfil porque não entendem por que o produto precisa dessas informações."

**Hipótese de solução:**
> "Se explicarmos o benefício de cada campo de perfil ao lado do campo, usuários completarão o onboarding com mais frequência."

**Hipótese de usuário:**
> "Acreditamos que usuários recorrentes preferem acessar ações frequentes sem passar pelo menu principal."

## Critérios de uma Boa Hipótese

- [ ] É específica — não pode ser interpretada de formas muito diferentes
- [ ] É refutável — existe uma evidência que provaria que está errada
- [ ] É relevante — se confirmada, influencia uma decisão de design
- [ ] É verificável — existe um método realista para testá-la

## Priorizando Hipóteses

| Critério | Peso |
|----------|------|
| Impacto se confirmada | Alto |
| Risco se ignorada | Alto |
| Facilidade de verificação | Médio |
| Custo de estar errado | Médio |

## Status de Hipóteses

- `[HIPÓTESE]` — Não testada
- `[CONFIRMADA]` — Com evidência
- `[REFUTADA]` — Com evidência
- `[PARCIAL]` — Evidência mista
