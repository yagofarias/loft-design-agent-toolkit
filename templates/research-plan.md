---
version: "1.0"
agent: research-plan
status: "[Planejamento | Em campo | Análise | Concluído]"
---

# Plano de Pesquisa — [Nome do Estudo]

**Pesquisador(a):** [Nome]  
**Squad:** [Nome do squad]  
**Stakeholder principal:** [Nome + área]  
**Última atualização:** [DD/MM/AAAA]  
**Design Doc relacionado:** [Link — se esta pesquisa deriva de um framing]  
**Confluence:** [URL da página — preenchido após publicar]  
**Dovetail:** [Link para o projeto no Dovetail — preenchido após criar]

---

## Como usar este documento

Este documento pode ser preenchido de duas formas:

**Com o agente** — use `/research-plan`. O agente faz o diagnóstico, consulta o acervo, formula as perguntas de pesquisa e preenche as seções 1–7 automaticamente. A seção de Achados é preenchida após a pesquisa.

**Sozinho** — leia as instruções de cada campo (em itálico), preencha e delete as instruções quando não precisar mais.

| Seção | Quando preencher | Quem | Obrigatório? |
|-------|-----------------|------|-------------|
| TL;DR | Após preencher seções 1–3 | Pesquisador | ✅ Sim |
| 1. Contexto | Antes de qualquer coisa | Pesquisador + PM | ✅ Sim |
| 2. Objetivos e Hipóteses | Logo após o contexto | Pesquisador | ✅ Sim |
| 3. Perguntas de Pesquisa | Durante o planejamento | Pesquisador | ✅ Sim |
| 4. Design do Estudo | Durante o planejamento | Pesquisador | ✅ Sim |
| 5. Participantes | Antes do recrutamento | Pesquisador + Ops | ✅ Sim |
| 6. Artefatos | Antes do campo | Pesquisador | ✅ Sim |
| 7. Plano de Análise | Antes do campo | Pesquisador | ✅ Sim |
| Cronograma | Logo após definir o método | Pesquisador + PM | Recomendado |
| Achados | Após a pesquisa | Pesquisador | ✅ Sim |

---

## TL;DR

*2–3 frases que qualquer pessoa do time entende em 30 segundos. Escreva por último. Pense: o que queremos descobrir, por que agora, e como vamos descobrir.*

*Exemplo: "Gestores de imobiliária não entendem por que uma análise de fiança foi reprovada. Vamos conduzir 6 entrevistas em profundidade para entender como eles interpretam o resultado e o que precisam saber para orientar o locatário. Os achados vão alimentar a revisão do fluxo de comunicação de resultado do Loft/Fiança."*

[escreva aqui]

---

## 1. Contexto e Background

### 1.1 Situação atual

*O que está acontecendo no produto ou no negócio que motivou esta pesquisa? Seja específico — qual comportamento, dado ou feedback disparou a necessidade de pesquisar?*

[escreva aqui]

### 1.2 O que já sabemos

*Pesquisas anteriores relevantes, dados de analytics, feedbacks recorrentes, insights do Dovetail. Evite repetir pesquisas — ancore o novo estudo nas lacunas do que já existe.*

*Se nada foi encontrado no acervo: registre isso explicitamente — não deixe em branco.*

[escreva aqui]

### 1.3 Por que pesquisar agora

*O que mudou ou o que está em aberto que justifica este estudo neste momento? Conecte com uma decisão de produto que depende desses achados.*

[escreva aqui]

---

## 2. Objetivos

### 2.1 Objetivo geral

*Uma frase: o que queremos ser capazes de afirmar ao final desta pesquisa.*

[escreva aqui]

### 2.2 Objetivos específicos

*Cada objetivo deve ser independente e verificável. Conecte cada um a uma pergunta de pesquisa na Seção 3.*

1. [Conhecimento específico que queremos obter]
2. [Segundo objetivo]
3. [Terceiro objetivo — adicione ou remova conforme necessário]

---

## 3. Perguntas de Pesquisa e Hipóteses

*Perguntas de pesquisa descrevem o que queremos entender — não são perguntas do roteiro de entrevista. Hipóteses são respostas provisórias baseadas no que já sabemos — tornam os estudos mais eficientes ao definir o que confirmar ou refutar.*

*Formato de pergunta: "Queremos entender [comportamento/decisão/percepção] de [perfil] quando [situação]."*
*Formato de hipótese: "Acreditamos que [resposta esperada] porque [evidência ou raciocínio]."*

| # | Pergunta de pesquisa | Hipótese | Prioridade |
|---|---------------------|----------|-----------|
| P1 | Queremos entender... | Acreditamos que... porque... | Alta |
| P2 | | | Média |
| P3 | | | Baixa |

*Prioridade orienta o que investigar primeiro se o campo for mais curto que o planejado.*

---

## 4. Design do Estudo

### 4.1 Tipo de pesquisa

- [ ] **Exploratória** — descobrir o que não sabemos (novo domínio, novo público)
- [ ] **Avaliativa** — avaliar o que já existe (usabilidade, clareza, eficácia)
- [ ] **Generativa** — identificar oportunidades e direções novas

### 4.2 Métodos

*Para cada método: qual pergunta ele responde, por que este método é o mais adequado, e qual a limitação.*

| Método | Responde às perguntas | Por que este método | Limitações |
|--------|-----------------------|---------------------|-----------|
| [Entrevista em profundidade] | [P1, P2] | [Permite explorar motivações e contexto não-observável] | [Não indica prevalência] |
| [Teste de usabilidade] | [P3] | [Revela problemas de interação em contexto controlado] | [Comportamento pode ser artificial] |

**Guia de seleção de método:**

