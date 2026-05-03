---
version: "2.0"
agent: project-framing
status: "[Rascunho | Em revisão | Aprovado | Em execução | Arquivado]"
---

# Design Doc — [Nome do Projeto ou Feature]

**Dono:** [Designer responsável]  
**Squad:** [Nome do squad]  
**Stakeholder principal:** [Nome + área]  
**Última atualização:** [DD/MM/AAAA]  
**Documentos relacionados:** [Links — Figma, ticket, SDD, PRD existente]

---

## Como usar este documento

Este documento pode ser preenchido de duas formas:

**Com o agente** — use `agents/project-framing.md`. O agente faz as perguntas e preenche as seções 1-3 automaticamente. As seções 4-6 ficam com marcações para você completar depois.

**Sozinho** — leia as instruções de cada campo (em itálico abaixo de cada título), preencha o conteúdo no espaço indicado e delete as instruções quando não precisar mais delas.

### Ordem sugerida de preenchimento

| Seção | Quando preencher | Quem | Obrigatório? |
|-------|-----------------|------|-------------|
| TL;DR | Ao final do framing — escreva depois de preencher as seções 1-3 | Designer | ✅ Sim |
| Cronograma | Opcional no início, essencial antes do handoff | Designer + PM | Progressivo |
| 1. Contexto | Primeira coisa a preencher | Designer + PM | ✅ Sim |
| 2. Objetivo e Sucesso | Logo após o contexto | Designer + PM | ✅ Sim |
| 3. Usuários e Cenário | Durante o framing | Designer | ✅ Sim |
| 4. Solução | Durante a exploração de design | Designer | ✅ Sim |
| 5. Riscos e Incertezas | Durante a exploração — antes de finalizar | Designer + Eng | ✅ Sim |
| 6. Viabilidade e Entrega | Antes do handoff | Designer + Eng + PM | ✅ Sim |
| Decisões Registradas | Ao longo de todo o projeto | Todos | Recomendado |

> **Dica para começar:** preencha apenas a Seção 1 (Contexto) e o TL;DR. Com isso já dá para alinhar com o time e continuar o resto de forma iterativa.

---

## TL;DR

*3 a 5 frases que qualquer pessoa do time entenderia em 30 segundos. Escreva por último, depois de preencher as seções 1-3. Pense: qual é o problema, quem sente, o que estamos fazendo, como saberemos que deu certo.*

*Exemplo: "Gestores de imobiliárias pequenas perdem até 40 minutos por análise de fiança por precisar alternar entre sistemas. Estamos redesenhando o fluxo de análise do Loft/Fiança para consolidar as etapas em uma única tela. O sucesso será medido pela redução do tempo médio de análise de 40 para 15 minutos nos primeiros 30 dias após o lançamento."*

[escreva aqui]

---

## Cronograma

*Preencha conforme o projeto avança. Não precisa ter datas no início — comece pelas fases que sabe que existem e vá refinando. Use este cronograma para argumentar por tempo adequado para cada etapa.*

*Fases opcionais (adicione se fizer sentido para o projeto): `Benchmark competitivo` · `Pesquisa quantitativa` · `Teste A/B` · `Rollout gradual por segmento`*

| Fase | O que acontece | Responsável | Prazo estimado | Status |
|------|----------------|-------------|----------------|--------|
| Alinhamento inicial | Compartilhar este design doc com stakeholders e coletar feedback | Designer + PM | [A DEFINIR] | ⬜ Pendente |
| Discovery de usuário | Entrevistas ou validação qualitativa do problema | Designer | [A DEFINIR] | ⬜ Pendente |
| Discovery de engenharia | Confirmar viabilidade técnica das principais decisões antes de desenhar | Eng + Designer | [A DEFINIR] | ⬜ Pendente |
| Exploração de design | Wireframes e jornada mapeada | Designer | [A DEFINIR] | ⬜ Pendente |
| Teste de usabilidade | Validar fluxo com usuários reais antes de polir | Designer | [A DEFINIR] | ⬜ Pendente |
| Design critique | Revisão heurística com pares | Designer + pares | [A DEFINIR] | ⬜ Pendente |
| Handoff para dev | Spec completa, tracking spec aprovada | Designer + Eng | [A DEFINIR] | ⬜ Pendente |
| Lançamento | Ship + ativação de tracking | Eng + PM | [A DEFINIR] | ⬜ Pendente |
| Revisão pós-lançamento | Checar métricas de sucesso | PM + Designer | [A DEFINIR] | ⬜ Pendente |

