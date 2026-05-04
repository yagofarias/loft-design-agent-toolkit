---
name: ux-writing
description: >
  Critérios para avaliar e escrever copies de interface da Loft. Aplica os
  princípios do brand-voice.md em contextos específicos de UI: CTAs, erros,
  empty states, labels, confirmações e comunicação financeira.
---

# Skill: UX Writing

## Propósito

Copy de interface é design. Uma label ambígua causa suporte. Um erro genérico gera frustração. Um CTA vago diminui conversão.

Esta skill aplica os princípios de voz e tom da Loft em contextos específicos de interface. **A fonte de verdade para voz, tom e glossário é `context/global/brand-voice.md`** — leia antes de aplicar esta skill. O `context/local/brand-voice-local.md` do squad complementa com variações específicas do domínio.

---

## Os 3 Princípios Base

Direto do brand-voice.md — valem para toda copy de interface:

**Claro** — sem jargões, linguagem familiar ao usuário do produto
**Conciso** — eficiente e fácil de escanear. Cada palavra precisa ganhar seu espaço
**Útil** — todo texto orienta para a próxima ação. Não existe copy neutra

---

## Critérios por Tipo de Copy

### CTAs e Botões

**Padrão:** `[Verbo imperativo] + [Objeto específico]`

| ✅ | ❌ | Por quê |
|----|----|----|
| "Enviar proposta" | "Confirmar" | Confirmar o quê? |
| "Analisar fiança" | "Avançar" | Para onde? |
| "Ver contrato" | "Clique aqui" | Nunca "clique aqui" como CTA |
| "Tentar novamente" | "OK" | "OK" não orienta ação |
| "Salvar rascunho" | "Salvar" | Específico reduz ansiedade em fluxos financeiros |

### Labels e Títulos de Campo

- Use substantivos, não instruções — "Nome completo", não "Digite seu nome completo"
- Seja específico sobre o formato quando necessário — "CPF (000.000.000-00)", não "Documento"
- Evite abreviações que possam confundir — "Nº do contrato", não "Nº contrato"

### Placeholder Text

- Mostre exemplos de formato, não repita o label — `000.000.000-00`, não "Digite seu CPF"
- Nunca use placeholder como substituto de label — desaparece quando o usuário digita
- Para campos opcionais: indicar no label `(opcional)`, não no placeholder

### Mensagens de Erro

**Estrutura:** `[O que aconteceu] + [Por que, quando possível] + [O que fazer]`

| ✅ | ❌ |
|----|-----|
| "Não conseguimos processar. Verifique os dados do cartão e tente novamente." | "Erro de pagamento." |
| "CPF inválido. Verifique os números e tente novamente." | "Campo inválido." |
| "Digite seu nome para continuar." | "Você esqueceu de preencher o nome." |
| "Não encontramos esse CNPJ. Verifique se o número está correto." | "CNPJ não encontrado." |

**Erro do sistema vs. erro do usuário:**
- Sistema falhou → use "nós": "Não conseguimos carregar"
- Usuário errou → informe a ação correta, não o erro: "Digite um e-mail válido"

### Mensagens de Confirmação e Sucesso

- Confirme o que aconteceu: "Proposta enviada" não "Pronto!"
- Indique o próximo passo quando houver: "Garantia aprovada. O contrato está pronto para assinatura."
- Evite superlativos: "Sua proposta foi enviada com sucesso" → "Proposta enviada"

### Empty States

**Estrutura:** `[Por que está vazio] + [O que fazer para mudar isso]`

| ✅ | ❌ |
|----|-----|
| "Nenhuma proposta recebida ainda. Compartilhe o link do seu anúncio para começar." | "Sem resultados." |
| "Você ainda não tem contratos ativos. Finalize uma proposta para criar seu primeiro contrato." | "Nenhum contrato encontrado." |

### Tooltips e Textos de Ajuda

