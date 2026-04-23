---
name: state-mapping
description: >
  Framework para identificar e documentar todos os estados necessários
  de telas e componentes. Garante que loading, erro, vazio, sucesso e
  estados de permissão estejam definidos antes da implementação.
---

# Skill: State Mapping

## Propósito

Toda tela e componente que interage com dados ou ações do usuário tem múltiplos estados. Documentar apenas o estado "feliz" é uma das causas mais comuns de retrabalho entre design e dev.

## Estados Obrigatórios por Categoria

### Telas com dados remotos

| Estado | Quando ocorre | O que mostrar |
|--------|---------------|---------------|
| Loading | Aguardando resposta da API | Skeleton ou spinner contextual |
| Sucesso com dados | Resposta retornou com conteúdo | Estado principal |
| Sucesso sem dados | Resposta retornou vazia | Empty state com orientação |
| Erro de rede | Sem conexão ou timeout | Mensagem + ação de retry |
| Erro de servidor | API retornou erro 5xx | Mensagem + alternativa |
| Erro de autorização | Usuário sem permissão | Mensagem contextual + CTA |

### Formulários e inputs

| Estado | Quando ocorre |
|--------|---------------|
| Default / Em branco | Campo não interagido |
| Focused | Campo em edição |
| Preenchido / Válido | Input com valor válido |
| Inválido / Erro | Validação falhou |
| Desabilitado | Campo não editável |

### Ações e CTAs

| Estado | Quando ocorre |
|--------|---------------|
| Default | Pronto para interação |
| Loading | Aguardando resultado da ação |
| Sucesso | Ação completou com êxito |
| Erro | Ação falhou |
| Desabilitado | Ação não disponível |

## Documentando um Estado

```
ESTADO: [Nome]
GATILHO: [O que causa este estado]
DURAÇÃO: [Permanente / Temporário / Até interação do usuário]
COMPONENTES AFETADOS: [O que muda visualmente]
AÇÃO DISPONÍVEL: [O que o usuário pode fazer neste estado]
TRANSIÇÃO PARA: [Qual estado vem depois e por quê]
```

## Nomenclatura de Estados

- `default` / `idle`
- `loading` / `skeleton`
- `success` / `fulfilled`
- `error` / `failed`
- `empty`
- `disabled`
- `readonly`
