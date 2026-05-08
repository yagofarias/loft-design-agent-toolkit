# Como Contribuir — Loft Design Agent Toolkit

Este guia é para quem quer melhorar o toolkit: corrigir algo que não está funcionando, propor um agente novo, ou refinar uma skill existente com aprendizados reais de uso.

---

## Princípios de contribuição

**Contribuições devem vir da prática.**
A melhor fonte para melhorar um agente é tê-lo usado em um projeto real e identificado onde ele falhou. Contribuições teóricas são bem-vindas mas priorizamos o que foi testado.

**Cada mudança deve ter uma razão clara.**
Não refatore por preferência estética. Se algo está mudando, deve haver evidência de que o estado atual causa problemas.

**Menos é mais.**
Agentes que fazem menos coisas com mais precisão são melhores do que os que tentam cobrir tudo.

**O contexto é mais valioso do que o prompt.**
Antes de reescrever um agente, verifique se os arquivos de `/context` estão bem preenchidos. Muitos problemas de qualidade de output são de contexto, não de instrução.

---

## O que você pode contribuir

| Tipo | Exemplos |
|------|---------|
| **Bug fix** | Instrução ambígua em um agente, seção faltando em template, gate incompleto |
| **Melhoria** | Refinar uma heurística, adicionar edge cases ao checklist |
| **Novo agente** | Agente para um caso de uso não coberto |
| **Nova skill** | Conhecimento modular reutilizável por múltiplos agentes |
| **Novo playbook** | Sequência para um tipo de projeto não coberto |
| **Contexto global** | Melhorias nos arquivos de `/context/global` |
| **Documentação** | Melhorias neste arquivo ou no `como-usar.md` |

> **Contexto de squad** (`/context/local`) não é contribuído para o repositório central — cada squad mantém o seu localmente.

---

## Processo de contribuição

### Para mudanças pequenas (bug fix, melhoria pontual)

1. Faça a mudança no arquivo relevante
2. Abra uma PR com título: `fix: [arquivo] — [o que foi corrigido]`
3. No corpo, explique em 2-3 frases: o que estava errado, o que mudou, se foi testado

### Para contribuições maiores (novo agente, nova skill, novo playbook)

Abra uma **issue de proposta** com:

1. **O problema que está sendo resolvido** — Qual situação do dia a dia de design este agente endereça?
2. **Por que não existe já** — Como é diferente do que já está no toolkit?
3. **O que ele vai produzir** — Qual é o output esperado?
4. **Dependências** — Carrega quais skills? Usa quais arquivos de contexto?

Aguarde feedback antes de implementar.

---

## Como escrever um novo agente

### Frontmatter obrigatório

```yaml
---
name: nome-do-agente
description: >
  Uma ou duas frases descrevendo quando este agente deve ser usado.
---
```

### Seções obrigatórias

```markdown
# Agent: [Nome]

[Parágrafo descrevendo o papel e a perspectiva do agente]

## Quando usar este agente
[Lista de situações concretas]

## Habilidades que este agente carrega
[Skills de /skills/ com justificativa]
[Arquivos de /context/ necessários — globais e/ou de squad]

## Protocolo de execução

### Fase 1 — Intake
### Fase 2 — [Nome]
### Fase N — Output
### Fase N+1 — Validação

## Comportamento esperado
[O que o agente deve e não deve fazer]
```

### Checklist antes de abrir PR

- [ ] O agente tem um output claro referenciado em `/templates`?
- [ ] As skills carregadas são todas necessárias?
- [ ] A fase de validação tem pelo menos 3 critérios verificáveis?
- [ ] O "Quando usar" é específico o suficiente para excluir quando não usar?
- [ ] O agente foi testado em pelo menos um projeto real?

---

## Como escrever uma nova skill

Skills são unidades de conhecimento. Devem ser atômicas, reutilizáveis e prescritivas.

### Frontmatter obrigatório

```yaml
---
name: nome-da-skill
description: >
  Uma frase descrevendo o conhecimento que esta skill provê.
---
```

### Critério de qualidade

Uma skill de qualidade responde: *"Se eu der esta skill para um designer júnior, ele consegue aplicar sem me perguntar nada?"*

---

## Atualizando os arquivos de contexto global

Os arquivos de `/context/global` são os mais críticos para qualidade dos outputs. Devem ser atualizados quando:

- O Copan evolui (novos componentes, tokens deprecados)
- Os princípios de produto mudam
- O guia de voz da marca é revisado

### Processo

1. Faça a mudança no arquivo de contexto
2. Teste com um agente que depende desse contexto
3. Abra uma PR: `context: [arquivo] — [o que mudou]`
4. No corpo, descreva o que mudou e por que

> **Contexto de squad não vai para o repositório central.** Cada squad mantém `/context/local` localmente — não abra PRs com conteúdo específico de squad.

---

## Convenções de nomenclatura

### Arquivos
- Todos: `kebab-case.md`

### Commits

Todo commit deve ter uma mensagem clara que responda: **o que mudou e por quê**. Não "atualiza arquivo X" — mas o que foi adicionado, corrigido ou removido e qual o impacto.

**Formato:**
```
[tipo]: [descrição do que mudou — específico]
```

**Tipos:**
```
feat:     novo agente, skill, template ou funcionalidade
improve:  refinamento de conteúdo existente (ex: novos exemplos, seção ampliada)
fix:      correção de erro, inconsistência ou referência quebrada
refactor: renomear, reorganizar ou mover sem mudar comportamento
context:  atualização de arquivos de contexto global
docs:     melhorias em documentação (README, como-usar, como-contribuir)
```

**Exemplos bem escritos:**
```
feat: add solution-craft agent with direction cards and tangibilization
improve: edge-cases — add Loft-specific checklists for financial flows and B2B
fix: update all references from journey-builder to solution-craft
refactor: rename ui-states to state-coverage across all files
context: update brand-voice with fintech trust signals and B2B calibration
docs: expand commit convention in como-contribuir
```

**Exemplos mal escritos (evitar):**
```
update files
fix stuff
changes
WIP
melhoria
```

Se a mudança é grande, adicione um corpo ao commit:
```
feat: add solution-craft with ideation phase

- Phase 0 generates 2-3 direction cards anchored in market references
- Phase 5 generates tangibilization artifacts (Mermaid, text wireframe, storyboard)
- Replaces journey-builder across all agents, skills and README
```

### PRs
`[tipo]: [arquivo(s)] — [descrição breve]`

---

## Revisão de PRs

- PRs de conteúdo novo precisam de revisão de um designer ativo + aprovação do mantenedor
- PRs de bug fix e melhorias pequenas precisam de uma aprovação

### O que verificar ao revisar

- O conteúdo foi testado em projeto real?
- A mudança não quebra compatibilidade com agentes que dependem da skill/template?
- As referências a context seguem a estrutura `global/` e `squad/`?
- A contribuição segue os princípios declarados aqui?

---

## Sinais de que um agente precisa de revisão

- Outputs consistentemente genéricos mesmo com contexto bem preenchido
- O agente está sendo bypassed sistematicamente pelo time
- Designers estão adaptando muito o output antes de usar

---

## Reconhecimento

Contribuições são atribuídas no `CHANGELOG.md`. Se você usou o toolkit em um projeto e quer compartilhar como funcionou, abra uma issue com a label `case-study`.
