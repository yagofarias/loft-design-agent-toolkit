# Loft Design Agent Toolkit

Toolkit de agentes de design para o time da Loft. Ajuda designers a estruturar problemas, planejar pesquisas, explorar soluções, revisar designs e preparar handoffs — do brief ao dev, com contexto do produto sempre presente.

---

## Início rápido

```bash
git clone https://github.com/yagofarias/loft-design-agent-toolkit
cd loft-design-agent-toolkit
claude
```

No **Claude Code app**: clique em **Local** na barra superior e selecione a pasta clonada.

Na primeira sessão, o toolkit se apresenta e sugere `/context-setup` para configurar o contexto do seu squad. A partir daí, todos os projetos ficam organizados em `projects/[nome-do-projeto]/`.

### Fluxo principal

```
/context-setup → /framing → /research-plan → /solution-craft → /critique → /handoff
```

### Comandos disponíveis

| Comando | O que faz |
|---------|-----------|
| `/context-setup` | Configura o contexto do squad — oferece pesquisa web e análise de documentos para montar um rascunho rápido |
| `/framing` | Transforma qualquer ponto de partida em um Design Doc estruturado |
| `/research-plan` | Transforma hipóteses do design-doc em plano de pesquisa executável com método, participantes e roteiros |
| `/solution-craft` | Explora direções de solução e mapeia fluxos, estados e artefatos |
| `/critique` | Revisa um design — aceita link do Figma ou prints |
| `/handoff` | Prepara a spec completa para dev |
| `/retro` | Retrospectiva da sessão — diagnóstico do modelo + input do designer, salvo como arquivo no projeto |
| `/memory` | Salva o estado da sessão atual (arquivos gerados, decisões, próximos passos) e gera um bloco de contexto compacto para colar no início da próxima conversa — evita perder contexto entre sessões |

---

## O que o toolkit entrega

- **Design Doc estruturado** com problema, métricas, personas, cronograma e decisões registradas
- **Plano de Pesquisa** com objetivos, hipóteses, método, participantes, roteiros e plano de análise
- **Direction cards** com abordagens ancoradas em referências de mercado, antes de ir ao Figma
- **Journey spec** completa com fluxos, estados, edge cases, copies e acessibilidade
- **Critique report** com heurísticas de usabilidade, composição visual, WCAG, copy e consistência com o Copan
- **Tracking spec** com eventos de analytics, payloads e checklist de LGPD

---

## Agentes

| Agente | O que faz |
|--------|-----------|
| `project-framing` | Transforma qualquer ponto de partida (brief, PRD, RFC, SDD ou ideia) em um Design Doc. Aceita documentos existentes como input. |
| `research-plan` | Planeja pesquisas a partir de hipóteses do design-doc ou do zero. Consulta o acervo do squad (Dovetail/NotebookLM) antes de planejar. Gera roteiros, plano de análise e sintetiza achados pós-campo. |
| `solution-craft` | Explora direções de solução (direction cards) e mapeia fluxos, estados, edge cases e artefatos de tangibilização. |
| `design-critique` | Avalia o design em uma passagem: usabilidade, composição visual, WCAG, estados, copy e Copan. Gera relatório com gate de aprovação. |
| `delivery-handoff` | Gera a spec de analytics e valida se o design está completamente documentado para o dev. |

---

## Skills

| Skill | O que faz |
|-------|-----------|
| `gut-check` | Sabatina de 5 perguntas críticas antes de avançar — inclui zoom-out contextual |
| `problem-scoping` | Estrutura problem statements, hipóteses e requisitos de design |
| `research-archive` | Consulta o acervo de pesquisas do squad antes de planejar um novo estudo — evita pesquisa redundante |
| `interview-script` | Gera roteiro de entrevista em 5 blocos com perguntas abertas, probes e notas para o entrevistador |
| `summarize-interview` | Sintetiza transcripts em temas, jobs identificados, pain points, workarounds e surpresas |
| `user-flows` | Mapeia happy path, alternativos, erros e fluxos com múltiplos atores (B2B) |
| `state-coverage` | Garante cobertura de todos os estados: loading, erro, vazio, aprovação, expirado |
| `edge-cases` | Checklist de cenários extremos — universal + específicos da Loft (fintech, B2B) |
| `heuristics` | 10 heurísticas de Nielsen + avaliação tipográfica + WCAG 2.1 + exemplos do contexto Loft |
| `ux-writing` | Critérios de copy por tipo de elemento, ancorados no brand-voice da Loft |
| `copan-check` | Valida componentes e tokens contra o Copan — detecta sistema legado, usa Figma MCP quando disponível |
| `analytics-events` | Modela eventos com taxonomia PT-BR, tipos de propriedade e checklist LGPD |

---

## Contexto

O toolkit carrega dois níveis de contexto que tornam os outputs específicos para o seu domínio:

**Global** (`context/global/`) — válido para todo o time Loft:
- `product-principles.md` — princípios, missão e valores
- `brand-voice.md` — voz, tom e glossário
- `design-system.md` — referência do Copan: componentes, tokens, sistemas legados e regras de composição

**Squad** (`context/local/`) — específico do seu domínio, nunca sobrescrito por updates:
- `context.md` — regras de negócio, terminologia, constraints
- `personas.md` — perfis de usuário e jobs-to-be-done
- `competitors.md` — mapeamento competitivo
- `target-audiences.md` — segmentos e guias de comunicação
- `brand-voice-local.md` — ajustes de tom do domínio
- `research-archive.md` — acervo de pesquisas (resumo do Dovetail/NotebookLM)

---

## Documentação

- [Como usar](docs/como-usar.md) — guia completo de uso, workflows e perguntas frequentes
- [Como contribuir](docs/como-contribuir.md) — convenções de commits, processo de PR e como escrever agentes e skills

---

## Contribuindo

Veja [docs/como-contribuir.md](docs/como-contribuir.md).
