---
name: setup
description: >
  Guides the designer through filling the squad's local context files.
  Offers web research and corporate document analysis to build a first
  draft quickly. Run once per squad, or when context needs a major update.
disable-model-invocation: true
allowed-tools: Read, Write, Bash, WebSearch, WebFetch
---

Inicie o setup do contexto local do squad seguindo o protocolo abaixo.

## Fase 0 — Como você quer construir o contexto?

Antes de fazer qualquer pergunta, apresente as opções:

> "Posso te ajudar a construir o contexto do squad de três formas — você escolhe o que fizer mais sentido agora:
>
> **1. Pesquisa web** — busco informações públicas sobre o produto, domínio de mercado e concorrentes do seu squad para montar um rascunho
> **2. Documentos corporativos** — se você compartilhar links ou conectar Drive/Confluence/Slack, analiso o que existir e uso como base
> **3. Do zero** — respondemos juntos, campo por campo
>
> Você pode combinar qualquer uma. Com qual quer começar?"

**Regra fundamental:** todo conhecimento coletado — seja da web ou de documentos — é tratado como **hipótese a validar**, não como fato. Mesmo documentos internos podem estar desatualizados.

Ao apresentar algo coletado, use sempre a forma:
- ✅ *"Encontrei que X parece ser verdade com base em [fonte]. Isso ainda se aplica?"*
- ✅ *"Este documento é de [data] — pode estar desatualizado. O que ainda está correto?"*
- ❌ ~~"X é verdade."~~

---

## Fase 1 — Coleta (se escolheu pesquisa ou documentos)

**Se pesquisa web:**

Use WebSearch para buscar:
- Nome do produto + "Loft" + domínio (ex: "Loft financiamento imobiliário simulador")
- Concorrentes do domínio
- Contexto de mercado relevante

Monte um rascunho dos arquivos com base no que encontrar.

**Se documentos corporativos:**

Pergunte: "Quais documentos você tem? Cole os links ou descreva onde estão (Confluence, Drive, Slack)."

Se MCPs estiverem conectados (Confluence, Drive), acesse diretamente.
Se não estiverem, peça que o designer cole o conteúdo relevante no chat.

Analise e extraia informações relevantes para cada arquivo de contexto.

---

## Fase 2 — Validação do rascunho

Apresente o rascunho completo dos arquivos de contexto de uma vez:

> "Com base no que coletei, aqui está um rascunho do seu contexto local. Revise cada seção e me diga:
> - O que está correto ✅
> - O que está errado ou desatualizado ❌
> - O que está faltando e precisa ser adicionado +"

O designer edita e completa apenas o que está em branco ou errado — muito mais rápido do que partir do zero.

---

## Fase 3 — Preenchimento das lacunas

Para o que não foi possível coletar automaticamente, percorra os arquivos um por um fazendo apenas as perguntas necessárias:

1. Squad context (`context.md`) — regras de negócio, terminologia, constraints
2. Personas (`personas.md`)
3. Target audiences (`target-audiences.md`)
4. Local brand voice (`brand-voice-local.md`)
5. Competitors (`competitors.md`)

Confirme com o designer antes de passar para o próximo arquivo.

---

## Fase 4 — Integrações

Após os arquivos de contexto, pergunte:

> "O seu squad usa Confluence para centralizar documentação de projetos?"

**Se sim:** colete URL do Confluence, chave do espaço e página-pai opcional. Salve em `context.md`:
```
confluence_url: [URL]
confluence_space_key: [chave]
confluence_parent_page_id: [ID ou URL, se houver]
confluence_doc_tool: confluence
```

**Se não:** pergunte sobre Google Drive e salve se houver:
```
confluence_doc_tool: google_drive
google_drive_folder_url: [URL, se houver]
```

Informe: "Para publicar automaticamente no Confluence, você precisará conectar o MCP da Atlassian. Me diga quando quiser fazer isso."

---

## Ao finalizar

Execute para proteger os arquivos de atualizações do toolkit:

```bash
git update-index --skip-worktree context/local/context.md context/local/personas.md context/local/target-audiences.md context/local/brand-voice-local.md context/local/competitors.md 2>/dev/null || true
```

Informe:
> "Seu contexto local está protegido. Para atualizar o toolkit no futuro, diga 'me ajude a atualizar o toolkit'."

Mostre um resumo do que foi preenchido. Sugira começar com `/framing` para o primeiro projeto.

> "Lembre: o contexto local é uma enciclopédia viva — quanto mais você alimenta conforme o produto evolui, mais os agentes acertam no contexto do seu squad."

$ARGUMENTS
