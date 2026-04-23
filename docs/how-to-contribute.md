# How to Contribute — Loft Design Agent Toolkit

Este guia é para quem quer melhorar o toolkit: corrigir algo que não está funcionando, propor um agente novo, ou refinar uma skill existente com aprendizados reais de uso.

Contribuir aqui é análogo a contribuir com um design system: você está melhorando uma ferramenta compartilhada que afeta como todo o time trabalha. As mesmas boas práticas se aplicam.

---

## Princípios de contribuição

**Contribuições devem vir da prática.**
A melhor fonte para melhorar um agente é tê-lo usado em um projeto real e identificado onde ele falhou ou onde poderia ser mais útil. Contribuições teóricas são bem-vindas mas priorizamos o que foi testado.

**Cada mudança deve ter uma razão clara.**
Não refatore por preferência estética. Se algo está mudando, deve haver uma evidência de que o estado atual causa problemas ou que o novo estado é melhor.

**Menos é mais.**
Agentes e skills que fazem menos coisas com mais precisão são melhores do que os que tentam cobrir tudo. Se uma contribuição está expandindo muito o escopo de um agente, considere criar um agente novo.

**O contexto é mais valioso do que o prompt.**
Antes de reescrever um agente, verifique se os arquivos de `/context` estão bem preenchidos. Muitos problemas de qualidade de output são de contexto, não de instrução.

---

## O que você pode contribuir

### Tipos de contribuição aceitos

| Tipo | Exemplos |
|------|---------|
| **Bug fix** | Instrução ambígua em um agente, seção faltando em template, gate de checklist incompleto |
| **Melhoria** | Refinar uma heurística na skill de critique, adicionar edge cases ao checklist, melhorar uma seção de template |
| **Novo agente** | Agente para um caso de uso não coberto (veja seção abaixo) |
| **Nova skill** | Conhecimento modular que pode ser reutilizado por múltiplos agentes |
| **Novo playbook** | Sequência de trabalho para um tipo de projeto não coberto |
| **Contexto** | Melhorias nos arquivos de `/context` que melhoram os outputs para o Loft |
| **Documentação** | Melhorias neste arquivo ou no `how-to-use.md` |

### O que não aceitar como contribuição

- Duplicação de skills que já existem com nomes diferentes
- Agentes que fazem a mesma coisa que um existente com pequenas variações
- Mudanças de formatação sem mudança de conteúdo
- Adição de seções "por precaução" sem caso de uso concreto

---

## Processo de contribuição

### Para mudanças pequenas (bug fix, melhoria pontual)

1. **Faça a mudança** no arquivo relevante
2. **Abra uma PR** com título descritivo: `fix: [arquivo] — [o que foi corrigido]`
3. **No corpo da PR**, explique em 2-3 frases: o que estava errado, o que mudou, e se foi testado em algum projeto real

Exemplo de título:
```
fix: agents/solution-critique — adicionada verificação de estados mobile
improve: skills/copy-review — novos critérios para textos financeiros
```

### Para contribuições maiores (novo agente, nova skill, novo playbook)

Antes de escrever qualquer coisa, abra uma **issue de proposta** com:

1. **O problema que está sendo resolvido** — Qual situação do dia a dia de design este agente/skill endereça?
2. **Por que não existe já** — Como é diferente do que já está no toolkit?
3. **O que ele vai produzir** — Qual é o output esperado?
4. **Dependências** — Carrega quais skills? Usa quais arquivos de contexto?

Aguarde feedback antes de implementar. Isso evita trabalho refeito e garante que a contribuição faz sentido na arquitetura geral.

---

## Como escrever um novo agente

Todo agente bem escrito tem:

### Frontmatter obrigatório

```yaml
---
name: nome-do-agente
description: >
  Uma ou duas frases descrevendo quando este agente deve ser usado.
  Seja específico: o Claude usa isso para decidir quando carregar o agente.
---
```

### Seções obrigatórias

```markdown
# Agent: [Nome Legível]

[Parágrafo descrevendo o papel e a perspectiva do agente]

## Quando usar este agente
[Lista de situações concretas — não princípios abstratos]

## Habilidades que este agente carrega
[Lista de skills de /skills/ com justificativa]
[Lista de arquivos de /context/ necessários]

## Protocolo de execução

### Fase 1 — Intake
[O que pedir ao designer antes de começar]

### Fase 2 — [Nome da fase]
[O que fazer]

### Fase N — Output
[O que produzir, referenciando o template correspondente]

### Fase N+1 — Validação
[Checklist de auto-revisão antes de entregar]

## Comportamento esperado
[Regras de comportamento — o que o agente deve e não deve fazer]
```

### Checklist antes de abrir PR para um novo agente

- [ ] O agente tem um output claro referenciado em `/templates`?
- [ ] As skills carregadas são todas necessárias (nenhuma redundante)?
- [ ] A fase de validação tem pelo menos 3 critérios verificáveis?
- [ ] O "Quando usar" está específico o suficiente para excluir situações onde não deve ser usado?
- [ ] O "Comportamento esperado" define limitações, não só capacidades?
- [ ] O agente foi testado em pelo menos um projeto real antes da PR?

