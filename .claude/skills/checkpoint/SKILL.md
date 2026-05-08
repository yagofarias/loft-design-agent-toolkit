---
name: checkpoint
description: >
  Saves a checkpoint of the current session: what was produced, decisions made,
  and a compact context block to paste at the start of the next conversation.
  Use after 2+ agents in one session to preserve context efficiently.
  💡 Recommended model: Haiku 4.5 (lightweight, structural).
disable-model-invocation: true
allowed-tools: Read, Write
---

Gere um checkpoint da sessão atual seguindo o protocolo abaixo.

## Protocolo

### Passo 1 — Inventário da sessão

Com base na sessão atual, identifique:

- **Projeto:** nome e pasta em `projects/`
- **Agentes rodados:** quais comandos foram usados e em que ordem
- **Arquivos gerados:** lista dos arquivos criados/atualizados com seus paths
- **Decisões tomadas:** o que foi decidido que vai além do que está nos arquivos (direções descartadas, trade-offs escolhidos, premissas assumidas)
- **O que ficou em aberto:** perguntas não respondidas, `[A VALIDAR]` críticos, próximos passos concretos

---

### Passo 2 — Bloco de contexto compacto

Gere um bloco compacto para ser colado no início da próxima conversa, permitindo começar com contexto limpo sem precisar explicar tudo de novo:

```
## Contexto da sessão anterior — [projeto] — [data]

**Onde paramos:** [1-2 frases do estado atual do projeto]

**Arquivos gerados:**
- `projects/[projeto]/design-doc.md` — [status: rascunho/aprovado]
- `projects/[projeto]/journey-spec.md` — [status, se existir]

**Decisões chave:**
- [Decisão 1 — resumida em 1 linha]
- [Decisão 2]

**Próximo passo:**
[O que deve acontecer na próxima sessão]
```

---

### Passo 3 — Salvar o arquivo

Salve em `projects/[nome-do-projeto]/checkpoint-[data].md` com o inventário completo + o bloco de contexto compacto.

Após salvar, informe o path e mostre o bloco de contexto compacto destacado — é o que o designer vai copiar.

---

### Quando sugerir

O CLAUDE.md sugere o `/checkpoint` ao final de sessões que encadearam 2+ agentes. Se você perceber que a sessão está ficando longa antes disso, pode sugerir proativamente:

> "Essa sessão está ficando densa. Quer fazer um `/checkpoint` agora para preservar o contexto antes de continuar?"

$ARGUMENTS