| Tipo de pergunta | Método indicado |
|-----------------|----------------|
| Comportamento atual e workarounds | Entrevista contextual / shadowing |
| Motivação, decisão, JTBD | Entrevista em profundidade semi-estruturada |
| Usabilidade de fluxo ou interface | Teste de usabilidade (moderado ou não-moderado) |
| Frequência, prevalência, quantificação | Survey quantitativo |
| Comparação entre alternativas | Teste A/B / card sorting / tree test |

### 4.3 Moderação

- [ ] Moderado (pesquisador presente na sessão)
- [ ] Não-moderado (participante faz sozinho com instruções gravadas)
- [ ] Misto

---

## 5. Participantes

### 5.1 Perfil

*Quem precisa participar e por quê. Conecte com as personas do squad em `context/local/personas.md`.*

**Persona principal:** [nome da persona]

**Critérios de inclusão:**
- [Característica obrigatória — ex: usa o produto há mais de 3 meses]
- [Segunda característica]

**Critérios de exclusão:**
- [Quem não deve participar — ex: funcionários da Loft, pessoas que participaram de pesquisa nos últimos 3 meses]

### 5.2 Tamanho da amostra

| Método | Quantidade | Referência |
|--------|-----------|-----------|
| Entrevistas qualitativas | 5–8 | Saturação temática em pesquisa qualitativa |
| Teste de usabilidade (por perfil) | 5 | Identifica ~85% dos problemas de usabilidade |
| Survey quantitativo | 385+ | Margem ±5%, intervalo de confiança 95% |

*Justifique desvios do padrão acima.*

### 5.3 Recrutamento

**Canal:** [plataforma de recrutamento, base de clientes, painel interno]  
**Incentivo:** [voucher, crédito, agradecimento — verifique política interna]  
**Prazo para recrutar:** [DD/MM]  
**Responsável pelo recrutamento:** [nome]

---

## 6. Artefatos do Estudo

*Links para os materiais que guiam a execução. Gere cada um com as skills correspondentes antes de ir a campo.*

| Artefato | Status | Link |
|----------|--------|------|
| Roteiro de entrevista | `[A GERAR]` / `[Pronto]` | |
| Plano de teste de usabilidade | `[A GERAR]` / `[Pronto]` / `[N/A]` | |
| Questionário / survey | `[A GERAR]` / `[Pronto]` / `[N/A]` | |
| Termo de consentimento | `[Usar template padrão]` | |
| Protótipo para teste | `[Link Figma]` / `[N/A]` | |

---

## 7. Plano de Análise

### 7.1 Abordagem analítica

*Como os dados serão analisados. Escolha o mais adequado ao método.*

- [ ] **Análise temática** — identificar padrões e temas recorrentes em dados qualitativos
- [ ] **Affinity mapping** — organizar observações em clusters por similaridade
- [ ] **Análise de tarefas** — medir conclusão, tempo e erros em testes de usabilidade
- [ ] **Análise estatística descritiva** — frequências, médias, correlações em dados de survey

### 7.2 Critérios de sucesso da pesquisa

*O que torna esta pesquisa bem-sucedida — independentemente do resultado. Defina antes de ir a campo para evitar viés de confirmação.*

| Pergunta | O que confirma a hipótese | O que invalida |
|---------|--------------------------|----------------|
| P1 | [Padrão ou evidência esperada] | [Evidência contrária] |
| P2 | | |

### 7.3 Destino dos achados

*Onde os resultados vão ser documentados e como alimentam decisões.*

- [ ] Atualizar Design Doc: substituir `[A VALIDAR:]` por `[VALIDADO:]` ou `[INVALIDADO:]`
- [ ] Publicar no Dovetail com tags de persona e tema
- [ ] Atualizar `context/local/research-archive.md` com resumo dos principais achados
- [ ] Atualizar `context/local/personas.md` se novos padrões de comportamento forem identificados
- [ ] Readout com time: [formato — apresentação, leitura assíncrona, workshop]

---

## Cronograma

| Fase | Atividade | Responsável | Prazo |
|------|-----------|-------------|-------|
| **Preparação** | Recrutamento de participantes | | |
| | Finalizar artefatos (roteiro, protótipo) | | |
| | Piloto (1 sessão de teste do roteiro) | | |
| **Campo** | Sessões de pesquisa | | |
| **Análise** | Transcrição e síntese | | |
| | Affinity mapping / análise | | |
| **Compartilhamento** | Readout com o time | | |
| | Atualização do Design Doc | | |
| | Publicação no Dovetail | | |

---

## Achados

*Preenchido após a pesquisa. Esta seção alimenta o Design Doc e o acervo do squad.*

### Resumo executivo

*3–5 bullets com os achados principais. Escreva para quem não vai ler o resto.*

- [Achado principal]
- [Segundo achado]

### Por pergunta de pesquisa

| # | Pergunta | Status | Achado principal | Evidência |
|---|---------|--------|-----------------|-----------|
| P1 | | `VALIDADO` / `INVALIDADO` / `INCONCLUSIVO` | | [quote ou dado] |
| P2 | | | | |

### Implicações para o design

*O que muda nas decisões de produto a partir desta pesquisa.*

[escreva aqui]

### Surpresas

*O que não esperávamos encontrar.*

[escreva aqui]

### O que ainda está em aberto

*Perguntas que surgiram e não foram respondidas — candidatas à próxima rodada de pesquisa.*

[escreva aqui]

---

## Decisões e Mudanças de Plano

*Registro de ajustes feitos durante a execução — método alterado, perfil revisado, perguntas adicionadas.*

| Data | Decisão | Motivo |
|------|---------|--------|
| [DD/MM] | [O que mudou] | [Por quê] |
