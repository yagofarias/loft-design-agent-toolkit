---
name: state-coverage
description: >
  Garante que todos os estados necessários de telas e componentes foram
  identificados antes de desenhar. Cobre estados universais, de interação,
  parciais e específicos de fluxos financeiros e de aprovação da Loft.
---

# Skill: State Coverage

## Propósito

Designers tendem a desenhar o estado ideal. Devs precisam implementar todos os estados. Esta skill garante que nenhum estado foi esquecido antes de abrir o Figma — evitando retrabalho e perguntas durante a implementação.

**Distinção com `copan-check`:**
- `state-coverage` → o que você precisa *criar* (identificação)
- `copan-check` → se o que você *criou* usa os componentes certos (validação)

---

## Telas com Dados Remotos

Toda tela que busca dados de uma API precisa destes estados. Não são opcionais.

| Estado | Quando ocorre | O que mostrar |
|--------|---------------|---------------|
| **Loading** | Aguardando resposta da API | Skeleton (conteúdo) ou spinner (ação) |
| **Partial** | Dados carregando progressivamente | Primeiros itens visíveis, restantes em skeleton |
| **Sucesso com dados** | Resposta retornou com conteúdo | Estado principal |
| **Sucesso sem dados** | Resposta retornou vazia | Empty state com orientação e CTA |
| **Erro de rede** | Sem conexão ou timeout | Mensagem + botão de retry |
| **Erro de servidor** | API retornou 5xx | Mensagem + alternativa |
| **Erro de autorização** | Usuário sem permissão (403) | Mensagem contextual + o que pode fazer |
| **Offline** | Sem conexão | Conteúdo cacheado + aviso |

**Skeleton vs. Spinner:**
- **Skeleton** → conteúdo aparece no mesmo lugar (listas, cards, textos)
- **Spinner** → ação ou navegação (submit, carregamento de página)
- **Evitar loading** para respostas < 300ms — o flash é pior que não ter estado

---

## Formulários e Inputs

| Estado | Quando ocorre |
|--------|---------------|
| **Default / Em branco** | Campo não interagido |
| **Focused** | Campo em edição ativo |
| **Preenchido / Válido** | Input com valor aceito |
| **Inválido / Erro** | Validação falhou — mensagem inline |
| **Desabilitado** | Campo não editável no momento |
| **Readonly** | Visível mas não editável (modo exibição) |
| **Loading** | Validação assíncrona em andamento |

---

## Ações e CTAs

| Estado | Quando ocorre |
|--------|---------------|
| **Default** | Pronto para interação |
| **Hover / Focused** | Mouse sobre o elemento ou foco por teclado |
| **Loading** | Aguardando resultado da ação |
| **Sucesso** | Ação completou com êxito |
| **Erro** | Ação falhou |
| **Desabilitado** | Ação não disponível no momento |

**Sobre hover/focused:** essencial para acessibilidade — usuários de teclado precisam saber qual elemento está focado. Nunca omitir o focus state.

---

## Estados de Aprovação e Fluxos Financeiros

Específicos de produtos Loft — fiança, crédito, contratos, análises.

| Estado | Quando ocorre | O que mostrar |
|--------|---------------|---------------|
| **Aguardando análise** | Enviado, análise não iniciada | Indicador de fila + tempo estimado |
| **Em análise** | Processo em andamento | Progresso + o que está sendo verificado |
| **Aprovado** | Resultado positivo | Confirmação + próximos passos claros |
| **Aprovado com ressalvas** | Aprovação parcial ou condicional | O que foi aprovado + o que está pendente |
| **Reprovado** | Resultado negativo | Motivo (quando possível) + alternativas |
| **Pendente de documentação** | Aguardando documentos do usuário | O que falta + prazo + como enviar |
| **Expirado** | Prazo vencido | O que expirou + como renovar |
| **Cancelado** | Processo encerrado por qualquer parte | Por quem + o que fazer |
| **Em revisão manual** | Requer análise humana | Status claro de que uma pessoa está analisando |

---

## Timing de Transições

| Situação | Comportamento esperado |
|----------|----------------------|
| Resposta da API < 300ms | Não exibir loading — o flash é pior |
| Resposta entre 300ms e 1s | Skeleton ou spinner |
| Resposta > 1s | Skeleton obrigatório com feedback de progresso |
| Toast de sucesso | Auto-dismiss após 3–5 segundos |
| Toast de erro | Persistir até o usuário fechar ou agir |
| Loading de CTA | Desabilitar o botão imediatamente ao clicar (evitar duplo envio) |
| Transição entre estados | 150–200ms ease-out para aparecer, 100ms para desaparecer |

---

## Documentando um Estado

```
ESTADO: [Nome]
GATILHO: [O que causa este estado]
DURAÇÃO: [Permanente / Temporário / Até interação do usuário]
COMPONENTES AFETADOS: [O que muda visualmente]
AÇÃO DISPONÍVEL: [O que o usuário pode fazer neste estado]
TRANSIÇÃO PARA: [Qual estado vem depois e por quê]
ANIMAÇÃO: [Se houver — tipo, duração, easing]
```

---

## Nomenclatura Padrão

| Token | Uso |
|-------|-----|
| `default` / `idle` | Estado base sem interação |
| `loading` / `skeleton` | Aguardando dados ou ação |
| `success` / `fulfilled` | Concluído com sucesso |
| `error` / `failed` | Falha no fetch ou na ação |
| `empty` | Sem dados para exibir |
| `disabled` | Interação não permitida |
| `readonly` | Visível, não editável |
| `pending` | Aguardando processamento externo |
| `approved` | Aprovado em fluxo de análise |
| `rejected` | Reprovado em fluxo de análise |
| `expired` | Prazo vencido |

---

## Checklist de Cobertura

- [ ] Estado default desenhado?
- [ ] Loading/skeleton coberto para dados remotos?
- [ ] Estado partial para listas que carregam progressivamente?
- [ ] Estado vazio com orientação e CTA?
- [ ] Todos os erros cobertos: rede, servidor, autorização?
- [ ] Estado de sucesso com feedback claro?
- [ ] Estado desabilitado quando aplicável?
- [ ] Hover e focus states para elementos interativos?
- [ ] Para fluxos financeiros: aprovação, pendência, expiração e cancelamento?
- [ ] Timing de transições definido para estados críticos?