- Responda à pergunta implícita "o que é isso?" ou "por que preciso disso?"
- Máximo de 2 linhas — se precisar de mais, é conteúdo de ajuda, não tooltip
- Exemplo: "Seu CPF é usado para verificar sua identidade. Não compartilhamos com terceiros."

### Diálogos de Confirmação

**Para ações destrutivas ou irreversíveis:**
- Título: descreva a ação, não peça confirmação — "Cancelar proposta" não "Tem certeza?"
- Body: consequência clara — "Esta proposta será cancelada e o inquilino será notificado."
- CTAs: específicos — "Cancelar proposta" e "Manter proposta" — nunca "Sim/Não"

---

## Copy para Contextos Sensíveis da Loft

Fluxos financeiros e imobiliários têm contextos que exigem atenção extra ao tom.

### Comunicação financeira

- Preciso e direto, sem eufemismos
- Valores monetários sempre formatados: "R$ 2.400,00" — não "2400" nem "R$ 2.4k"
- Períodos sempre explícitos: "2 meses de aluguel" — não "2x"

### Crédito negado / Fiança reprovada

- Tom neutro — sem culpar o usuário, sem drama
- Explique o que foi possível, não só o que não foi
- Ofereça alternativa quando existir
- ✅ "Não foi possível aprovar a garantia neste momento. Veja outras modalidades disponíveis."
- ❌ "Sua solicitação foi negada."

### Pendência de documentação

- Seja específico sobre o que falta — nunca "documentação incompleta" sem detalhar
- Indique prazo quando houver
- ✅ "Falta o comprovante de renda. Envie até [data] para continuar com a análise."
- ❌ "Documentação pendente."

### Copy de segurança e LGPD

Ao solicitar dados sensíveis, explique o benefício e dê acesso à política:
- ✅ "Com essas informações, mantemos você atualizado sobre o contrato. Confira nossa Política de Privacidade."
- ❌ "Utilizaremos seus dados conforme nossa política."

---

## B2B vs. B2C — Calibragem de Tom

A Loft atende dois perfis com necessidades de comunicação diferentes. O contexto do squad (`context/local/brand-voice-local.md`) define qual prevalece.

| Contexto | Tom | Exemplo |
|----------|-----|---------|
| **Gestor / Imobiliária (B2B)** | Parceiro, orientado a resultado, eficiente | "Sua imobiliária recebeu 3 novas propostas. Analise agora." |
| **Corretor (B2B)** | Prático, ágil, direto | "Fiança aprovada. Cliente pode assinar." |
| **Proprietário (B2C)** | Claro, tranquilizador, sem jargão | "Seu aluguel foi pago e está a caminho da sua conta." |
| **Inquilino (B2C)** | Acessível, empático, orientador | "Seu contrato está pronto. Leia com atenção antes de assinar." |

---

## Constraints de Comprimento

| Elemento | Limite recomendado |
|----------|-------------------|
| Label de campo | 3–4 palavras |
| CTA principal | 2–4 palavras |
| Título de modal/dialog | 5–8 palavras |
| Mensagem de erro inline | 1–2 linhas |
| Toast / notificação | 1 linha |
| Empty state — título | 6–10 palavras |
| Empty state — descrição | 1–2 linhas |
| Tooltip | Máximo 2 linhas |

---

## Checklist de Revisão

- [ ] Segue os princípios de voz da Loft (brand-voice.md)?
- [ ] Está em português brasileiro sem anglicismos desnecessários?
- [ ] CTAs têm verbo imperativo + objeto específico?
- [ ] Mensagens de erro dizem o que aconteceu E o que fazer?
- [ ] Empty states explicam por que está vazio E o que fazer?
- [ ] Copy para dados sensíveis tem justificativa de benefício?
- [ ] Ações destrutivas têm linguagem específica (não "Sim/Não")?
- [ ] Comprimento está dentro dos limites para o componente?
- [ ] Terminologia é consistente com o glossário do brand-voice.md?
- [ ] Tom está calibrado para o público (B2B ou B2C) do contexto do squad?