---

## Como escrever uma nova skill

Skills são unidades de conhecimento. Elas devem ser:

- **Atômicas** — Uma skill, um domínio de conhecimento
- **Reutilizáveis** — Pensadas para ser carregadas por múltiplos agentes
- **Prescritivas** — Não apenas teoria, mas frameworks e checklists acionáveis

### Frontmatter obrigatório

```yaml
---
name: nome-da-skill
description: >
  Uma frase descrevendo o conhecimento que esta skill provê.
  Inclua quando ela deve ser carregada automaticamente.
---
```

### Estrutura recomendada

```markdown
# Skill: [Nome]

## Propósito
[Por que esta skill existe e que problema de design ela resolve]

## [Framework / Princípios / Checklist principal]
[O conteúdo real da skill — seja prescritivo]

## [Seção complementar]
[Exemplos, casos especiais, anti-patterns]
```

### Critério de qualidade para skills

Uma skill de qualidade deve responder: *"Se eu der esta skill para um designer júnior, ele consegue aplicar sem me perguntar nada?"*

Se a resposta for não, a skill precisa de mais exemplos ou de critérios mais claros.

---

## Como escrever um novo playbook

Playbooks são sequências de trabalho. Eles devem responder: *"Dado que meu projeto é X, qual é a ordem certa de agentes e o que verificar entre cada um?"*

### Estrutura obrigatória

```markdown
# Playbook: [Nome]

Use quando: [Critério claro de quando este playbook se aplica]
Não use quando: [Critério claro de quando NÃO usar]

## Fluxo

[Diagrama em texto mostrando a sequência]

## Fase 1 — [Nome]

**Agente:** `agents/nome.md`
**Input necessário:** [Lista]
**Output esperado:** [Template]

### Gate — Checklist de aprovação
[Lista de verificações antes de avançar]
[O que fazer se um item falhar]

## Fase N — ...
```

---

## Como atualizar os arquivos de contexto

Os arquivos de `/context` são os mais importantes para a qualidade dos outputs. Devem ser atualizados quando:

- O design system evolui (novos componentes, tokens deprecados)
- As personas são revisadas ou novas são criadas
- O guia de voz é atualizado
- Novos segmentos de público são incorporados

### Processo de atualização de contexto

1. **Faça a mudança** no arquivo de contexto
2. **Teste** com um agente que depende desse contexto para verificar se o output melhorou
3. **Abra uma PR** com o título: `context: [arquivo] — [o que mudou]`
4. **No corpo**, descreva o que mudou e por que (ex: "Novo token de spacing adicionado no DS Sprint 42")

---

## Convenções de nomenclatura

### Arquivos

- Agentes: `kebab-case.md` (ex: `project-framing.md`)
- Skills: `kebab-case.md` (ex: `heuristic-evaluation.md`)
- Playbooks: `kebab-case.md` (ex: `start-from-scratch.md`)
- Templates: `kebab-case.md` (ex: `problem-frame.md`)

### Commits

Use prefixos convencionais:

```
feat: novo agente de X
improve: refinamento de skill Y
fix: correção em template Z
context: atualização de personas
docs: melhoria no how-to-use
refactor: reorganização de seção em agente W
```

### PRs

Títulos no formato: `[tipo]: [arquivo(s)] — [descrição breve`]

---

## Revisão de PRs

Toda PR de conteúdo novo (agente, skill, playbook) precisa de:

1. **Revisão de um designer** que use o toolkit ativamente — para validar se faz sentido no fluxo real de trabalho
2. **Aprovação do mantenedor do toolkit** — para garantir coerência arquitetural

PRs de bug fix e melhorias pequenas precisam de apenas uma aprovação.

### O que verificar ao revisar uma PR

- O conteúdo foi testado em projeto real? (se não, pedir evidência ou indicar como testar)
- A mudança não quebra compatibilidade com agentes existentes que dependem da skill/template?
- O frontmatter está correto e completo?
- As referências a outros arquivos do toolkit estão corretas?
- A contribuição segue os princípios declarados no início deste documento?

---

## Mantendo o toolkit saudável

### Sinais de que um agente precisa de revisão

- Outputs consistentemente genéricos mesmo com contexto bem preenchido
- O agente está sendo bypassed sistematicamente pelo time
- A fase de validação raramente encontra problemas (pode estar muito superficial)
- Designers estão adaptando muito o output antes de usar (pode ser que o template esteja errado)

### Deprecando agentes ou skills

Antes de remover qualquer arquivo:

1. Marque como `[DEPRECATED]` no frontmatter por pelo menos 30 dias
2. Adicione uma nota indicando o substituto recomendado
3. Só então remova em uma PR separada com justificativa

---

## Reconhecimento

Contribuições são atribuídas no `CHANGELOG.md` por nome e o que foi contribuído. Se você usou o toolkit em um projeto e quer compartilhar como funcionou (ou não funcionou), abra uma issue com a label `case-study` — esses relatos são extremamente úteis para evoluir o toolkit.
