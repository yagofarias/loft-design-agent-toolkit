# How to Use — Loft Design Agent Toolkit

Este guia é para designers que querem começar a usar o toolkit. Você não precisa entender tudo de uma vez — comece pelo básico e vá expandindo conforme o uso.

---

## O que é este toolkit

O Loft Design Agent Toolkit é um repositório de agentes, skills, playbooks e templates que você usa junto com Claude para estruturar e acelerar o seu trabalho de design.

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
git clone https://github.com/yagofarias/loft-design-agent-toolkit
cd loft-design-agent-toolkit
```

---

## Setup inicial (faça uma vez)

### 1. Preencha o contexto global

Os arquivos de `/context/global` são mantidos pelo time central de design e valem para todos os squads. Verifique se estão atualizados antes de usar:

| Arquivo | O que contém |
|---------|--------------|
| `context/global/product-principles.md` | Princípios de design e produto da Loft |
| `context/global/design-system.md` | Links e referência rápida do Copan (DS da Loft) |
| `context/global/brand-voice.md` | Guia de voz e tom da marca Loft |

### 2. Preencha o contexto do seu squad

Os arquivos de `/context/local` são mantidos por você e pelo seu squad. São o que torna os outputs do toolkit específicos para o seu domínio:

| Arquivo | O que colocar | Obrigatório? |
|---------|---------------|-------------|
| `context/local/context.md` | Regras de negócio, terminologia, constraints, métricas | ✅ Sempre |
| `context/local/personas.md` | Personas específicas do seu segmento | Se o squad tiver personas próprias |
| `context/local/target-audiences.md` | Segmentações de público (B2B/B2C, tamanho de empresa) | Se a comunicação variar por segmento |
| `context/local/brand-voice-local.md` | Tom específico do squad que complementa o global | Se o squad tiver tom próprio |

> **Dica:** Comece preenchendo só o `context/local/context.md`. Mesmo parcialmente preenchido, ele já melhora muito a qualidade dos outputs.

### 3. Teste com um projeto real

Escolha um projeto pequeno em andamento e passe pelo `playbooks/quick-product-change.md`. É o mais rápido e te dá uma ideia de como o toolkit funciona antes de usar em algo maior.

---

## Como usar no dia a dia

### Opção A — Pelo claude.ai (mais simples)

1. Abra uma nova conversa no claude.ai
2. Faça upload do arquivo do agente que você quer usar (ex: `agents/project-framing.md`)
3. Faça upload dos arquivos de contexto relevantes:
   - `context/global/product-principles.md`
   - `context/global/brand-voice.md`
   - `context/local/context.md`
   - (outros opcionais dependendo do projeto)
4. Cole o template correspondente no chat e diga: *"Use este agente para me ajudar com [projeto]"*

### Opção B — Pelo Claude Code (mais poderoso)

```bash
cd ~/projetos/meu-projeto

claude --context ~/loft-design-agent-toolkit/agents/project-framing.md \
       --context ~/loft-design-agent-toolkit/context/global/product-principles.md \
       --context ~/loft-design-agent-toolkit/context/local/context.md
```

### Opção C — Referência manual (mais flexível)

Abra o arquivo do agente, copie o conteúdo e cole no início de uma conversa com Claude como contexto. Funciona em qualquer interface.

---

## Qual agente usar em cada situação

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
| Preciso sintetizar pesquisa antes de começar | `agents/ux-research-primer.md` |
| Quero ver como o mercado resolve esse problema | `agents/benchmark-research.md` |

---

## Entendendo a estrutura

```
/agents      → Orquestradores. Conduzem uma tarefa completa, do início ao output.
/skills      → Conhecimento modular. Os agentes carregam skills automaticamente.
/playbooks   → Sequências. Dizem quais agentes usar, em qual ordem, com quais gates.
/templates   → Outputs estruturados. Os agentes preenchem esses arquivos.
/context
  /global    → Contexto da Loft. Mantido pelo time central. Vale para todos.
  /squad     → Contexto do seu squad. Mantido por você. Específico do seu domínio.
/docs        → Este arquivo e o guia de contribuição.
```

---

## Dicas de uso

**Preencha o contexto do squad antes de qualquer coisa.**
É o que faz os agentes responderem com o vocabulário certo, respeitarem as regras de negócio do seu domínio e gerarem outputs úteis ao invés de genéricos.

**Comece pelo problem frame, sempre.**
Mesmo em projetos pequenos, ter o problem statement claro muda a qualidade de tudo que vem depois.

**Use os gates dos playbooks como check-ins reais.**
Os checklists entre fases existem para prevenir que você avance com uma base fraca. Se um gate falha, há algo a resolver — não pule.

**Salve os templates preenchidos junto ao projeto.**
Eles viram documentação viva — úteis para onboarding de novos membros, revisões retrospectivas e auditorias.

**Itere no contexto do squad conforme aprender.**
Toda vez que o output parecer genérico demais, provavelmente é porque o `context/local/context.md` está incompleto. Adicione o que faltou.

---

## Fluxo de trabalho típico

```
Projeto novo chegou
       ↓
Abro o playbook adequado
       ↓
Verifico se context/local/context.md está atualizado
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
Não. Para mudanças pequenas, o `quick-product-change.md` pula vários agentes.

**O contexto do squad pode ficar vazio?**
Pode, mas os outputs vão ser genéricos. Vale 30 minutos preenchendo o básico antes do primeiro uso.

**Quem mantém os arquivos de `/context/global`?**
O time central de design / design ops. Se algo estiver desatualizado, sinalize via PR ou para o responsável pelo toolkit.

**Posso ter múltiplos arquivos de contexto de squad?**
Sim. Se você atua em mais de um domínio, pode manter versões diferentes da pasta `/context/local` e carregar a que for relevante para cada projeto.

**O toolkit funciona com outros modelos além do Claude?**
Os arquivos são texto puro e funcionam com qualquer modelo que aceite contexto longo. O formato de SKILL.md é compatível com Claude Code nativamente.
