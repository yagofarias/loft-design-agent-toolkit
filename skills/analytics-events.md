---
name: analytics-events
description: >
  Framework para modelar eventos de analytics a partir de jornadas de
  design. Define taxonomia, nomenclatura, tipos de propriedade e priorização
  de eventos para Amplitude, Mixpanel e similares.
---

# Skill: Analytics Events

## Propósito

Eventos de analytics são a memória do produto. Modelados bem no design, garantem que o time consiga responder perguntas de negócio reais após o lançamento — sem depender de reimplementação.

---

## Princípio base: comece pelo objetivo

Antes de nomear qualquer evento, responda:
- Qual pergunta de negócio este evento ajuda a responder?
- Qual métrica do design-doc (seção 2.2) este evento instrumenta?

Eventos sem objetivo claro viram ruído. Menos eventos bem definidos > muitos eventos vagos.

---

## Taxonomia e Nomenclatura

**Formato:** `[substantivo]_[verbo_no_passado]` em `snake_case` — sempre do ponto de vista do usuário

| Tipo de ação | Padrão | Exemplo Loft |
|-------------|--------|-------------|
| Visualização de tela | `[tela]_visualizada` | `analise_fianca_visualizada` |
| Ação completada | `[objeto]_[verbo_passado]` | `proposta_enviada`, `fianca_aprovada` |
| Etapa de fluxo | `[fluxo]_etapa_[N]_concluida` | `cadastro_etapa_2_concluida` |
| Abandono | `[fluxo]_abandonado` | `analise_fianca_abandonada` |
| Erro exibido | `[contexto]_erro_exibido` | `validacao_documentos_erro_exibido` |
| Seleção / escolha | `[objeto]_selecionado` | `imobiliaria_selecionada` |

**Regras de nomenclatura:**
- Snake_case sempre — nunca camelCase ou kebab-case
- Verbo no passado — `proposta_enviada`, não `enviar_proposta`
- Perspectiva do usuário — `fianca_aprovada` (o usuário viu isso), não `sistema_aprovou_fianca`
- Específico o suficiente — `analise_fianca_iniciada` > `botao_clicado`

---

## Tipos de Propriedade — distinção crítica

**Event properties** — atributos específicos daquela instância do evento. Existem apenas naquele momento.

```
EVENTO: proposta_enviada
EVENT PROPERTIES:
  proposta_id: string        — ID interno, nunca dados pessoais
  imobiliaria_id: string     — ID da imobiliária
  valor_aluguel: integer     — em centavos, sem PII
  modalidade_garantia: enum  — ["fianca_aluguel", "garantia_investe", "caucao"]
  tempo_preenchimento_seg: integer
```

**User properties** — atributos do usuário que persistem e se aplicam a eventos futuros. Modificar com cuidado — afeta análises retroativas.

```
USER PROPERTIES (setadas/atualizadas neste fluxo):
  plano_imobiliaria: enum    — ["basico", "pro", "enterprise"]
  data_primeiro_contrato: date
  total_contratos_ativos: integer
```

**Context properties** — enviadas automaticamente com todos os eventos. Definidas uma vez, não repetir em cada evento.

```
CONTEXT PROPERTIES (automáticas):
  user_id: string            — hash anônimo, não o CPF
  imobiliaria_id: string
  platform: enum             — ["web", "mobile_ios", "mobile_android"]
  user_role: enum            — ["gestor", "corretor", "admin"]
```

---

## Regras para Propriedades

- **Sem PII** — nunca CPF, nome completo, e-mail, endereço, renda individual
- **IDs internos, não labels** — `imobiliaria_id: "imob_123"` não `imobiliaria_nome: "Imóveis SP"`
- **Enums com valores definidos** — documente os valores aceitos; evita strings livres que poluem dados
- **Valores monetários em centavos** — `valor_aluguel: 250000` (R$ 2.500,00), nunca float para dinheiro
- **Booleanos para flags** — `tem_foto_principal: true` não `foto: "sim"`
- **Nomes consistentes entre eventos** — se `imobiliaria_id` em um evento, não use `id_imobiliaria` em outro

---

## Funil de Conversão

Para medir conversão corretamente, todos os eventos do funil precisam da mesma **propriedade de ancoragem** — que identifica o objeto sendo convertido.

```
FUNIL: [Nome do objetivo]
PROPRIEDADE DE ANCORAGEM: [ex: proposta_id — presente em todos os eventos]

1. [evento_entrada]     — usuário iniciou o fluxo
2. [evento_progresso]   — checkpoint relevante
3. [evento_conversão]   — conclusão do objetivo

ABANDONO: usuário que dispara [evento_entrada] e não dispara
[evento_conversão] em [N horas/dias]
```

Sem a propriedade de ancoragem, o funil conta qualquer evento no fluxo — não a mesma proposta, o mesmo contrato, o mesmo usuário no mesmo objeto.

---

## Priorizando Eventos

| Prioridade | Critério | Ação |
|------------|----------|------|
| **P0** | Mede o objetivo principal definido no design-doc | Implementar obrigatoriamente antes do lançamento |
| **P1** | Identifica pontos de abandono ou erros críticos | Implementar no lançamento |
| **P2** | Enriquece análise, mas não bloqueia decisões | Implementar se houver capacidade |

---

## Verificações antes de entregar a spec

- [ ] Cada evento responde a uma pergunta de negócio específica?
- [ ] Os nomes seguem `[substantivo]_[verbo_passado]` em snake_case?
- [ ] Event properties e user properties estão distintas?
- [ ] A propriedade de ancoragem está presente em todos os eventos do funil?
- [ ] Nenhuma propriedade contém PII?
- [ ] Enums têm os valores aceitos documentados?
- [ ] Context properties estão definidas uma vez — não repetidas em cada evento?
