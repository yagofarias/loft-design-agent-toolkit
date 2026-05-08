---
name: retro
description: >
  Runs a session retrospective after using any agent. Generates a diagnosis
  of what worked well and what could improve, collects the designer's input,
  and saves a retro-[agent]-[date].md file to the project folder.
  💡 Recommended model: Haiku 4.5 (lightweight).
disable-model-invocation: true
allowed-tools: Read, Write
---

Rode uma retrospectiva da sessão atual seguindo o protocolo abaixo.

## Protocolo

### Passo 1 — Diagnóstico do modelo

Com base na sessão atual, gere uma avaliação honesta em três partes:

**O que funcionou bem**
- O que o toolkit entregou de valor real nesta sessão?
- Quais perguntas ou frameworks ajudaram o designer a chegar em clareza?
- O que o agente fez que você não esperava que fosse útil?

**O que poderia ter sido melhor**
- Onde a conversa ficou repetitiva, genérica ou perdeu foco?
- Alguma pergunta que deveria ter sido feita e não foi?
- O output gerado ficou muito longo, muito vago, ou com algo faltando?

**Insights sobre o projeto que surgiram**
- O que ficou mais claro sobre o problema ou a solução depois desta sessão?
- Alguma premissa foi questionada ou confirmada?
- O que a próxima sessão deveria começar resolvendo?

Apresente o diagnóstico de forma direta — 3 a 5 bullets por parte, sem enrolar.

---

### Passo 2 — Input do designer

Após apresentar o diagnóstico, pergunte:

> "Você concorda com esta avaliação? Tem algo que eu errei, deixei de perceber, ou que você vivenciou de forma diferente?"

Aguarde a resposta antes de continuar.

---

### Passo 3 — Gerar o arquivo

Combine o diagnóstico do modelo com o input do designer e salve em `projects/[nome-do-projeto]/retro-[agente]-[data].md`.

Estrutura do arquivo:

```markdown
# Retrospectiva — [/agente] — [DD/MM/AAAA]

**Projeto:** [nome]
**Agente:** [nome do agente usado]
**Designer:** [nome, se disponível]

---

## O que funcionou bem
[bullets]

## O que poderia ter sido melhor
[bullets]

## Insights sobre o projeto
[bullets]

## Perspectiva do designer
[resposta do designer — verbatim ou resumida com fidelidade]

## Próximos passos sugeridos
[o que fazer na próxima sessão com base nesta]
```

Após salvar, informe o path do arquivo e sugira o próximo passo do projeto.

$ARGUMENTS
