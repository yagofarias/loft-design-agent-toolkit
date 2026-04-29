---
name: requirement-translation
description: >
  Framework para traduzir requisitos técnicos, de negócio e de stakeholders
  em requisitos de design acionáveis. Cobre elicitação, análise de processos,
  identificação de lacunas e tradução de linguagem de negócio para linguagem
  de design.
---

# Skill: Requirement Translation

## Propósito

Requisitos chegam em formatos diferentes: PRDs formais, conversas no Slack, tickets de Jira, ou "a gente precisa fazer isso até sexta". Esta skill ajuda a processar qualquer formato, identificar o que está implícito e extrair o que o designer realmente precisa saber.

---

## Elicitação de Requisitos

Antes de processar qualquer requisito, garanta que você tem as respostas para:

### Perguntas de Negócio
1. **Qual é o problema que este requisito resolve?** — Qual dor, risco ou oportunidade está sendo endereçado?
2. **Qual é o impacto esperado?** — O que muda para o negócio se isso for bem executado?
3. **Quem aprova?** — Qual stakeholder tem a palavra final sobre este requisito?
4. **O que define sucesso?** — Existe uma métrica, prazo ou critério de aceite?

### Perguntas de Usuário
1. **Quem usa isso?** — Qual persona, segmento ou tipo de usuário é o beneficiário?
2. **Com que frequência?** — Uso diário, semanal, ocasional, ou momento único?
3. **Em qual contexto?** — Dispositivo, situação, nível de atenção disponível?
4. **O que o usuário está tentando fazer?** — O job-to-be-done real, não a feature pedida?

### Perguntas de Processo
1. **Como isso é feito hoje?** — Qual é o processo atual (mesmo que manual ou workaround)?
2. **O que está quebrando no processo atual?** — Qual é a fricção específica?
3. **O que não pode mudar?** — Quais partes do processo atual devem ser preservadas?

---

## Tipos de Requisito e Como Processar

### PRD Completo
Extraia e restructure em:
1. **O que** — O que o produto deve fazer (comportamento, não implementação)
2. **Para quem** — Usuário afetado com contexto de uso
3. **Por quê** — Motivação de negócio e motivação do usuário
4. **Critérios de aceite** — Como saberemos que está pronto
5. **Fora do escopo** — O que explicitamente não está incluído
6. **Dependências** — O que precisa existir antes

### Ticket de Engenharia
Frequentemente técnico demais. Filtre:
- Ignore detalhes de implementação (APIs, schemas, algoritmos)
- Extraia o comportamento esperado do ponto de vista do usuário
- Identifique constraints que impactam design (limites de caractere, formatos obrigatórios, estados possíveis)
- Questione o que está implícito mas não documentado

### Brief Informal
Valide antes de começar:
```
Do brief informal, extraia:
- O que foi pedido: [literal]
- O que parece ser o objetivo real: [interpretação]
- O que está ambíguo: [lista de dúvidas]
- O que precisa ser confirmado antes de começar: [lista]
```
Nunca assuma que entendeu — confirme antes de executar.

---

## Mapeamento de Processo Atual vs. Desejado

Para requisitos que envolvem mudança de fluxo existente, mapeie:

| Etapa | Como é hoje | Problema atual | Como deveria ser | Impacto da mudança |
|-------|-------------|----------------|------------------|--------------------|
| [Passo 1] | [Descrição] | [Fricção] | [Estado desejado] | [O que muda] |

Isso revela:
- **Gaps reais** — O que está faltando no processo atual
- **Riscos de mudança** — O que pode quebrar se alterado
- **Quick wins** — Melhorias que não exigem redesign completo

---

## Mapeamento de Stakeholders

Para cada projeto, identifique e documente:

| Stakeholder | Papel | Interesse principal | Poder de veto | Nível de engajamento necessário |
|-------------|-------|---------------------|---------------|--------------------------------|
| [Nome/Área] | Solicitante / Aprovador / Usuário / Técnico | [O que mais importa para ele] | Sim/Não | Alto / Médio / Baixo |

**Conflitos entre stakeholders** devem ser documentados explicitamente, não ignorados. Quando há tensão, escale antes de continuar — não resolva por conta própria.

---

## Sinais de Requisitos Problemáticos

Identifique e questione quando encontrar:

**Requisito prescritivo de solução:**
> "Adicionar um modal com confirmação de dois passos"
Pergunte: *Qual problema esse modal resolve? Existe outra forma de resolver?*

**Requisito sem critério de sucesso:**
> "Melhorar a experiência do usuário no checkout"
Pergunte: *O que define "melhorar"? Como vamos medir?*

**Requisito contraditório:**
> "Simplificar o fluxo E adicionar mais opções de configuração"
Aponte: *Esses objetivos estão em tensão. Qual é prioritário?*

**Requisito com escopo indefinido:**
> "Fazer o design de toda a área de configurações"
Pergunte: *Quais configurações? Para qual versão? Para quais dispositivos?*

**Requisito baseado em suposição não validada:**
> "Os usuários querem poder exportar para PDF"
Pergunte: *Como sabemos que querem? Existe dado ou é hipótese?*

---

## Formato de Requisito de Design

Após processar o input, produza requisitos de design no formato:

```
REQUISITO DE DESIGN: [Número]
ORIGEM: [De onde veio — PRD, ticket, conversa, pesquisa]
DESCRIÇÃO: [O que o design precisa garantir — comportamento, não solução]
CRITÉRIO: [Como verificar se foi atendido]
USUÁRIO AFETADO: [Quem e em qual contexto]
IMPACTO SE IGNORADO: [O que acontece se este requisito não for atendido]
PRIORIDADE: [Essencial / Importante / Desejável]
DÚVIDA ABERTA: [O que ainda precisa ser confirmado — com responsável]
```

---

## Classificação de Constraints

Documente separadamente:

| Tipo | Descrição | Exemplos |
|------|-----------|---------|
| **Constraints reais** | Limitações não negociáveis | Regulatório, técnico bloqueante, prazo fixo |
| **Constraints assumidas** | Parecem existir mas não foram confirmadas | "Não podemos mudar o backend" — confirmado? |
| **Preferências** | O que stakeholders gostariam | "Prefiro que fique na mesma tela" |

Diferenciar constraints reais de preferências é uma das habilidades mais valiosas nesta fase. Muitas restrições que parecem fixas são negociáveis.

---

## Glossário de Termos Ambíguos

Quando o time usar termos vagos, defina e confirme o significado antes de prosseguir:

| Termo ambíguo | O que pode significar | Como confirmar |
|---------------|----------------------|----------------|
| "Simples" | Menos etapas / Visual limpo / Fácil de aprender | Perguntar: simples para quem? |
| "Rápido" | Performance técnica / Menos cliques / Aprendizado rápido | Definir a métrica |
| "Intuitivo" | Sem onboarding / Consistente com padrões | Especificar o contexto |
| "Moderno" | Estético / Tecnológico / Minimalista | Pedir referências visuais |
| "Melhorar" | Corrigir bug / Redesign / Otimizar conversão | Definir o critério de sucesso |
