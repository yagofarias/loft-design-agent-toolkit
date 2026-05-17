---
name: research-archive
description: >
  Consulta o acervo de pesquisas do squad antes de planejar um novo estudo.
  Evita pesquisa redundante e ancora novas perguntas nas lacunas reais do
  conhecimento existente. Fonte: context/local/research-archive.md (resumo
  do Dovetail/NotebookLM) + projects/ (estudos anteriores).
---

# Skill: Research Archive

## Propósito

Antes de planejar qualquer pesquisa, verificar o que o squad já sabe. Pesquisa redundante é o erro mais comum e mais caro em ResearchOps — esta skill garante que cada novo estudo parte das lacunas reais, não do zero.

---

## Protocolo de consulta

### Passo 1 — Verificar o acervo centralizado

Leia `context/local/research-archive.md`.

Se o arquivo existir e tiver conteúdo: extraia os estudos relevantes ao tema da pesquisa atual.

Se o arquivo não existir ou estiver vazio: sinalize ao designer:
> "Seu squad ainda não tem um acervo de pesquisa documentado. Você tem estudos anteriores no Dovetail ou NotebookLM? Posso ajudar a criar um resumo para que os próximos planejamentos já partam do que existe."

### Passo 2 — Buscar em projects/

Busque em `projects/*/research-plan.md` por planos de pesquisa anteriores com temas, personas ou perguntas similares ao estudo atual.

Para cada estudo relevante encontrado, extraia:
- Objetivo do estudo
- Principais achados (seção Achados)
- O que ficou em aberto

### Passo 3 — Síntese do conhecimento existente

Apresente ao designer um resumo em dois blocos:

**O que já sabemos sobre [tema]:**
- [Achado de estudo anterior + fonte]
- [Segundo achado]

**O que ainda está em aberto (lacunas):**
- [Pergunta não respondida ou hipótese não testada]
- [Segunda lacuna]

**Perguntas que não precisam ser pesquisadas novamente:**
- [Pergunta já respondida com confiança]

---

## research-archive.md — estrutura esperada

O arquivo `context/local/research-archive.md` deve ser mantido pelo squad com resumos dos estudos publicados no Dovetail. Estrutura:

```markdown
# Acervo de Pesquisa — [Nome do Squad]

> Resumo dos estudos publicados no Dovetail.
> Atualizar após cada pesquisa concluída.
> Para detalhes completos, acessar o Dovetail: [link]

---

## [Título do Estudo] — [Mês/Ano]

**Método:** [Entrevistas / Teste de usabilidade / Survey]  
**Personas:** [Quem participou]  
**Objetivo:** [O que queríamos descobrir]  

**Principais achados:**
- [Achado 1]
- [Achado 2]

**O que ficou em aberto:**
- [Pergunta não respondida]

**Link Dovetail:** [URL]
```

---

## Quando sugerir atualização do acervo

Ao final de qualquer pesquisa concluída (`/research-plan` Fase 8), oferecer:
> "Quer que eu gere o resumo desta pesquisa para adicionar ao acervo? Leva 2 minutos e garante que o próximo estudo já parte daqui."
