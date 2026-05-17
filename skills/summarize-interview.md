---
name: summarize-interview
description: >
  Sintetiza o transcript de uma sessão de pesquisa em achados estruturados:
  perfil do participante, temas principais com quotes, jobs identificados,
  pain points com severidade, workarounds, surpresas e próximos passos.
  Usado na Fase 8 do /research-plan após cada sessão de campo.
---

# Skill: Summarize Interview

## Propósito

Transformar a gravação ou transcript de uma sessão em achados acionáveis. Esta skill garante que nenhuma insight se perde entre o campo e a síntese — e que o formato é consistente entre todas as sessões, facilitando a análise cruzada.

**Input:** transcript da sessão (texto, cópia de transcrição automática, ou notas do entrevistador).  
**Output:** resumo estruturado pronto para Dovetail e para atualizar o research-plan.md.

---

## Protocolo de síntese

### Passo 1 — Perfil do participante

Extraia do transcript:

```
Participante: [P1, P2... — nunca nome real]
Persona: [qual persona do squad mais se aproxima]
Contexto: [cargo/papel, frequência de uso, dispositivo principal]
Sessão: [data, duração, método]
```

### Passo 2 — Leitura orientada pelas hipóteses

Antes de sintetizar, releia as perguntas de pesquisa e hipóteses do `research-plan.md`. Procure no transcript evidências de confirmação ou invalidação para cada hipótese.

### Passo 3 — Temas principais

Identifique os 3–5 temas mais recorrentes ou significativos da sessão. Para cada tema:

```
## Tema: [nome descritivo]

**Observação:** [o que o participante fez, disse ou demonstrou]
**Quote de suporte:** "[trecho literal do transcript]"
**Interpretação:** [o que isso indica sobre o comportamento ou necessidade]
**Hipótese relacionada:** [P1 / P2 / novo achado]
```

### Passo 4 — Jobs identificados

*Jobs observados durante a sessão — o que o participante realmente estava tentando fazer, independentemente de como verbalizou.*

```
Job: [formato: "Quando [situação], quero [motivação], para [resultado]"]
Evidência: [trecho ou comportamento que revelou este job]
Já documentado nas personas? [Sim — P.X / Não — novo]
```

### Passo 5 — Pain points

| # | Pain point | Severidade | Momento | Quote |
|---|-----------|-----------|---------|-------|
| 1 | [descrição] | 🔴 Crítico / 🟡 Moderado / ⚪ Leve | [etapa da jornada] | "[trecho]" |

**Critério de severidade:**
- 🔴 Crítico: bloqueou a tarefa ou causou abandono
- 🟡 Moderado: criou fricção visível mas foi contornado
- ⚪ Leve: comentário negativo sem impacto na tarefa

### Passo 6 — Workarounds

*Soluções improvisadas que o participante usa para contornar limitações do produto.*

```
Workaround: [o que o participante faz]
Contexto: [quando e por quê usa este workaround]
Oportunidade: [o que esse comportamento sugere para o design]
```

### Passo 7 — Surpresas

*O que não estava nas hipóteses e merece atenção.*

- [Comportamento inesperado]
- [Crença ou modelo mental que diferiu do esperado]

### Passo 8 — Próximos passos desta sessão

*Ações concretas derivadas desta sessão — não da pesquisa inteira.*

- [ ] [Validar com outras sessões]
- [ ] [Pesquisar mais sobre X]
- [ ] [Ajustar roteiro para a próxima sessão]

---

## Após sintetizar todas as sessões

Quando todas as sessões forem sintetizadas, o agente de research-plan conduz a análise cruzada:

1. Agrupa achados similares entre participantes
2. Identifica padrões recorrentes (aparecem em 3+ sessões = tema)
3. Identifica outliers (aparecem em 1 sessão = registrar, não generalizar)
4. Preenche a seção Achados do research-plan.md
5. Atualiza o design-doc e o acervo do squad
