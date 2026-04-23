# How to Use — Loft Design Agent Toolkit

Este guia é para designers que querem começar a usar o toolkit. Você não precisa entender tudo de uma vez — comece pelo básico e vá expandindo conforme o uso.

---

## O que é este toolkit

O Loft Design Agent Toolkit é um repositório de agentes, skills, playbooks e templates que você usa junto com Claude para estruturar e acelerar o seu trabalho de design.

Pense nisso como um conjunto de "modos de trabalho" que você pode acionar dependendo do momento do projeto. Cada agente sabe exatamente o que fazer, o que perguntar, e o que produzir.

**O que o toolkit faz:**
- Estrutura o problema antes de você começar a desenhar
- Mapeia jornadas com estados e edge cases completos
- Revisa designs com heurísticas aplicadas ao seu contexto
- Valida copies contra o guia de voz do produto
- Gera specs de tracking prontas para o dev
- Verifica se o handoff está completo antes de passar para eng

**O que o toolkit não faz:**
- Não substitui o design no Figma
- Não toma decisões por você — estrutura o raciocínio para você decidir melhor
- Não é uma checklist burocrática — use o que fizer sentido para o projeto

---

## Pré-requisitos

Você precisa de:

1. **Claude** — via claude.ai, Claude Code, ou qualquer interface que aceite arquivos de contexto
2. **Este repositório clonado localmente** ou acessível para referência

```bash
git clone https://github.com/loft/design-agent-toolkit
cd loft-design-agent-toolkit
```

3. Os arquivos de `/context` preenchidos com os dados reais do produto (veja seção abaixo)

---

## Setup inicial (faça uma vez)

### 1. Preencha o contexto do produto

A pasta `/context` é o que diferencia este toolkit de um toolkit genérico. Sem ela, os agentes trabalham com boas práticas gerais — com ela, eles trabalham com o contexto real do Loft.

Abra cada arquivo e preencha:

| Arquivo | O que colocar |
|---------|---------------|
| `context/product-principles.md` | Princípios de design e produto do Loft |
| `context/personas.md` | Personas atuais com contextos de uso |
| `context/design-system-tokens.md` | Tokens de cor, tipografia, spacing e componentes principais |
| `context/brand-voice.md` | Guia de voz e tom, exemplos de copies aprovados e reprovados |
| `context/target-audiences.md` | Segmentos de público com particularidades de comunicação |

> **Dica:** Não precisa ser perfeito para começar. Um contexto parcial já é melhor do que nenhum. Vá refinando conforme usar.

### 2. Teste com um projeto real

Escolha um projeto pequeno em andamento e passe pelo `playbooks/quick-product-change.md`. É o mais rápido e te dá uma ideia de como o toolkit funciona antes de usar em algo maior.

---

## Como usar no dia a dia

### Opção A — Pelo claude.ai (mais simples)

1. Abra uma nova conversa no claude.ai
2. Faça upload do arquivo do agente que você quer usar (ex: `agents/project-framing.md`)
3. Faça upload dos arquivos de contexto relevantes (`context/personas.md`, etc.)
4. Cole o template correspondente no chat e diga: *"Use este agente para me ajudar com [projeto]"*

### Opção B — Pelo Claude Code (mais poderoso)

Se você usa Claude Code no terminal:

```bash
# Navegue até a pasta do seu projeto de design
cd ~/projetos/meu-projeto

# Inicie o Claude Code referenciando o toolkit
claude --context ~/loft-design-agent-toolkit/agents/project-framing.md \
       --context ~/loft-design-agent-toolkit/context/personas.md
```

Ou adicione ao `CLAUDE.md` do seu projeto de design uma referência ao toolkit para que seja carregado automaticamente.

### Opção C — Referência manual (mais flexível)

Abra o arquivo do agente que você quer usar, copie o conteúdo, e cole no início de uma conversa com Claude como contexto. Funciona em qualquer interface.

---

## Qual agente usar em cada situação

Use esta tabela como referência rápida:

