# Contexto do Squad

> Esta pasta é o coração do que torna o toolkit específico para o seu contexto local.
> Preencha os arquivos aqui antes de usar qualquer agente.
> Quanto mais rico o contexto, mais úteis e precisos serão os outputs.

---

## O que vai em cada arquivo

| Arquivo | O que colocar | Obrigatório? |
|---------|---------------|-------------|
| `context.md` | Regras de negócio, terminologia do domínio, constraints regulatórios, métricas do squad, decisões de design já tomadas | ✅ Sempre |
| `personas.md` | Personas específicas deste segmento com contexto de uso | Se o squad tiver personas próprias |
| `target-audiences.md` | Segmentações de público (B2B/B2C, tamanho de empresa, perfil) com particularidades de comunicação | Se a comunicação variar por segmento |
| `brand-voice-local.md` | Tom específico para este domínio que complementa (não substitui) o brand voice global | Se o squad tiver tom próprio |

---

## Como usar com os agentes

Ao chamar qualquer agente, referencie os arquivos globais + os arquivos do squad que forem relevantes:

```
context/global/product-principles.md   ← sempre
context/global/design-system.md        ← sempre
context/global/brand-voice.md          ← sempre
context/local/context.md               ← sempre (quando preenchido)
context/local/personas.md              ← quando relevante para o projeto
context/local/target-audiences.md      ← quando o projeto tiver comunicação segmentada
context/local/brand-voice-local.md     ← quando houver tom específico do squad
```

---

## Quando atualizar

- Sempre que uma regra de negócio mudar
- Quando uma persona for revisada
- Após projetos importantes que geraram aprendizados sobre o usuário
- Quando o squad acordar uma nova terminologia ou convenção
