# Loft Design Agent Toolkit

Toolkit de agentes de design para o time da Loft. Ajuda designers a estruturar problemas, explorar soluções, revisar designs e preparar handoffs — do brief ao dev, com contexto do produto sempre presente.

---

## Início rápido

```bash
git clone https://github.com/yagofarias/loft-design-agent-toolkit
cd loft-design-agent-toolkit
claude
```

No **Claude Code app**: clique em **Local** na barra superior e selecione a pasta clonada.

Na primeira sessão, o toolkit se apresenta e sugere `/setup` para configurar o contexto do seu squad. A partir daí, todos os projetos ficam organizados em `projects/[nome-do-projeto]/`.

### Comandos disponíveis

| Comando | O que faz |
|---------|-----------|
| `/setup` | Configura o contexto do squad — faça isso primeiro |
| `/framing` | Transforma qualquer ponto de partida em um Design Doc estruturado |
| `/solution-mapping` | Explora direções de solução e mapeia fluxos, estados e artefatos |
| `/critique` | Revisa um design — aceita link do Figma ou prints |
| `/handoff` | Prepara a spec completa para dev |

---

## O que o toolkit entrega

- **Design Doc estruturado** com problema, métricas, personas, cronograma e decisões registradas
- **Direction cards** com abordagens ancoradas em referências de mercado, antes de ir ao Figma
- **Journey spec** completa com fluxos, estados, edge cases, copies e acessibilidade
- **Critique report** com heurísticas de usabilidade, WCAG, copy e consistência com o Copan
- **Tracking spec** com eventos de analytics, payloads e checklist de LGPD

---

## Agentes

| Agente | O que faz |
|--------|-----------|
| `project-framing` | Transforma qualquer ponto de partida (brief, PRD, RFC, SDD ou ideia) em um Design Doc. Aceita documentos existentes como input. |
| `solution-mapping` | Explora direções de solução (direction cards) e mapeia fluxos, estados, edge cases e artefatos de tangibilização. |
| `design-critique` | Avalia o design em uma passagem: usabilidade, WCAG, estados, copy e Copan. Gera relatório com gate de aprovação. |
| `delivery-handoff` | Gera a spec de analytics e valida se o design está completamente documentado para o dev. |

---

## Skills

| Skill | O que faz |
|-------|-----------|
| `gut-check` | Sabatina de 5 perguntas críticas antes de avançar — inclui zoom-out contextual |
| `problem-scoping` | Estrutura problem statements, hipóteses e requisitos de design |
| `user-flows` | Mapeia happy path, alternativos, erros e fluxos com múltiplos atores (B2B) |
| `state-coverage` | Garante cobertura de todos os estados: loading, erro, vazio, aprovação, expirado |
| `edge-cases` | Checklist de cenários extremos — universal + específicos da Loft (fintech, B2B) |
| `heuristics` | 10 heurísticas de Nielsen + WCAG 2.1 + exemplos do contexto Loft |
| `ux-writing` | Critérios de copy por tipo de elemento, ancorados no brand-voice da Loft |
| `copan-check` | Valida componentes e tokens contra o Copan — aceita Figma URL ou prints |
| `analytics-events` | Modela eventos com taxonomia PT-BR, tipos de propriedade e checklist LGPD |

---

## Documentação

- [Como usar](docs/como-usar.md) — guia completo de uso, workflows e perguntas frequentes
- [Como contribuir](docs/como-contribuir.md) — convenções de commits, processo de PR e como escrever agentes e skills

---

## Contribuindo

Veja [docs/como-contribuir.md](docs/como-contribuir.md).
