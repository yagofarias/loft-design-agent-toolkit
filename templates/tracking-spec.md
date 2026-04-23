---
version: "1.0"
agent: tracking-handoff
status: "[RASCUNHO | APROVADO]"
---

# Tracking Spec

**Projeto:** [Nome]
**Jornada:** [Nome]
**Ferramenta:** [Amplitude / Mixpanel / GA4]
**Designer:** [Nome]
**Data:** [DD/MM/AAAA]
**Journey Spec:** [Link]

---

## Objetivo de Medição

[Quais perguntas de negócio esta instrumentação deve responder?]

- Qual é a taxa de conclusão do fluxo?
- Em qual etapa os usuários mais abandonam?
- Quanto tempo os usuários passam em cada passo?

---

## Convenção de Nomenclatura

**Padrão:** `[substantivo]_[verbo]` em `snake_case`
**Exemplos existentes no produto:** [Listar para manter consistência]

---

## Inventário de Eventos

| Evento | Tela | Gatilho | Tipo | Prioridade |
|--------|------|---------|------|-----------|
| [nome_do_evento] | [Tela] | [O que dispara] | screen_viewed / interaction / conversion | P0/P1/P2 |

---

## Especificação Detalhada

### [nome_do_evento]

**Descrição:** [O que este evento representa]
**Gatilho:** [Exatamente o que acontece para disparar]
**Tela:** [Onde ocorre]

**Propriedades obrigatórias:**

| Propriedade | Tipo | Valores aceitos | Descrição |
|-------------|------|-----------------|-----------|
| [nome] | string / integer / boolean | [Enum ou exemplo] | [O que representa] |

**Exemplo de payload:**
```json
{
  "event": "[nome_do_evento]",
  "properties": {
    "propriedade_1": "valor_exemplo"
  }
}
```

---

## Funil de Conversão

```
FUNIL: [Nome do objetivo]

1. [evento_entrada] — entrada no fluxo
2. [evento_progresso] — checkpoint relevante
3. [evento_conversão] — conclusão
```

---

## Eventos de Erro

| Evento de erro | Quando ocorre | Propriedade de contexto |
|---------------|--------------|------------------------|
| [nome_error_shown] | [Condição] | `error_type`: [enum] |

---

## Glossário

| Termo | Definição |
|-------|-----------|
| [Propriedade] | [O que significa neste produto] |

---

## Checklist de Implementação

- [ ] Todos os eventos P0 estão disparando?
- [ ] As propriedades obrigatórias estão presentes?
- [ ] Nenhum PII está sendo enviado?
- [ ] Os nomes seguem o padrão snake_case?
- [ ] Os eventos aparecem na ferramenta de analytics?
