---
name: gut-check
description: >
  Sabatina de 5 perguntas críticas feitas antes de avançar em qualquer agente.
  Usa perspectivas de produto, negócio, design e personas do contexto local para
  revelar pontos cegos antes que virem problemas. Engenharia entra apenas no
  aprofundamento opcional.
---

# Skill: Gut-Check

Esta skill interrompe o avanço automático para questionar o que está sendo assumido. A ideia não é travar — é garantir que você está resolvendo o problema certo, do jeito certo, para a pessoa certa, antes de investir tempo em estrutura ou execução.

---

## Quando ativar

- Sugerida automaticamente após o intake de qualquer agente
- Pode ser ativada a qualquer momento com "me faz o gut-check" ou "me questiona"
- Especialmente valiosa quando o brief parece claro demais ou quando o escopo foi definido por outra pessoa

---

## Protocolo de execução

### Passo 1 — Seleção das 5 perguntas

Com base no que foi descrito no intake, selecione as **5 perguntas de maior risco** para este contexto específico. Não use um questionário fixo — priorize o que pode mais facilmente estar errado ou não validado.

Selecione a partir das perspectivas abaixo, escolhendo as mais relevantes para o contexto:

**🔵 Produto**
- Esse é realmente o problema que precisamos resolver agora, ou existe outro mais urgente por trás?
- Se isso funcionar perfeitamente, o que muda para o usuário ou para o negócio?
- Qual evidência temos de que esse problema existe da forma que estamos assumindo?
- Já tentamos resolver isso antes? O que aprendemos?
- O que acontece se não fizermos isso?

**🟡 Negócio**
- Quem aprova essa solução e quais são os critérios de sucesso para essa pessoa?
- Como medimos se isso funcionou? Existe uma métrica clara?
- Existe alguma restrição de prazo, compliance ou dependência que pode inviabilizar a abordagem?
- Esse é o momento certo para resolver isso, ou existe uma dependência estratégica não resolvida?
- Qual o custo de estar errado aqui?

**🎨 Design**
- O usuário que vai usar isso entenderia o que precisa fazer sem instrução?
- Existe um padrão estabelecido no produto ou no mercado que o usuário já conhece? Por que nos afastaríamos dele?
- Qual é o pior momento possível em que esse fluxo pode ser usado? O design suporta isso?
- O que acontece quando algo dá errado no meio do caminho?
- Estamos resolvendo para o usuário ou para quem pediu a feature?

**👤 Persona** *(use quando existir persona definida em `context/local/personas.md`)*
- [Nome da persona] usaria isso da forma que estamos imaginando? Em qual situação ela encontraria esse fluxo?
- O que [Nome da persona] faria se encontrasse esse problema hoje, sem essa solução?
- Qual parte desse fluxo [Nome da persona] provavelmente ignoraria ou erraria?
- Essa solução faz mais sentido para [Persona A] ou para [Persona B]? Estamos servindo às duas da mesma forma?

---

### Passo 2 — Condução da sabatina

Para cada uma das 5 perguntas selecionadas:

1. **Identifique a perspectiva** — deixe claro de onde a pergunta vem (🔵 Produto / 🟡 Negócio / 🎨 Design / 👤 [Nome da persona])
2. **Faça a pergunta** — uma de cada vez, sem agrupar
3. **Apresente sua resposta sugerida** — o que você acredita ser verdadeiro com base no contexto descrito. Isso força uma posição, não apenas uma sonda.
4. **Aguarde a resposta** — não avance para a próxima pergunta até receber

> Exemplo de formato:
>
> **🔵 Produto**
> Pergunta: Esse é realmente o problema que precisamos resolver agora, ou existe outro mais urgente por trás?
> Minha leitura: Com base no que você descreveu, parece que o problema real pode ser [X], não [Y]. A solução proposta resolveria o sintoma mas não a causa. Faz sentido?

---

### Passo 3 — Encerramento das 5 perguntas

Após a quinta resposta, apresente um resumo rápido:

- **Pontos validados** — o que ficou mais sólido após as respostas
- **Pontos em aberto** — o que ainda não está claro ou tem risco
- **Maior risco identificado** — o ponto que mais merece atenção antes de avançar

Em seguida, pergunte:

> "Quer aprofundar em algum ponto antes de avançar? Posso ir mais fundo nas áreas de maior risco — e se quiser, incluo a perspectiva de engenharia para avaliar viabilidade e complexidade técnica."

---

### Passo 4 — Aprofundamento (opcional)

Se a pessoa quiser continuar:

- Concentre nas áreas de maior risco identificadas nas 5 perguntas
- Inclua a perspectiva de engenharia aqui:

**🟢 Engenharia** *(só no aprofundamento)*
- Existe alguma dependência técnica que pode inviabilizar essa abordagem?
- Qual parte desse fluxo tem maior risco de complexidade inesperada?
- Existem APIs, integrações ou estados de dados que precisam estar resolvidos antes?
- A solução proposta escala para o volume esperado?

Continue com uma pergunta por vez até a pessoa sinalizar que quer avançar.

---

## Comportamento esperado

- Nunca agrupe perguntas — uma de cada vez, sempre
- Sempre apresente uma resposta sugerida antes de esperar a do designer — sem posição, não há sabatina
- Priorize as perspectivas mais relevantes para o contexto descrito — não cubra todas se não fizer sentido
- Use personas do contexto local quando existirem — elas tornam as perguntas concretas, não abstratas
- Não transforme o gut-check em interrogatório — o tom é de parceiro que quer que o projeto dê certo, não de oponente
- Se as respostas revelarem um problema estrutural no brief, sinalize antes de continuar
