---
name: problem-scoping
description: >
  Framework completo para definir problemas de design: transforma pedidos,
  briefs e PRDs em problem statements estruturados, gera hipóteses verificáveis
  e traduz requisitos de negócio em requisitos de design acionáveis.
---

# Skill: Problem Definition

## Propósito

Esta skill cobre três capacidades que sempre andam juntas na fase de definição: estruturar o problema certo, tornar suposições explícitas como hipóteses verificáveis, e traduzir o que foi pedido no que o design realmente precisa entregar.

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

❌ Fraco: "Como podemos melhorar o checkout?"
✅ Forte: "Como podemos reduzir o abandono na etapa de pagamento para usuários mobile que chegam via campanha de e-mail, sem aumentar o número de campos obrigatórios?"

### Separando Pedido de Problema

Quando receber um pedido, sempre pergunte:

1. **Por que isso foi pedido?** — Qual dor ou oportunidade motivou?
2. **Para quem?** — Quem realmente é afetado?
3. **Como sabemos que é um problema?** — Existe dado, reclamação, ou hipótese?
4. **O que define sucesso?** — Se isso for resolvido, o que muda?

### Critérios de Sucesso

| ❌ Ruim | ✅ Bom |
|---------|--------|
| "Melhorar a experiência" | "Reduzir chamadas ao suporte sobre este fluxo em 30%" |
| "Deixar mais simples" | "Usuários completam o fluxo sem ajuda em menos de 2 minutos" |
| "Implementar o redesign" | "Taxa de conclusão do checkout mobile aumenta de 54% para 65%" |

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
> "Acreditamos que usuários novos abandonam o onboarding na etapa de configuração de perfil porque não entendem por que o produto precisa dessas informações."

**Hipótese de solução** — sobre a eficácia de uma abordagem:
> "Se explicarmos o benefício de cada campo ao lado do campo, usuários completarão o onboarding com mais frequência."

**Hipótese de usuário** — sobre comportamento ou necessidade:
> "Acreditamos que usuários recorrentes preferem acessar ações frequentes sem passar pelo menu principal."

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

**Prescritivo de solução:** "Adicionar um modal com confirmação de dois passos"
→ Pergunte: *Qual problema esse modal resolve?*

**Sem critério de sucesso:** "Melhorar a experiência no checkout"
→ Pergunte: *O que define "melhorar"?*

**Contraditório:** "Simplificar o fluxo E adicionar mais opções"
→ Aponte: *Esses objetivos estão em tensão. Qual é prioritário?*

**Baseado em suposição não validada:** "Os usuários querem exportar para PDF"
→ Pergunte: *Como sabemos? É dado ou hipótese?*

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
