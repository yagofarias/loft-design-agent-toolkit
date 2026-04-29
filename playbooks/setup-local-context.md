---
name: setup-local-context
description: >
  Playbook guiado para ajudar o squad a preencher a camada de contexto local
  do toolkit. Faz perguntas progressivas e produz os arquivos de context/local/
  prontos para uso pelos agentes. Usar uma vez por squad, ou quando o contexto
  mudar significativamente (novo produto, novo público, pivô de estratégia).
tools: Read, Write
model: sonnet
---

# Playbook: Setup do Contexto Local do Squad

Este playbook guia o designer (ou o responsável pelo toolkit no squad) a preencher os arquivos de contexto local. Esses arquivos são o que transforma os agentes genéricos em agentes que conhecem o seu domínio.

**Tempo estimado:** 30–60 minutos  
**Quem deve preencher:** Designer de produto do squad, em conjunto com PM quando possível  
**Quando refazer:** A cada mudança significativa de estratégia, público ou produto

---

## Antes de começar

Leia os arquivos globais para entender o que já está definido — o contexto local **complementa**, não repete:

- `context/global/product-principles.md` — princípios e missão da Loft
- `context/global/brand-voice.md` — voz e tom global da marca
- `context/global/design-system.md` — referências do Copan

---

## Fase 1 — Contexto do Squad (`context/local/context.md`)

Responda as perguntas abaixo. Ao final, o agente preencherá o arquivo.

**Sobre o domínio:**

1. Qual é o nome do seu squad / vertical / produto?
2. Em uma frase: qual problema de negócio o seu squad resolve para a Loft?
3. Quem são os usuários diretos do produto do seu squad? (ex: gestor de imobiliária, corretor, inquilino, proprietário)
4. Em que etapa da jornada imobiliária o seu produto atua? (ex: captação de leads, gestão de locação, análise de crédito, pós-contrato)

**Sobre as regras de negócio:**

5. Quais são as 3 regras de negócio mais importantes que um designer novo precisaria saber para não errar?
6. Existe alguma limitação técnica ou de produto que afeta frequentemente as decisões de design? (ex: integração com banco X, fluxo de aprovação manual, SLA definido)
7. Quais são os indicadores que o squad usa para medir sucesso? (ex: taxa de conversão de proposta, tempo de análise, NPS)
8. Existe algum termo específico do domínio que tem significado diferente do uso comum? (ex: "contrato" no seu squad significa X, não Y)

**Sobre o produto atual:**

9. Qual é o estado atual do produto — em escala, em construção, ou em reformulação?
10. Quais são as principais dores conhecidas dos usuários com o produto hoje?

---

## Fase 2 — Personas (`context/local/personas.md`)

Para cada persona relevante no seu squad, responda:

> Se o squad já tiver personas documentadas em outra ferramenta, resuma aqui o essencial — não precisa ser exaustivo.

**Para cada persona (repita o bloco quantas vezes precisar):**

1. Qual é o nome que o squad dá para essa persona? (pode ser informal, ex: "O Gestor Pequeno")
2. Descreva em uma frase quem é essa pessoa e o que ela faz.
3. Por que essa persona é específica para o seu squad — o que a torna diferente de outros usuários Loft?
4. Como ela usa o produto do seu squad?
   - Dispositivo principal: mobile / desktop / ambos?
   - Com que frequência: diário / semanal / eventual?
   - Em qual momento: no escritório, em campo, em casa?
   - Nível de familiaridade com o domínio: leigo / intermediário / especialista?
5. Quais são os 2 objetivos principais dela neste contexto?
6. Quais são os 2 maiores medos ou frustrações dela neste processo?
7. O que ela já sabe e o design pode assumir?
8. O que ela não sabe e o design precisa deixar claro?
9. Se ela pudesse falar com o produto, o que diria? (uma frase representativa)

---

## Fase 3 — Públicos e Comunicação (`context/local/target-audiences.md`)

> Diferente das personas (que descrevem quem é o usuário), os públicos descrevem como comunicar com diferentes segmentos.