---

## 1. Contexto

### 1.1 Problema ✅ obrigatório

*O que está acontecendo hoje que não deveria? Descreva a dor real — não a solução. Use dados ou evidências sempre que tiver.*

*Perguntas para ajudar:*
*— Quem sente essa dor e com que frequência?*
*— Como sabemos que esse é o problema certo? Existe evidência (dado, pesquisa, reclamação recorrente)?*
*— O que essa dor custa (tempo, dinheiro, confiança)?*

*Exemplo ruim: "A tela de análise de fiança precisa ser redesenhada."*
*Exemplo bom: "Gestores de imobiliárias levam em média 40 minutos para analisar uma proposta de fiança porque precisam alternar entre 3 sistemas diferentes. Isso causa atrasos de até 2 dias na resposta ao inquilino e leva à perda de 15% das propostas para concorrentes mais ágeis (dado interno, Q1/2026)."*

[descreva o problema aqui]

---

### 1.2 Por que agora ✅ obrigatório

*O que mudou ou o que está em jogo que torna isso urgente ou oportuno? O que acontece se não fizermos isso agora?*

*Perguntas para ajudar:*
*— Existe uma data, evento ou dependência que força a decisão?*
*— Existe uma janela de oportunidade que fecha?*
*— O que perdemos se deixarmos para o próximo trimestre?*

*Exemplo: "A Loft está lançando o Qualifica Leads em agosto. Se o fluxo de análise não for redesenhado antes, o tempo ganho na qualificação será perdido na análise — e o benefício do novo produto será invisível para a imobiliária."*

[descreva por que agora]

---

### 1.3 O que foi pedido vs. o problema real ✅ obrigatório

*Stakeholders frequentemente pedem uma solução específica quando o problema real é outro. Separar os dois evita entregar a coisa errada perfeitamente feita.*

| O que foi pedido | O problema que interpretamos |
|------------------|------------------------------|
| [O que o stakeholder pediu, literalmente] | [Sua leitura: qual problema de fundo isso endereça] |

*Exemplo:*

| O que foi pedido | O problema que interpretamos |
|------------------|------------------------------|
| "Adiciona um botão de aprovar na tela de análise" | Gestores não conseguem agir rápido porque as informações necessárias estão em telas diferentes |

---

## 2. Objetivo e Sucesso

### 2.1 O que queremos alcançar ✅ obrigatório

*Escreva em termos de impacto no usuário ou no negócio — não em termos de entregáveis ou funcionalidades.*

*❌ Não: "Redesenhar a tela de análise de fiança"*
*✅ Sim: "Reduzir o tempo médio de análise de fiança de 40 para 15 minutos"*

*❌ Não: "Implementar notificações em tempo real"*
*✅ Sim: "Garantir que nenhuma proposta fique sem resposta por mais de 4 horas durante horário comercial"*

[descreva o objetivo aqui]

---

### 2.2 Métricas de sucesso ✅ obrigatório

*Defina pelo menos uma métrica primária e uma guardrail. A primária mede o que mudou se deu certo. A guardrail é o que não pode piorar com a mudança.*

*Se não souber os valores de baseline, escreva "a levantar" — mas defina qual métrica você quer acompanhar.*

*Perguntas para ajudar:*
*— Como saberemos que deu certo em 30 dias? Em 90 dias?*
*— O que seria um resultado ruim mas aceitável?*
*— O que seria inaceitável — e que nos faria reverter a mudança?*

| Tipo | Métrica | Baseline atual | Meta | Prazo para medir |
|------|---------|----------------|------|-----------------|
| Primária | [ex: tempo médio de análise de fiança] | [ex: 40 min] | [ex: 15 min] | [ex: 30 dias] |
| Guardrail | [ex: NPS do fluxo de locação] | [ex: 42] | Não piorar | Contínuo |
| Secundária | [ex: taxa de conclusão da análise no mesmo dia] | [ex: 60%] | [ex: 85%] | [ex: 60 dias] |

---

### 2.3 Fora do escopo (explícito) ✅ obrigatório

*Liste o que explicitamente NÃO entra nesta entrega. Isso previne que o escopo cresça no meio do projeto e alinha expectativas com stakeholders e engenharia antes de começar.*

