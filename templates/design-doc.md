---
version: "1.0"
agent: project-framing
status: "[Rascunho | Em revisão | Aprovado | Em execução | Arquivado]"
---

# Design Doc — [Nome do Projeto ou Feature]

**Dono:** [Designer responsável]
**Squad:** [Nome do squad]
**Stakeholder principal:** [Nome + área]
**Última atualização:** [DD/MM/AAAA]
**Documentos relacionados:** [Links — Figma, tickets, SDD, PRD existente]

---

## TL;DR

> [A PREENCHER — 3 a 5 frases que qualquer pessoa do time entenderia em 30 segundos]
>
> 💡 Pense nisto como um mini press release: qual é o problema, quem sente, o que estamos fazendo e como vamos saber que funcionou. Escreva para alguém que não está no contexto do squad.
>
> Exemplo: "Gestores de imobiliárias pequenas perdem até 40 minutos por análise de fiança por precisar alternar entre sistemas. Estamos redesenhando o fluxo de análise do Loft/Fiança para consolidar as etapas em uma única tela. O sucesso será medido pela redução do tempo médio de análise de 40 para 15 minutos nos primeiros 30 dias após o lançamento."

---

## Cronograma

> Preencha conforme o projeto avança. Não precisa ter datas no início — comece com fases e vá refinando.
> Use este cronograma para comunicar o que você precisa garantir antes de construir. Ele é sua ferramenta para argumentar por mais tempo quando necessário.
>
> 💡 Se você tem uma data de entrega, informe ao agente e ele faz a engenharia reversa sugerindo uma distribuição realista das fases.

| Fase | O que acontece | Responsável | Prazo estimado | Status |
|------|----------------|-------------|----------------|--------|
| Alinhamento inicial | Compartilhar este design doc com stakeholders e coletar feedback | Designer + PM | [A DEFINIR] | ⬜ Pendente |
| Discovery de usuário | Entrevistas ou validação qualitativa do problema | Designer | [A DEFINIR] | ⬜ Pendente |
| Discovery de engenharia | Confirmar viabilidade técnica das principais decisões antes de desenhar | Eng + Designer | [A DEFINIR] | ⬜ Pendente |
| Exploração de design | Wireframes, jornada mapeada no journey-builder | Designer | [A DEFINIR] | ⬜ Pendente |
| Teste de usabilidade | Validar fluxo com usuários reais antes de polir | Designer | [A DEFINIR] | ⬜ Pendente |
| Design critique | Revisão heurística com pares | Designer + pares | [A DEFINIR] | ⬜ Pendente |
| Handoff para dev | Spec completa, tracking spec aprovada | Designer + Eng | [A DEFINIR] | ⬜ Pendente |
| Lançamento | Ship + ativação de tracking | Eng + PM | [A DEFINIR] | ⬜ Pendente |
| Revisão pós-lançamento | Checar métricas de sucesso contra as metas definidas | PM + Designer | [A DEFINIR] | ⬜ Pendente |

> Fases opcionais dependendo do projeto: `Benchmark competitivo` · `Pesquisa quantitativa` · `Teste A/B` · `Rollout gradual`

---

## 1. Contexto

### Problema

> [A PREENCHER]
>
> 💡 Descreva a dor real — evite começar pela solução. Use dados ou evidências quando possível.
>
> Perguntas para guiar:
> - O que está acontecendo hoje que não deveria?
> - Quem sente essa dor? Com que frequência?
> - Como sabemos que esse é o problema certo? Existe evidência (dado, pesquisa, reclamação recorrente)?

### Por que agora

> [A PREENCHER]
>
> 💡 O que mudou ou o que está em jogo que torna isso urgente ou oportuno?
>
> Perguntas para guiar:
> - Existe uma data, evento ou dependência que força a decisão?
> - O que acontece se não fizermos isso agora?
> - Existe uma janela de mercado ou oportunidade que fecha?

### O que foi pedido vs. o problema real

| O que foi pedido | O problema que interpretamos |
|------------------|------------------------------|
| [Literal: o que o stakeholder disse] | [Sua leitura: qual problema de fundo isso endereça] |

> 💡 Stakeholders frequentemente pedem uma solução específica quando o problema real é outro. Esta tabela força a separação.

---

## 2. Objetivo e Sucesso

### O que queremos alcançar

> [A PREENCHER]
>
> 💡 Escreva em termos de impacto no usuário ou no negócio — não em termos de entregáveis.
>
> ❌ "Redesenhar a tela de análise de fiança"
> ✅ "Reduzir o tempo médio de análise de fiança de 40 para 15 minutos"

### Métricas de sucesso

> [A PREENCHER]
>
> 💡 Defina pelo menos uma métrica primária (o que muda se funcionou) e uma guardrail (o que não pode piorar). Sem métricas, não há como saber se o projeto foi bem-sucedido.
>
> Perguntas para guiar:
> - Como saberemos que deu certo em 30 dias? Em 90 dias?
> - O que seria um resultado ruim mas aceitável?
> - O que seria inaceitável — e que nos faria reverter?
> - Existe uma métrica que já acompanhamos que este projeto deve mover?

| Tipo | Métrica | Baseline atual | Meta | Prazo para medir |
|------|---------|----------------|------|-----------------|
| Primária | [ex: tempo médio de análise] | [valor atual] | [valor alvo] | [30/60/90 dias] |
| Guardrail | [ex: NPS do fluxo] | [valor atual] | Não piorar | Contínuo |
| Secundária | [ex: taxa de abandono do fluxo] | [valor atual] | [valor alvo] | [prazo] |

