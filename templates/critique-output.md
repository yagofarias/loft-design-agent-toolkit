---
version: "2.1"
agent: design-critique
status: "[Rascunho | Entregue]"
---

# Critique Output

**Projeto:** [Nome]
**Designer:** [Nome]
**Jornada revisada:** [Nome da jornada ou feature]
**Avaliado por:** [Nome(s) — expert review solo ou sessão de grupo]
**Estágio do design:** [Exploração / Refinamento / Pré-handoff]
**Data:** [DD/MM/AAAA]
**Figma:** [Link]
**Design Doc:** [Link para templates/design-doc.md]

---

## Escopo desta rodada

*O que estava em escopo para este critique e o que foi explicitamente deixado de fora. Sem escopo definido, o feedback perde foco.*

**Em escopo:** [Ex: fluxo de análise de fiança — do intake ao parecer. Foco em usabilidade e copy.]

**Fora de escopo:** [Ex: telas de onboarding, responsivo mobile, animações — serão avaliados na próxima iteração.]

**Decisões intencionais do designer:** [Escolhas deliberadas que podem parecer estranhas mas têm razão de ser — para o crítico não flagrar o que já foi pensado. Ex: "O botão de cancelar foi omitido intencionalmente nesta etapa por restrição de negócio discutida com PM."]

---

## Gate de Aprovação

> Decisão sobre se este design pode avançar para o `delivery-handoff`.

- ☐ ✅ **Aprovado** — sem problemas bloqueantes, pode ir para handoff
- ☐ ⚠️ **Aprovado com ressalvas** — problemas de severidade ≤ 2, podem ser corrigidos em paralelo ao handoff
- ☐ ❌ **Reprovado** — há problemas de severidade 3 ou 4 que precisam ser resolvidos antes de avançar

**Justificativa:** [1-2 frases explicando a decisão]

---

> Decisão sobre se este design pode avançar para o `delivery-handoff`.

- ☐ ✅ **Aprovado** — sem problemas bloqueantes, pode ir para handoff
- ☐ ⚠️ **Aprovado com ressalvas** — problemas de severidade ≤ 2, podem ser corrigidos em paralelo ao handoff
- ☐ ❌ **Reprovado** — há problemas de severidade 3 ou 4 que precisam ser resolvidos antes de avançar

**Justificativa:** [1-2 frases explicando a decisão]

---

## Sumário Executivo

*O que o design acerta, os 2-3 problemas de maior impacto e o que fazer a seguir. Máximo 5 frases.*

[escreva aqui]

---

## Problemas Identificados

*Tabela unificada ordenada por severidade (4 → 1). A metodologia de avaliação está em `skills/heuristic-evaluation.md`.*

*Escala: **4** = bloqueia avanço · **3** = corrigir antes do lançamento · **2** = melhoria importante · **1** = cosmético*
*Tipos: `Usabilidade` · `Acessibilidade` · `Copy` · `Design System` · `Opinião` — marcar Opinião quando não houver heurística objetiva por trás*

| # | Tipo | Sev. | Problema | Onde ocorre | Sugestão |
|---|------|------|---------|-------------|----------|
| 1 | [Tipo] | [4–1] | [Descrição objetiva — o que o usuário não consegue fazer ou entende errado] | [Tela / componente / momento] | [O que fazer — específico] |

---

## Copies — Antes e Depois

*Preencha apenas para copies com problemas de severidade 2 ou maior. Formato lado a lado facilita a revisão pelo designer.*

*Se não houver problemas de copy, escreva "Nenhum problema de copy identificado."*

### Copy #1

| | Texto |
|--|-------|
| **Como está** | [copy atual] |
| **Problema** | [por que não funciona — tom, clareza, tamanho, etc.] |
| **Sugestão A** | [alternativa — justificativa em uma frase] |
| **Sugestão B** | [alternativa — se houver uma segunda opção] |

---

## Design System

*Consistência com o Copan. Preencha apenas o que foi encontrado.*

### Componentes

| Componente | Variante usada | Existe no Copan? | Tokens corretos? | Status | Ação |
|-----------|----------------|-----------------|------------------|--------|------|
| [Nome] | [Variante] | Sim / Não | Sim / Não | ✅ / ⚠️ / ❌ | [O que fazer] |

### Componentes novos identificados

*Componentes que não existem no Copan e precisam de proposta antes do handoff.*

| Componente proposto | Baseado em | O que é diferente | Prioridade |
|--------------------|-----------|-------------------|-----------|
| [Nome] | [Componente existente mais próximo] | [O que justifica ser novo] | Antes do handoff / Pós-lançamento |

*Se nenhum componente novo foi identificado, escreva "Nenhum componente novo identificado."*

### Terminologia e Nomenclatura

*Termos ou labels usados de forma inconsistente entre telas — o usuário vê palavras diferentes para a mesma coisa. Preencha apenas se encontrado.*

| Termo encontrado | Onde aparece | Padronizar para | Motivo |
|-----------------|-------------|----------------|--------|
| [Como está no design] | [Telas afetadas] | [Termo correto conforme brand-voice.md ou glossário local] | [Ex: alinha com glossário global / é o termo do produto] |

*Se não há inconsistências, escreva "Terminologia consistente em toda a jornada."*

---

## Estados Ausentes ou Incompletos

*Estados obrigatórios que estão faltando ou incompletos no design.*

| Tela / Componente | Estado faltando | Impacto para o usuário | Prioridade |
|-------------------|----------------|----------------------|-----------|
| [Nome] | [Ex: estado de erro da API] | [O que o usuário experimenta se não tratado] | P0 / P1 / P2 |

*Se todos os estados estiverem cobertos, escreva "Todos os estados obrigatórios estão cobertos."*

---

## Pontos Positivos

*O que está funcionando bem e deve ser preservado — específico, não genérico. Critique sem pontos positivos não é critique, é ataque.*

- [Ponto concreto — ex: "A hierarquia visual da tela de confirmação está clara e guia o usuário sem ambiguidade"]
- [Ponto concreto]

---

## Validação contra o Design Doc

*Verifica se o design entrega o que foi prometido nas seções 1 e 2 do design-doc.*

**Problema declarado:**
> [Copiar da seção 1.1 do design-doc.md]

**O design resolve o problema?**
- ☐ Sim, completamente
- ☐ Sim, parcialmente — [o que falta ou não está coberto]
- ☐ Não — [por quê]

**Métricas de sucesso definidas:**
> [Copiar da seção 2.2 do design-doc.md — métrica primária e guardrail]

**Este design viabiliza as métricas?**
- ☐ Sim — [por quê este design permite medir o que foi definido]
- ☐ Parcialmente — [o que está faltando para medir]
- ☐ Não — [o que precisa mudar no design para as métricas serem mensuráveis]

---

## Próximos Passos

*Ações ordenadas por prioridade. Itens com severidade 3-4 devem estar resolvidos antes de avançar.*

| # | Ação | Severidade relacionada | Responsável | Prazo |
|---|------|----------------------|-------------|-------|
| 1 | [Ação específica e verificável] | [4/3/2/1] | Designer | Antes do handoff |
| 2 | [Ação específica e verificável] | [2/1] | Designer / DS | Pode ser paralelo |