*Exemplo:*
*— Não inclui o redesign do fluxo de renovação de contrato (próximo trimestre)*
*— Não inclui integração com cartório digital (dependência de contrato com fornecedor)*

- [item fora do escopo — motivo ou contexto]
- [item fora do escopo — motivo ou contexto]

---

## 3. Usuários e Cenário

### 3.1 Personas impactadas ✅ obrigatório

*Quem usa isso diretamente? Quem é afetado indiretamente? Se o seu squad tiver personas definidas em `context/local/personas.md`, referencie-as aqui pelo nome.*

*Há conflito de necessidades entre personas? Se sim, qual persona tem prioridade?*

| Persona | Papel no fluxo | O que muda para ela com esta entrega | Prioridade |
|---------|----------------|--------------------------------------|-----------|
| [Nome ou descrição] | Usuário primário — quem executa o fluxo | [O que muda ou melhora] | Alta |
| [Nome ou descrição] | Usuário secundário — quem é afetado pelo resultado | [O que muda ou melhora] | Média |

---

### 3.2 Como fazem hoje (sem a solução) ✅ obrigatório

*Descreva o workaround atual. Isso ancora o valor real da solução — sem isso, fica difícil justificar por que vale a pena construir.*

*Perguntas para ajudar:*
*— O que a pessoa faz hoje quando encontra esse problema?*
*— Quantas etapas, sistemas ou pessoas estão envolvidos no workaround atual?*
*— Qual é o custo em tempo, esforço ou frustração?*

*Exemplo: "A gestora abre o email com a proposta, copia o CPF do inquilino, acessa o portal de análise de crédito, cola o CPF, aguarda o resultado, volta ao email para comparar com os documentos anexados, e então acessa o sistema de contratos para registrar a decisão. Em média 40 minutos por proposta, com risco de erro a cada troca de sistema."*

[descreva o processo atual aqui]

---

### 3.3 Cenário de uso principal ✅ obrigatório

*Uma história curta em linguagem simples: quem é a pessoa, em qual situação real, o que ela precisa fazer e o que acontece. Não precisa ser perfeita — só precisa ser concreta.*

*Escreva para alguém que nunca viu o produto. Se possível, use uma persona real do seu squad.*

*Exemplo: "Ana gere uma imobiliária com 3 corretores. São 18h de uma quinta-feira. Ela recebe uma notificação de nova proposta de locação para um apartamento que está há 45 dias no mercado. O inquilino quer uma resposta ainda hoje. Ana precisa analisar a fiança e dar um parecer, mas já está encerrando o expediente. Com o fluxo atual, ela sabe que vai levar pelo menos meia hora — e provavelmente vai perder a proposta para outra imobiliária que responder mais rápido."*

[escreva o cenário aqui]

---

## 4. Solução

*Esta seção é preenchida durante a exploração de design, em conjunto com o `journey-builder`. No início do projeto, deixe as subseções em aberto — preencha quando tiver alternativas para comparar.*

### 4.1 Opções consideradas ✅ obrigatório quando houver decisão

*Liste pelo menos 2 opções antes de defender a escolha. Inclua sempre a opção de "não fazer nada" — ela ajuda a calibrar o valor do que você está propondo. Mostrar que você avaliou alternativas aumenta a confiança na decisão final.*

**Opção A: [Nome da opção]**
- O que é: [Descrição em 1-2 frases]
- O que resolve: [Benefícios concretos]
- O que não resolve: [Limitações — seja honesto]
- Trade-off principal: [O custo real desta escolha — tempo, complexidade, risco]

**Opção B: [Nome da opção]**
- O que é:
- O que resolve:
- O que não resolve:
- Trade-off principal:

**Opção C: Não fazer nada (sempre inclua)**
- Consequência: [O que acontece se mantivermos o estado atual por mais 3-6 meses]

---

### 4.2 Decisão recomendada ✅ obrigatório quando houver decisão

*Qual opção você recomenda e por quê. Seja direto. Se ainda não decidiu, escreva "Decisão pendente" e liste o que precisa ser resolvido para decidir — isso é mais honesto do que deixar vago.*

[escreva a decisão ou "Decisão pendente — aguardando [X]"]

---

### 4.3 Premissas assumidas ⚠️ importante

