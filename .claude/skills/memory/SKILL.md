---
name: memory
description: >
  Salva o estado da sessão atual: o que foi produzido, decisões tomadas,
  e um bloco de contexto compacto para colar no início da próxima conversa.
  Usar após 2+ agentes em uma sessão para preservar contexto de forma eficiente.
  💡 Recommended model: Haiku 4.5 (lightweight, structural).
disable-model-invocation: true
allowed-tools: Read, Write
---

Gere um memory da sessão atual seguindo o protocolo abaixo.

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

Salve em `projects/[nome-do-projeto]/memory-[data].md` com o inventário completo + o bloco de contexto compacto.

Após salvar, informe o path e mostre o bloco de contexto compacto destacado — é o que o designer vai copiar.

---

### Quando sugerir

O CLAUDE.md sugere o `/memory` ao final de sessões que encadearam 2+ agentes. Se você perceber que a sessão está ficando longa antes disso, pode sugerir proativamente:

> "Essa sessão está ficando densa. Quer fazer um `/memory` agora para preservar o contexto antes de continuar?"

$ARGUMENTS
