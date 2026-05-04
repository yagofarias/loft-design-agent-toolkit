---
name: problem-scoping
description: >
  Framework completo para definir problemas de design: transforma pedidos,
  briefs e PRDs em problem statements estruturados, gera hipóteses verificáveis
  e traduz requisitos de negócio em requisitos de design acionáveis.
---

# Skill: Problem Scoping

## Propósito

Esta skill cobre três capacidades que sempre andam juntas na fase de definição: estruturar o problema certo, tornar suposições explícitas como hipóteses verificáveis, e traduzir o que foi pedido no que o design realmente precisa entregar.

**Output desta skill:** alimenta as seções 1, 2 e 3 do `templates/design-doc.md` — Contexto, Objetivo e Sucesso, e Usuários e Cenário.

---

## Parte 1 — Problem Statement

### Framework

Use a estrutura:

> "Como podemos **[ação específica]** para **[usuário com contexto]** de forma que **[outcome mensurável]**, sem **[restrição importante]**?"

**Bons problem statements:**
- São específicos o suficiente para excluir soluções irrelevantes
- São amplos o suficiente para não prescrever a solução
- Referenciam o usuário, não o negócio
- Incluem o contexto de uso quando relevante

**Exemplos:**

❌ Fraco: "Como podemos melhorar o fluxo de análise de fiança?"
✅ Forte: "Como podemos reduzir o tempo de análise de fiança de 40 para 15 minutos para gestores de imobiliárias pequenas, sem aumentar o risco de aprovação incorreta?"

❌ Fraco: "Como podemos melhorar o onboarding de imobiliárias?"
✅ Forte: "Como podemos ajudar imobiliárias novas a cadastrar seu primeiro imóvel em menos de 10 minutos, sem que precisem de suporte para concluir o processo?"

### Separando Pedido de Problema

Quando receber um pedido, sempre pergunte:

1. **Por que isso foi pedido?** — Qual dor ou oportunidade motivou?
2. **Para quem?** — Quem realmente é afetado?
3. **Como sabemos que é um problema?** — Existe dado, reclamação, ou hipótese?
4. **O que define sucesso?** — Se isso for resolvido, o que muda?

### Critérios de Sucesso

| ❌ Ruim | ✅ Bom |
|---------|--------|
| "Melhorar a experiência de análise" | "Reduzir o tempo médio de análise de fiança de 40 para 15 minutos" |
| "Deixar o cadastro mais simples" | "Imobiliárias novas completam o primeiro cadastro sem contato com suporte" |
| "Implementar o redesign do CRM" | "Taxa de uso do funil de vendas sobe de 30% para 60% entre corretores ativos" |

### Mapeamento de Stakeholders

| Papel | Quem | Interesse principal | Poder de veto |
|-------|------|---------------------|---------------|
| Usuário primário | Quem usa diretamente | | |
| Usuário secundário | Quem é afetado indiretamente | | |
| Stakeholder de negócio | Quem tem interesse no resultado | | Sim/Não |
| Stakeholder técnico | Quem implementa e mantém | | Sim/Não |

Conflitos entre necessidades desses grupos devem ser documentados explicitamente, não ignorados.

---

## Parte 2 — Hipóteses

### Estrutura

> "Acreditamos que **[usuário]** tem dificuldade com **[situação específica]** porque **[razão hipotética]**. Se **[mudança de design]**, então **[outcome esperado]**, o que verificaremos através de **[método de validação]**."

### Tipos

**Hipótese de problema** — sobre a existência e natureza do problema:
> "Acreditamos que gestores de imobiliárias abandonam a análise de fiança no meio do processo porque precisam alternar entre 3 sistemas diferentes para reunir as informações necessárias."

**Hipótese de solução** — sobre a eficácia de uma abordagem:
> "Se consolidarmos os dados de análise em uma única tela, o tempo médio de análise vai cair de 40 para menos de 20 minutos."

**Hipótese de usuário** — sobre comportamento ou necessidade:
> "Acreditamos que corretores preferem visualizar o status das propostas diretamente na listagem de imóveis, sem precisar entrar em cada proposta individualmente."

### Critérios de uma Boa Hipótese

- [ ] É específica — não pode ser interpretada de formas muito diferentes
- [ ] É refutável — existe uma evidência que provaria que está errada
- [ ] É relevante — se confirmada, influencia uma decisão de design
- [ ] É verificável — existe um método realista para testá-la

### Status de Hipóteses

- `[HIPÓTESE]` — Não testada
- `[CONFIRMADA]` — Com evidência
- `[REFUTADA]` — Com evidência
- `[PARCIAL]` — Evidência mista

---

## Parte 3 — Tradução de Requisitos

### Elicitação de Requisitos

Antes de processar qualquer requisito, garanta respostas para:

**Perguntas de negócio:**
1. Qual é o problema que este requisito resolve?
2. Qual é o impacto esperado?
3. Quem aprova?
4. O que define sucesso?

**Perguntas de usuário:**
1. Quem usa isso — qual persona, segmento, tipo de usuário?
2. Com que frequência?
3. Em qual contexto — dispositivo, situação, nível de atenção?
4. O que o usuário está tentando fazer — o job-to-be-done real?

**Perguntas de processo:**
1. Como isso é feito hoje?
2. O que está quebrando no processo atual?
3. O que não pode mudar?

### Tipos de Requisito e Como Processar

**PRD completo:** Extraia o quê, para quem, por quê, critérios de aceite, fora do escopo e dependências.

**Ticket de engenharia:** Ignore implementação. Extraia o comportamento esperado do ponto de vista do usuário e os constraints que impactam design.

**Brief informal:**
```
O que foi pedido: [literal]
O que parece ser o objetivo real: [interpretação]
O que está ambíguo: [lista]
O que precisa ser confirmado: [lista]
```

### Sinais de Requisitos Problemáticos

**Prescritivo de solução:** "Adicionar um botão de aprovação rápida na listagem de propostas"
→ Pergunte: *Qual problema esse botão resolve? O que está lento hoje?*

**Sem critério de sucesso:** "Melhorar a experiência de análise de fiança"
→ Pergunte: *O que define "melhorar"? Tempo? Taxa de conclusão? NPS?*

**Contraditório:** "Simplificar o fluxo de cadastro E coletar mais dados do inquilino"
→ Aponte: *Esses objetivos estão em tensão. Qual é prioritário para este lançamento?*

**Baseado em suposição não validada:** "As imobiliárias querem exportar contratos em PDF"
→ Pergunte: *Como sabemos? É dado de suporte, pesquisa ou hipótese interna?*

### Classificação de Constraints

| Tipo | Descrição |
|------|-----------|
| **Reais** | Limitações não negociáveis — regulatório, técnico bloqueante, prazo fixo |
| **Assumidas** | Parecem existir mas não foram confirmadas — `[ASSUMIDO: ...]` |
| **Preferências** | O que stakeholders gostariam, mas negociável |

### Formato de Requisito de Design

```
REQUISITO: [Número]
ORIGEM: [PRD / ticket / conversa / pesquisa]
DESCRIÇÃO: [O que o design precisa garantir — comportamento, não solução]
CRITÉRIO: [Como verificar se foi atendido]
USUÁRIO AFETADO: [Quem e em qual contexto]
IMPACTO SE IGNORADO: [O que acontece se não for atendido]
PRIORIDADE: [Essencial / Importante / Desejável]
DÚVIDA ABERTA: [O que ainda precisa ser confirmado — com responsável]
```