1. O seu produto atende mais de um perfil de comunicação? (ex: pequena imobiliária vs. grande rede, proprietário vs. inquilino)
2. Para cada segmento:
   - Como esse segmento prefere receber informação — linguagem técnica ou acessível?
   - Qual é o nível de autonomia esperado — ele precisa de mais orientação ou de mais controle?
   - Há alguma sensibilidade específica na comunicação com esse segmento? (ex: não mencionar fiador, não usar o termo "inadimplência" diretamente)
   - Qual exemplo de copy funciona bem para ele?
   - Qual exemplo de copy claramente não funciona?
3. Existem contextos de comunicação sensível no seu domínio que exigem cuidado extra? (ex: crédito negado, inadimplência, rescisão de contrato)

---

## Fase 4 — Tom Local (`context/local/brand-voice-local.md`)

> O tom local ajusta a voz global da Loft para o contexto específico do seu produto. Só preencha onde o seu domínio realmente exige um ajuste.

1. O tom global da Loft (direto, confiável, parceiro) precisa de algum ajuste no seu domínio? Como?
2. Existem termos que o seu squad usa de forma diferente do padrão global? (adicionar ao glossário local)
3. Existem situações emocionalmente sensíveis frequentes no seu domínio? (ex: crédito negado, rescisão, inadimplência) — qual é o tom correto para cada uma?
4. Copies do seu produto que você considera referência (aprovados)?
5. Copies ou padrões de linguagem que claramente não funcionam no seu domínio?

---

## Fase 5 — Concorrentes (`context/local/competitors.md`)

> Esta camada ajuda os agentes a entender o campo competitivo do seu domínio sem precisar pesquisar do zero em cada projeto.

1. Quais são os 2–3 concorrentes diretos mais relevantes para o seu produto?
   - Para cada um: o que eles fazem bem? O que fazem mal? Como a Loft se diferencia?
2. Existem produtos adjacentes (não concorrentes diretos, mas que competem pela atenção ou pelo fluxo do usuário)?
3. Existem referências de fora do mercado imobiliário que o squad usa como inspiração de UX ou produto?
4. Há algo que um concorrente faz que o squad deliberadamente optou por não copiar — e por quê?

---

## Fase 6 — Geração dos Arquivos

Com base nas respostas coletadas, preencha os arquivos em sequência:

```
1. Abra context/local/context.md       → preencha com respostas da Fase 1
2. Abra context/local/personas.md      → preencha com respostas da Fase 2
3. Abra context/local/target-audiences.md  → preencha com respostas da Fase 3
4. Abra context/local/brand-voice-local.md → preencha com respostas da Fase 4
5. Crie context/local/competitors.md   → preencha com respostas da Fase 5
```

Para cada arquivo:
- Remova as seções que não se aplicam ao squad
- Adicione seções que o squad precisar e que não estejam no template
- Marque com `[A VALIDAR]` qualquer informação que ainda precisa de confirmação

---

## Checklist de Conclusão

- [ ] `context.md` preenchido com domínio, regras de negócio e indicadores de sucesso
- [ ] `personas.md` com ao menos 1 persona real (não o template vazio)
- [ ] `target-audiences.md` com ao menos 1 segmento de comunicação
- [ ] `brand-voice-local.md` com ajustes específicos do domínio (ou nota de que o global é suficiente)
- [ ] `competitors.md` criado com ao menos 2 concorrentes diretos
- [ ] Nenhum arquivo com dados contradizendo `context/global/` sem justificativa

## Comportamento esperado do agente

- Faça as perguntas fase por fase — não despeje tudo de uma vez
- Aceite respostas curtas, listas brutas, nomes informais — você vai estruturar
- Se uma pergunta não se aplicar ao squad, pule e documente o motivo
- Ao gerar cada arquivo, mostre o resultado e peça confirmação antes de salvar
- Sinalize claramente o que ficou como `[A VALIDAR]` para não gerar falsa confiança
- Ao final, liste quais agentes já podem ser usados com o contexto preenchido