*O que precisa ser verdade para esta solução funcionar? Se alguma dessas premissas for falsa, o design pode precisar mudar. Liste explicitamente para que o time possa validá-las.*

*Exemplo:*
*— `[ASSUMIDO:` o backend já expõe os dados de análise em uma única API — validar com eng]*
*— `[ASSUMIDO:` o gestor usa o produto pelo celular na maioria das vezes — validar com analytics]*

- `[ASSUMIDO:` ...]
- `[ASSUMIDO:` ...]

---

## 5. Riscos e Incertezas

*Preencha durante a exploração — antes de finalizar o design. Um risco identificado aqui é um problema evitado depois.*

### 5.1 O que pode dar errado ✅ obrigatório

*Pense em riscos de produto (usuário não adota), de UX (fluxo confuso), de negócio (ROI não acontece) e de engenharia (dependência técnica não resolvida). Liste os mais relevantes — não precisa ser exaustivo.*

| Risco | Probabilidade | Impacto | Mitigação proposta |
|-------|--------------|---------|-------------------|
| [Descreva o risco em uma frase] | Alta / Média / Baixa | Alto / Médio / Baixo | [O que fazer para reduzir ou responder] |
| [ex: Gestores não adotam o novo fluxo por falta de treinamento] | Média | Alto | [Criar onboarding in-product + comunicar lançamento pela imobiliária] |

---

### 5.2 O que ainda não sabemos ✅ obrigatório

*Liste as dúvidas que ainda não foram respondidas e que podem impactar a solução. Isso é honestidade intelectual — não fraqueza. Um `[A VALIDAR]` explícito é melhor do que uma falsa certeza.*

*Perguntas para ajudar:*
*— Existe alguma suposição sobre o usuário que ainda não validamos?*
*— Existe alguma dependência técnica que não foi confirmada?*
*— Existe algo que, se mudar, quebra a solução?*

- `[A VALIDAR:` ...] — como validar: [...]
- `[A VALIDAR:` ...] — como validar: [...]

---

## 6. Viabilidade e Entrega

*Esta seção é preenchida em conjunto com engenharia, antes do handoff. O objetivo não é detalhar a implementação, mas garantir que não haverá surpresas.*

### 6.1 Considerações de engenharia ✅ obrigatório antes do handoff

*Não precisa ser técnico. Identifique as dependências críticas e os pontos de risco para que engenharia possa se planejar.*

*Perguntas para discutir com eng:*
*— Existe alguma API ou sistema que precisa ser criado ou modificado?*
*— Existe alguma dependência de outro squad ou time?*
*— Alguma parte desta solução tem risco de prazo ou complexidade inesperada?*
*— Existe algum risco de regressão em outras partes do produto?*

[preencha após conversa com engenharia]

---

### 6.2 Estratégia de rollout ✅ obrigatório antes do handoff

*Como isso vai ao ar? Qual é o plano se algo der errado?*

*Opções comuns: lançamento para todos ao mesmo tempo · feature flag para rollout gradual · apenas para um segmento de imobiliárias primeiro · experimento A/B*

*Critério de rollback: qual sinal indica que precisamos reverter?*

[descreva a estratégia de rollout e o critério de reversão]

---

### 6.3 Validação pós-lançamento ✅ obrigatório antes do handoff

*O que você vai checar nos primeiros dias e semanas? Quando o time se reúne para analisar os dados? Conecte com as métricas da Seção 2.2.*

| Marco | O que checar | Responsável | Quando |
|-------|-------------|-------------|--------|
| 7 dias | Bugs, erros de fluxo, reclamações críticas | Designer + Eng | [Data] |
| 30 dias | Métricas primárias e guardrail contra baseline | PM + Designer | [Data] |
| 90 dias | Métricas de longo prazo e hipóteses de impacto | PM + Designer | [Data] |

---

## Decisões Registradas

*Use ao longo do projeto para registrar decisões importantes com contexto suficiente para que alguém que entrar depois entenda o raciocínio. Uma linha por decisão relevante — não precisa registrar tudo.*

*Quando registrar: quando o time debateu duas opções e escolheu uma, quando um requisito mudou, quando uma premissa foi validada ou invalidada.*

| Data | Decisão | Alternativa descartada | Por quê esta e não aquela |
|------|---------|------------------------|--------------------------|
| [DD/MM] | [O que foi decidido, em uma frase] | [O que foi descartado] | [O raciocínio — 1-2 frases] |
