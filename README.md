# Loft Design Agent Toolkit

Um toolkit de agentes de design para o time da Loft — agentes, skills, playbooks e templates para estruturar problemas, mapear jornadas, revisar soluções e gerar specs prontas para dev usando Claude.

---

## Agentes

Quatro agentes que cobrem o processo completo de design. Cada um pode ser usado de forma independente ou em sequência via playbook.

| Agente | O que faz |
|--------|-----------|
| `project-framing` | Transforma qualquer ponto de partida (brief, PRD, RFC, SDD ou ideia bruta) em um Design Doc estruturado. Aceita documentos existentes como input e extrai o que é relevante para design. Gera o documento vivo que guia o projeto inteiro. |
| `journey-builder` | Mapeia fluxos, estados, edge cases e dependências a partir do Design Doc. Preenche a seção 4 (Solução) do documento vivo. |
| `design-critique` | Avalia o design em uma passagem: heurísticas de usabilidade, acessibilidade WCAG, completude de estados, clareza de copy e consistência com o DS. Relatório consolidado. |
| `delivery-handoff` | Gera a spec de eventos de analytics e valida se o design está completamente documentado para o dev — sem ambiguidade, sem estados faltando. |

---

## Skills

Unidades de conhecimento modulares carregadas pelos agentes.

| Skill | O que faz | Carregada por |
|-------|-----------|--------------|
| `gut-check` | Sabatina de 5 perguntas críticas antes de avançar — perspectivas de produto, negócio, design e persona | todos os agentes |
| `problem-scoping` | Estrutura problem statements, gera hipóteses verificáveis e traduz requisitos em necessidades de design | project-framing |
| `user-flows` | Mapeia happy path, fluxos alternativos, erros e fluxos com múltiplos atores (B2B) | journey-builder, delivery-handoff |
| `state-coverage` | Garante que todos os estados de UI foram identificados: loading, erro, vazio, aprovação, expirado | journey-builder, design-critique, delivery-handoff |
| `edge-cases` | Checklist de cenários extremos — universal + específicos da Loft (documentos, financeiro, aprovação, B2B) | journey-builder, design-critique, delivery-handoff |
| `heuristics` | Avaliação com as 10 heurísticas de Nielsen + WCAG 2.1 + exemplos do contexto Loft | design-critique |
| `ux-writing` | Critérios de copy por tipo de elemento — aplica o brand-voice.md em contextos de UI e fintech | design-critique |
| `copan-check` | Valida componentes e tokens contra o Copan — aceita link do Figma ou prints | design-critique, delivery-handoff |
| `analytics-events` | Modela eventos de analytics com taxonomia PT-BR, event/user/context properties e checklist LGPD | delivery-handoff |

---

## Playbooks

Sequências passo a passo com gates de qualidade entre as fases.

| Playbook | Quando usar |
|----------|------------|
| `start-from-scratch` | Produto novo ou feature grande do zero |
| `brief-to-design` | Recebeu um PRD, SDD ou brief formal para executar |
| `quick-product-change` | Mudança pequena e incremental em feature existente |
| `setup-local-context` | Primeira vez usando o toolkit — preencha o contexto do seu squad |

---

## Estrutura de Contexto

```
context/
  global/                  ← mantido pelo time central de design
    product-principles.md  ← princípios, missão e valores da Loft
    brand-voice.md         ← voz, tom e guia de writing
    design-system.md       ← links e referência rápida do Copan

  local/                   ← mantido pelo seu squad (preencha antes de usar)
    README.md              ← instruções
    context.md             ← regras de negócio, terminologia, constraints
    personas.md            ← personas específicas do squad
    target-audiences.md    ← segmentos de público e guias de comunicação
    brand-voice-local.md   ← ajustes de tom específicos do domínio
    competitors.md         ← mapeamento competitivo do squad
```

---

## Templates

Outputs estruturados gerados pelos agentes ao longo do processo.

| Template | Gerado por | O que contém |
|----------|-----------|--------------|
| `design-doc.md` | `project-framing` | Documento vivo do projeto — TL;DR, cronograma, contexto (problema, guardrail de impacto, hipóteses), objetivo e métricas, usuários, solução, riscos e entrega |
| `journey-spec.md` | `journey-builder` | Fluxo principal, estados, edge cases e dependências |
| `critique-output.md` | `design-critique` | Relatório de heurísticas, acessibilidade, copy e DS por severidade |
| `tracking-spec.md` | `delivery-handoff` | Spec de eventos de analytics com payloads e funil de conversão |

> O `design-doc.md` é o documento central. Ele começa preenchido pelo `project-framing` e evolui ao longo do projeto — seções 4-6 são completadas pelos agentes seguintes.

---

## Instalação e uso

### Claude Code (app ou terminal)

**1. Clone o repositório:**
```bash
git clone https://github.com/yagofarias/loft-design-agent-toolkit
```

**2. Adicione a pasta no Claude Code:**

No app Claude Code, clique em **Local** na barra superior e selecione a pasta `loft-design-agent-toolkit` que você acabou de clonar. O `CLAUDE.md` na raiz é lido automaticamente.

Pelo terminal:
```bash
cd loft-design-agent-toolkit
claude
```

**3. Na primeira sessão**, o toolkit se apresenta e sugere `/setup` para configurar o contexto do seu squad.

**4. Para cada projeto**, ao rodar qualquer comando, o toolkit cria automaticamente uma pasta em `projects/[nome-do-projeto]/` e organiza todos os arquivos gerados lá.

**Atualizando o toolkit:** não precisa saber git. Abra o Claude Code na pasta do toolkit e diga: *"me ajude a atualizar o toolkit"*. O Claude roda o `git pull` de forma segura, garantindo que seu contexto local não seja sobrescrito.

**Segurança do contexto local:** os arquivos de `context/local/` que você preencheu estão protegidos por `.gitignore` e `skip-worktree` — atualizações do toolkit nunca os sobrescrevem. Por precaução, recomendamos manter uma cópia da pasta `context/local/` no Google Drive ou Notion do seu squad.

**Comandos disponíveis:**

| Comando | O que faz |
|---------|-----------|
| `/setup` | Configura o contexto do squad — faça isso primeiro |
| `/framing` | Inicia um project framing |
| `/journey` | Mapeia fluxos e estados |
| `/critique` | Revisa um design (URL do Figma ou prints) |
| `/handoff` | Prepara spec completa para dev |

Você pode passar contexto direto no comando: `/framing preciso redesenhar o fluxo de análise de fiança`

### Claude Cowork / claude.ai

Carregue o arquivo do agente que quiser usar como contexto e inicie a conversa. Veja `docs/como-usar.md` para exemplos detalhados.

---

## Por onde começar

1. Clone o repositório e rode `claude` na pasta (Claude Code) ou carregue os arquivos como contexto (Cowork)
2. Execute `/setup` ou abra `playbooks/setup-local-context.md` para preencher o contexto do seu squad
3. Verifique se `context/global/` está atualizado para a Loft
4. Use `/framing` ou `agents/project-framing.md` para começar um projeto

## Contribuindo

Veja `docs/como-contribuir.md`.
