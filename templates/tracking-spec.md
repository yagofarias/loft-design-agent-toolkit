---
version: "2.0"
agent: delivery-handoff
status: "[Rascunho | Aprovado]"
---

# Tracking Spec

**Projeto:** [Nome]
**Jornada:** [Nome]
**Designer:** [Nome]
**Data:** [DD/MM/AAAA]
**Ferramenta:** [Amplitude / Mixpanel / GA4]
**Journey Spec:** [Link]
**Design Doc:** [Link — seção 2.2 define as métricas que esta spec instrumenta]

---

## Objetivos de Medição

*Conecte às métricas definidas na seção 2.2 do design-doc. Esta spec existe para responder as perguntas de negócio definidas lá.*

**Métrica primária a instrumentar:**
> [Copiar da seção 2.2 do design-doc — ex: "Reduzir tempo médio de análise de fiança de 40 para 15 minutos"]

**Perguntas que os eventos desta spec devem responder:**
- [Ex: Qual é a taxa de conclusão do fluxo de análise?]
- [Ex: Em qual etapa os gestores mais abandonam?]
- [Ex: Qual o tempo médio entre o início e a aprovação da fiança?]

---

## Convenção de Nomenclatura

**Formato:** `[Substantivo]_[Verbo_no_passado]` em `snake_case` — sempre do ponto de vista do usuário

*Exemplos corretos: `fianca_analisada`, `proposta_enviada`, `contrato_assinado`*
*Exemplos incorretos: `analisar_fianca`, `send_proposal`, `contrato_assinar`*

**Capitalização:** snake_case para eventos e propriedades — tudo minúsculo com underscores

**Convenção existente no produto:** [Listar 3-5 eventos já implementados para manter consistência — ex: `proposta_criada`, `imobiliaria_cadastrada`]

---

## Context Properties

*Propriedades enviadas automaticamente em todos os eventos deste fluxo. Documente uma vez aqui — não repita em cada evento.*

| Propriedade | Tipo | Descrição | Exemplo |
|------------|------|-----------|---------|
| `user_id` | string | ID único do usuário autenticado | `"usr_abc123"` |
| `imobiliaria_id` | string | ID da imobiliária do usuário | `"imob_xyz789"` |
| `platform` | string | Web ou mobile | `"web"` |
| `user_role` | string | Papel do usuário no sistema | `"gestor"` / `"corretor"` |
| [Adicione outras propriedades de contexto relevantes para este fluxo] | | | |

---

## User Properties

*Atributos do usuário que são setados ou atualizados neste fluxo. User properties persistem — se setadas aqui, afetam análises futuras.*

| Propriedade | Quando é setada | Valor | Impacto |
|------------|----------------|-------|---------|
| [Ex: `has_completed_first_analysis`] | [Após primeira análise concluída] | `true` | [Muda comportamento do onboarding futuro] |

*Se nenhuma user property é atualizada neste fluxo, escreva "Nenhuma user property é modificada nesta jornada."*

---

## Inventário de Eventos

*Todos os eventos do fluxo. P0 = implementar antes do lançamento · P1 = necessário para análise completa · P2 = nice-to-have*

| Evento | Tela | Gatilho | Tipo | Disparo | Prioridade |
|--------|------|---------|------|---------|-----------|
| [nome_do_evento] | [Tela] | [O que dispara] | `screen_viewed` / `interaction` / `conversion` / `error` | Único / Múltiplo | P0/P1/P2 |

*Coluna **Disparo**: "Único" = dispara uma vez por sessão/fluxo · "Múltiplo" = pode disparar várias vezes*

---

## Especificação Detalhada

*Especifique todos os eventos P0 e P1. Para P2, basta o inventário acima.*

### [nome_do_evento]

**Descrição:** [O que este evento representa — do ponto de vista do usuário]
**Gatilho:** [Exatamente o que acontece para disparar — específico o suficiente para o dev implementar sem perguntar]
**Tela:** [Onde ocorre]
**Disparo:** [Único ou Múltiplo — e se múltiplo, sob quais condições]

**Propriedades do evento:**

| Propriedade | Tipo | Valores aceitos | Obrigatória? | Descrição |
|------------|------|-----------------|-------------|-----------|
| [nome] | string / integer / boolean / enum | [Lista de valores ou exemplo] | Sim / Não | [O que representa] |

**Exemplo de payload:**
```json
{
  "event": "[nome_do_evento]",
  "properties": {
    "propriedade_1": "valor_exemplo",
    "propriedade_2": 42
  }
}
```

---

## Funil de Conversão

*Para cada objetivo de negócio, defina o funil. A propriedade de ancoragem garante que o usuário percorreu o mesmo objeto — ex: mesmo `proposta_id` em todos os steps.*

```
FUNIL: [Nome do objetivo — ex: "Conclusão da análise de fiança"]

Propriedade de ancoragem: [Ex: proposta_id — deve estar presente em todos os eventos]

1. [evento_entrada]      — entrada no fluxo
2. [evento_progresso]    — checkpoint crítico
3. [evento_conversão]    — conclusão do objetivo

ABANDONO: usuário que dispara [evento_entrada] e não dispara
[evento_conversão] em [N horas / dias]
```

---

## Eventos de Erro

*Eventos disparados quando algo dá errado. Essenciais para diagnóstico de problemas em produção.*

| Evento | Quando ocorre | Propriedade de contexto | Prioridade |
|--------|--------------|------------------------|-----------|
| [nome_error_shown] | [Condição que gera o erro] | `error_type`: [enum de valores possíveis] | P0/P1 |

---

## Privacidade e LGPD

*O que NÃO pode ser enviado como propriedade de evento.*

**PII — nunca enviar:**
- CPF, CNPJ, RG ou qualquer documento de identidade
- Nome completo do usuário final
- Endereço residencial ou comercial completo
- Dados bancários (conta, agência, número de cartão)
- Renda ou faixa de renda individual
- E-mail ou telefone pessoal

**Identificadores seguros (podem ser enviados):**
- `user_id` interno do sistema (hash anônimo)
- `imobiliaria_id` (identificador da empresa, não da pessoa)
- `proposta_id`, `contrato_id` (IDs internos sem dados pessoais)

---

## Glossário

*Termos específicos deste fluxo que podem gerar confusão na implementação.*

| Termo | Definição no contexto deste produto |
|-------|-------------------------------------|
| [Propriedade ou conceito] | [O que significa especificamente aqui] |

---

## Checklist de Implementação

**Antes de marcar como pronto:**

- [ ] Todos os eventos P0 estão disparando no ambiente de staging?
- [ ] As propriedades obrigatórias estão presentes em todos os eventos P0?
- [ ] Nenhum dado PII está sendo enviado (ver seção de Privacidade acima)?
- [ ] Os nomes seguem a convenção `snake_case` e `[substantivo]_[verbo_passado]`?
- [ ] As context properties estão sendo enviadas automaticamente com todos os eventos?
- [ ] Eventos marcados como "Único" disparam apenas uma vez por fluxo?
- [ ] O funil está funcionando na ferramenta de analytics com a propriedade de ancoragem correta?
- [ ] Eventos de erro estão disparando sob as condições documentadas?
- [ ] Esta spec é aditiva ou modifica eventos existentes? Se modifica, dashboards existentes foram revisados?
- [ ] Os eventos aparecem com os nomes corretos na ferramenta de analytics?
