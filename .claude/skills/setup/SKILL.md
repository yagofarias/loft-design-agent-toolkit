---
name: setup
description: >
  Guides the designer through filling the squad's local context files.
  Run this once when starting with the toolkit in a new squad. The local
  context is what makes all other agents specific to your domain.
disable-model-invocation: true
allowed-tools: Read, Write, Bash
---

Start a local context setup session by reading and following the protocol in `playbooks/setup-local-context.md`.

Before starting, read:
- `playbooks/setup-local-context.md`
- `context/local/README.md`

Then check which files in `context/local/` already have content and which still have placeholder text (`[A PREENCHER]`). Start from where the designer left off — don't repeat what's already filled.

Guide the designer through the setup phases one at a time:
1. Squad context (`context.md`)
2. Personas (`personas.md`)
3. Target audiences (`target-audiences.md`)
4. Local brand voice (`brand-voice-local.md`)
5. Competitors (`competitors.md`)
6. Integrations (Confluence + documentation tool)

After each file is filled, confirm with the designer before moving to the next.

## Fase 6 — Integrações

Após as 5 fases de contexto, pergunte:

> "O seu squad usa Confluence para centralizar documentação de projetos?"

**Se sim:**

1. Pergunte: "Qual é a URL do seu Confluence? (ex: https://loft.atlassian.net)"
2. Pergunte: "Em qual espaço do Confluence você quer publicar os design docs? Cole o link de uma página ou o nome do espaço."
3. Pergunte (opcional): "Existe uma página-pai onde os design docs devem ficar agrupados? Se sim, cole o link dela."

Salve as respostas em `context/local/context.md` na seção de integrações:
```
## Integrações

confluence_url: [URL base do Confluence]
confluence_space_key: [Chave do espaço — ex: DES, DESIGN]
confluence_parent_page_id: [ID ou URL da página-pai, se houver]
confluence_doc_tool: confluence
```

**Se não usa Confluence:**

Pergunte: "O squad usa Google Drive para documentação? Se sim, qual pasta?" Salve se houver.

```
confluence_doc_tool: google_drive
google_drive_folder_url: [URL da pasta, se houver]
```

**Sobre o MCP da Atlassian:**

Para a publicação funcionar, o MCP da Atlassian (Rovo) precisa estar conectado no Claude Code. Informe:

> "Para publicar automaticamente no Confluence, você precisa conectar o MCP da Atlassian uma vez. Quando quiser fazer isso, diga 'me ajude a conectar o Confluence' que eu te guio."

## Ao finalizar o setup

Depois que todos os arquivos forem preenchidos, execute este comando para proteger o contexto local de atualizações futuras do toolkit via `git pull`:

```bash
git update-index --skip-worktree context/local/context.md context/local/personas.md context/local/target-audiences.md context/local/brand-voice-local.md context/local/competitors.md 2>/dev/null || true
```

Informe o designer:
> "Seu contexto local está protegido. Se você atualizar o toolkit no futuro, basta dizer 'me ajude a atualizar o toolkit' que eu cuido disso sem apagar seus dados."

Mostre um resumo do que foi preenchido e quais agentes estão prontos para usar.

$ARGUMENTS
