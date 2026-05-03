# Loft Design Agent Toolkit

Um toolkit de agentes de design para o time da Loft — agentes, skills, playbooks e templates para estruturar problemas, mapear jornadas, revisar soluções e gerar specs prontas para dev usando Claude.

---

## Agentes

Quatro agentes que cobrem o processo completo de design. Cada um pode ser usado de forma independente ou em sequência via playbook.

### Contexto
> Use antes de desenhar quando o contexto do usuário ou a abordagem de mercado ainda não estiver clara.

| Agente | O que faz |
|--------|-----------|
| `project-framing` | Transforma um brief ou PRD em um problem statement estruturado. Inclui fases opcionais de síntese de pesquisa e benchmark competitivo quando o contexto ainda não estiver claro. |

### Design Core
> O coração do processo — define, mapeia, critica.

| Agente | O que faz |
|--------|-----------|
| `project-framing` | ↑ também é a entrada do design core |
| `journey-builder` | Mapeia fluxos, estados, edge cases e dependências a partir do problem frame. |
| `solution-critique` | Avalia o design em uma passagem: heurísticas de usabilidade, acessibilidade WCAG, completude de estados, clareza de copy e consistência com o DS. Relatório consolidado. |

### Entrega
> Último passo antes de passar para o dev.

| Agente | O que faz |
|--------|-----------|
| `delivery-handoff` | Gera a spec de eventos de analytics e valida se o design está completamente documentado para o dev — sem ambiguidade, sem estados faltando. |

---

## Skills

Unidades de conhecimento modulares carregadas pelos agentes. Podem ser usadas diretamente em uma conversa.

| Skill | Carregada por |
|-------|--------------|
| `gut-check` | todos os agentes ← sabatina de 5 perguntas críticas, sugerida após o intake |
| `problem-definition` | project-framing |
| `flow-structuring` | journey-builder, delivery-handoff |
| `state-mapping` | journey-builder, solution-critique, delivery-handoff |
| `edge-case-detection` | journey-builder, solution-critique, delivery-handoff |
| `heuristic-evaluation` | solution-critique |
| `copy-review` | solution-critique |
| `component-validation` | solution-critique, delivery-handoff |
| `event-modeling` | delivery-handoff |

### Gut-Check

Após o intake de qualquer agente, o toolkit sugere passar pelo gut-check antes de avançar. São 5 perguntas de alto risco selecionadas para o contexto específico — perspectivas de Produto, Negócio, Design e Persona (quando definida no contexto local). A skill oferece uma resposta sugerida para cada pergunta e, ao final, pergunta se a pessoa quer aprofundar — onde a perspectiva de Engenharia entra. Se o gut-check for pulado, o agente lembra ao final caso identifique premissas frágeis no output.

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

## Por onde começar

1. Execute o `playbooks/setup-local-context.md` para preencher o contexto do seu squad
2. Verifique se os arquivos de `context/global/` estão atualizados
3. Leia `docs/como-usar.md`
4. Comece com `agents/project-framing.md`

## Contribuindo

Veja `docs/como-contribuir.md`.