| Situação | Use este agente / playbook |
|----------|---------------------------|
| Recebi um brief e não sei por onde começar | `playbooks/start-from-scratch.md` |
| Recebi um PRD e preciso transformar em design | `playbooks/brief-to-design.md` |
| Mudança pequena em feature existente | `playbooks/quick-product-change.md` |
| Preciso definir o problema antes de desenhar | `agents/project-framing.md` |
| Preciso mapear telas e estados da jornada | `agents/journey-builder.md` |
| Quero revisar meu design antes de apresentar | `agents/solution-critique.md` |
| Preciso revisar copies e consistência de DS | `agents/ds-copy-review.md` |
| Preciso gerar spec de tracking para o dev | `agents/tracking-handoff.md` |
| Quero verificar se o handoff está completo | `agents/dev-handoff.md` |

---

## Entendendo a estrutura

```
/agents      → Orquestradores. Conduzem uma tarefa completa, do início ao output.
/skills      → Conhecimento modular. Os agentes carregam skills automaticamente.
              Você também pode usar skills diretamente para tarefas pontuais.
/playbooks   → Sequências. Dizem quais agentes usar, em qual ordem, com quais gates.
/templates   → Outputs estruturados. Os agentes preenchem esses arquivos.
/context     → Contexto do produto. O que torna o toolkit específico para o Loft.
/docs        → Este arquivo e o guia de contribuição.
```

Você interage principalmente com **agents** e **playbooks**. As **skills** funcionam em segundo plano. Os **templates** são os documentos que você vai acumular por projeto.

---

## Dicas de uso

**Comece pelo problem frame, sempre.**
Mesmo em projetos pequenos, ter o problem statement claro muda a qualidade de tudo que vem depois. Leva 30 minutos e poupa horas de retrabalho.

**Use os gates dos playbooks como check-ins reais.**
Os checklists entre fases existem para prevenir que você avance com uma base fraca. Se um gate falha, é sinal de que há algo a resolver — não pule.

**Salve os templates preenchidos junto ao projeto.**
Crie uma pasta de artefatos no seu projeto de design (ou no Notion, ou no Figma) e salve os templates preenchidos. Eles viram documentação viva do projeto.

**O toolkit é um ponto de partida, não uma receita.**
Se um agente está pedindo informação que você não tem, documente como `[A VALIDAR]` e continue. Um framing com lacunas explícitas é melhor do que um framing com lacunas escondidas.

**Itere no contexto conforme aprender.**
Toda vez que você usar o toolkit e sentir que a resposta ficou genérica demais, provavelmente é porque um arquivo de contexto está incompleto. Adicione o que faltou e o próximo uso vai ser melhor.

---

## Fluxo de trabalho típico

```
Projeto novo chegou
       ↓
Abro o playbook adequado
       ↓
Chamo o agente de project-framing
       ↓
Salvo o problem-frame.md preenchido
       ↓
Chamo o agente de journey-builder
       ↓
Salvo o journey-spec.md preenchido
       ↓
Design no Figma (usando os specs como referência)
       ↓
Chamo o agente de solution-critique
       ↓
Ajusto o design com base no critique
       ↓
Chamo ds-copy-review
       ↓
Chamo tracking-handoff + dev-handoff em paralelo
       ↓
Movo para "Pronto para Dev" no Figma
```

---

## Perguntas frequentes

**Preciso usar todos os agentes em todo projeto?**
Não. Para mudanças pequenas, o `quick-product-change.md` pula vários agentes. Use o que fizer sentido para o escopo.

**Posso usar os agentes fora de ordem?**
Sim, mas alguns dependem do output de outros. O `journey-builder` funciona melhor com o `problem-frame.md` preenchido. O `solution-critique` funciona melhor com o `journey-spec.md`. Siga a ordem recomendada quando puder.

**O que faço se o agente pedir uma informação que não tenho?**
Marque como `[A VALIDAR]` e continue. O objetivo é ter clareza sobre o que está confirmado e o que ainda é suposição — não bloquear o trabalho por falta de uma informação.

**Posso adaptar os agentes para o meu projeto específico?**
Sim. Os arquivos são markdown — edite à vontade para o contexto do seu projeto. Se a adaptação for útil para o time inteiro, considere abrir uma PR (veja `how-to-contribute.md`).

**O toolkit funciona com outros modelos além do Claude?**
Os arquivos são texto puro e funcionam com qualquer modelo que aceite contexto longo. O formato de SKILL.md é compatível com Claude Code nativamente. Para outros modelos, cole o conteúdo manualmente como contexto.
