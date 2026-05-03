---
version: "1.0"
agent: journey-builder
status: "[RASCUNHO | EM REVISÃO | APROVADO]"
---

# Journey Spec

**Projeto:** [Nome]
**Jornada:** [Nome — ex: "Checkout com Pix"]
**Designer:** [Nome]
**Data:** [DD/MM/AAAA]
**Figma:** [Link]

---

## Sumário

- **Usuário primário:** [Persona]
- **Ponto de entrada:** [De onde o usuário chega]
- **Ponto de saída:** [O que define conclusão]
- **Número de telas:** [N telas / estados]
- **Plataformas:** [Web / iOS / Android]
- **Problem Frame:** [Link para templates/design-doc.md]

---

## Pré-condições

- [Condição 1 — ex: "usuário autenticado"]
- [Condição 2 — ex: "ao menos 1 item no carrinho"]

---

## Fluxo Principal (Happy Path)

```
ENTRADA: [Como o usuário chega aqui]

PASSO 1: [Nome descritivo]
  O usuário vê: [Conteúdo principal]
  Ação disponível: [O que pode fazer]
  Gatilho de avanço: [O que faz seguir]

  → Vai para: PASSO 2

PASSO 2: [Nome]
  ...
  → SE [condição A]: PASSO 3A
  → SE [condição B]: PASSO 3B

SAÍDA: [Estado final]
```

---

## Inventário de Telas e Estados

| Tela | Estado | Gatilho | Prioridade |
|------|--------|---------|-----------|
| [Nome] | Default | — | P0 |
| [Nome] | Loading | Aguardando API | P0 |
| [Nome] | Erro | API retorna erro | P0 |
| [Nome] | Vazio | Nenhum dado | P1 |

---

## Mapeamento de Estados por Componente

### [Nome do componente/tela crítica]

| Estado | Gatilho | Comportamento | Componentes afetados |
|--------|---------|---------------|----------------------|
| Default | — | [Descrição] | [Lista] |
| Loading | [Trigger] | [Descrição] | [Lista] |
| Sucesso | [Trigger] | [Descrição] | [Lista] |
| Erro | [Trigger] | [Descrição] | [Lista] |

---

## Edge Cases

| # | Situação | Probabilidade | Impacto | Tratamento proposto | Prioridade |
|---|----------|--------------|---------|---------------------|-----------|
| 1 | [Descrição] | Alta/Média/Baixa | Crítico/Importante/Baixo | [Como responder] | P0/P1/P2 |

---

## Dependências

| Dependência | Tipo | Responsável | Status |
|-------------|------|-------------|--------|
| [API, permissão] | Backend / Frontend | [Área] | [Confirmado / A confirmar] |

---

## Dúvidas em Aberto

| # | Dúvida | Responsável | Prazo |
|---|--------|-------------|-------|
| 1 | [O que precisa ser respondido] | [Nome] | [Data] |