### Fora do escopo (explícito)

> [A PREENCHER]
>
> 💡 Liste o que explicitamente NÃO entra nesta entrega. Isso previne escopo crescente e alinha expectativas antes de começar.

- [Item fora do escopo — motivo]
- [Item fora do escopo — motivo]

---

## 3. Usuários e Cenário

### Personas impactadas

> [A PREENCHER — referencie `context/local/personas.md` se existir no seu squad]
>
> 💡 Quem usa isso diretamente? Quem é afetado indiretamente? Há conflito de necessidades entre personas?

| Persona | Papel no fluxo | Como é afetada | Prioridade |
|---------|----------------|----------------|-----------|
| [Nome] | Usuário primário | [O que muda para ela] | Alta |
| [Nome] | Usuário secundário | [O que muda para ela] | Média |

### Como fazem hoje (sem a solução)

> [A PREENCHER]
>
> 💡 Descreva o workaround atual. Isso ancora o valor da solução e impede que subestimemos o impacto real.
>
> Perguntas para guiar:
> - O que a pessoa faz hoje quando encontra esse problema?
> - Quanto tempo, esforço ou frustração isso custa?
> - Existe algum dado de suporte, NPS, ou pesquisa que ilustra essa dor?

### Cenário de uso principal

> [A PREENCHER]
>
> 💡 Uma história curta: quem é a pessoa, em qual situação, o que ela precisa fazer, o que acontece. Baseie-se em uma persona real do seu squad quando possível.
>
> Exemplo: "Ana, gestora de uma imobiliária com 3 corretores, recebe uma proposta de locação às 18h. Ela precisa analisar a fiança antes de responder ao inquilino, mas o sistema atual exige que ela alterne entre 3 abas diferentes para verificar documentos, histórico e status de análise."

---

## 4. Solução

### Opções consideradas

> [A PREENCHER — modo RFC: exponha as alternativas antes de defender a escolha]
>
> 💡 Liste pelo menos 2 opções reais, incluindo "não fazer nada" ou "solução mínima". Mostrar que você avaliou alternativas aumenta a confiança na decisão final.

**Opção A: [Nome]**
- O que é: [Descrição em 1-2 frases]
- O que resolve: [Benefícios]
- O que não resolve: [Limitações]
- Trade-off principal: [O custo desta escolha]

**Opção B: [Nome]**
- O que é:
- O que resolve:
- O que não resolve:
- Trade-off principal:

**Opção C: Não fazer nada**
- Consequência: [O que acontece se mantivermos o estado atual]

### Decisão recomendada

> [A PREENCHER]
>
> 💡 Qual opção e por quê. Seja direto. Se ainda não decidiu, diga isso explicitamente — uma decisão pendente é melhor do que uma decisão disfarçada de certeza.

### Premissas assumidas

> [A PREENCHER]
>
> 💡 O que precisa ser verdade para esta solução funcionar? Se uma premissa for falsa, o que quebra?

- `[ASSUMIDO:` ...]
- `[ASSUMIDO:` ...]

---

## 5. Riscos e Incertezas

### O que pode dar errado

> [A PREENCHER]
>
> 💡 Pense em riscos de produto (usuário não adota), de UX (fluxo confuso), de negócio (ROI não se concretiza) e de eng (dependência técnica não resolvida).

| Risco | Probabilidade | Impacto | Mitigação proposta |
|-------|--------------|---------|-------------------|
| [Descrição] | Alta / Média / Baixa | Alto / Médio / Baixo | [O que fazer se ocorrer] |

### O que ainda não sabemos

> [A PREENCHER]
>
> 💡 Honestidade intelectual: liste as dúvidas que ainda não foram respondidas e que podem impactar a solução. Isso não é fraqueza — é o que diferencia um design pensado de um design empurrado.
>
> Perguntas para guiar:
> - Existe alguma suposição que ainda não validamos com usuários?
> - Existe alguma dependência técnica que não foi confirmada?
> - Existe algo que se mudar quebra a solução?

---

## 6. Viabilidade e Entrega

### Considerações de engenharia

> [A PREENCHER — idealmente preenchido junto com eng, não sem]
>
> 💡 Não precisa ser técnico. O objetivo é identificar dependências críticas e pontos de risco antes que virem surpresas.
>
> Perguntas para guiar:
> - Existe alguma API ou sistema que precisa ser criado ou modificado?
> - Existe alguma dependência de outro squad ou time?
> - Alguma parte desta solução tem risco de prazo ou complexidade inesperada?

### Estratégia de rollout

> [A PREENCHER]
>
> 💡 Como isso vai ao ar? Feature flag para rollout gradual? Apenas para um segmento de imobiliárias primeiro? Existe critério para expandir ou reverter?

### Validação pós-lançamento

> [A PREENCHER]
>
> 💡 O que você vai checar nos primeiros dias e semanas? Quando o time se reúne para analisar os dados?

| Marco | O que checar | Quando |
|-------|-------------|--------|
| 7 dias | [Indicadores iniciais — bugs, erros, reclamações] | [Data] |
| 30 dias | [Métricas primárias contra baseline] | [Data] |
| 90 dias | [Métricas de longo prazo, hipóteses de impacto] | [Data] |

---

## Decisões Registradas

> Use esta seção ao longo do projeto para registrar decisões importantes com contexto suficiente para alguém que entrar no projeto depois entender o raciocínio.

| Data | Decisão | Alternativa descartada | Motivo |
|------|---------|------------------------|--------|
| [DD/MM] | [O que foi decidido] | [O que foi descartado] | [Por quê esta e não aquela] |
