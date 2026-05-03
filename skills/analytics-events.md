---
name: analytics-events
description: >
  Framework para modelar eventos de analytics a partir de jornadas de
  design. Define taxonomia, nomenclatura, propriedades e priorização
  de eventos para Amplitude, Mixpanel e similares.
---

# Skill: Event Modeling

## Propósito

Eventos de analytics são a memória do produto. Modelar eventos bem desde o design garante que o time vai conseguir responder perguntas de negócio relevantes após o lançamento.

## Taxonomia de Eventos

Use `[substantivo]_[verbo]` em snake_case:

| Tipo | Padrão | Exemplos |
|------|--------|----------|
| Visualização de tela | `screen_viewed` | `checkout_screen_viewed` |
| Clique em elemento | `[elemento]_clicked` | `cta_button_clicked` |
| Submit de formulário | `[formulário]_submitted` | `payment_form_submitted` |
| Conclusão de etapa | `[etapa]_completed` | `onboarding_step_completed` |
| Abandono | `[fluxo]_abandoned` | `checkout_abandoned` |
| Erro exibido | `[contexto]_error_shown` | `payment_error_shown` |

## Convenções

- Use inglês para nomes de eventos
- Use snake_case (nunca camelCase ou kebab-case)
- Seja específico: `add_to_cart_button_clicked` > `button_clicked`

## Propriedades de Eventos

```
EVENTO: checkout_step_completed
PROPRIEDADES:
  step_name: string — nome do passo ("payment", "review")
  step_number: integer — posição na sequência
  time_spent_seconds: integer — tempo desde abertura
  has_coupon_applied: boolean
  cart_value: float
```

## Regras para Propriedades

- **Não envie PII diretamente** — Nunca nome, e-mail, CPF como propriedade
- **Use IDs, não labels** — `product_id: "prod_123"` não `product_name: "Tênis"`
- **Valores booleanos para flags** — `has_photo: true` não `photo: "yes"`
- **Enum para categorias** — Defina os valores aceitos

## Funil de Conversão

```
FUNIL: [Nome do objetivo]

1. [evento_entrada] — usuário iniciou o fluxo
2. [evento_progresso] — primeiro checkpoint relevante
3. [evento_conversão] — conclusão do objetivo
```

## Priorizando Eventos

| Prioridade | Critério | Ação |
|------------|----------|------|
| **P0 — Crítico** | Mede o objetivo principal do negócio | Implementar obrigatoriamente |
| **P1 — Importante** | Identifica pontos de abandono | Implementar no lançamento |
| **P2 — Útil** | Enriquece análise | Implementar se houver capacidade |
| **P3 — Nice-to-have** | Curiosidade analítica | Backlog |
