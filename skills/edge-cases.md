---
name: edge-cases
description: >
  Checklist e framework para identificar casos extremos, condições
  incomuns e cenários de falha que precisam de tratamento de design.
  Previne retrabalho ao encontrar lacunas antes da implementação.
---

# Skill: Edge Case Detection

## Propósito

Edge cases são os casos que "nunca acontecem" — até acontecerem. Esta skill força uma revisão sistemática dos cenários além do happy path antes que o dev precise perguntar.

## Checklist Universal de Edge Cases

### Dados e conteúdo

- [ ] O que acontece com campos de texto muito longos?
- [ ] E com campos vazios que deveriam ter conteúdo?
- [ ] E com números extremos? (0 itens, 1 item, 9999 itens)
- [ ] E com datas inválidas ou no passado?
- [ ] E com caracteres especiais, emojis, ou RTL?
- [ ] E com valores monetários muito altos ou zerados?

### Conectividade e performance

- [ ] O que acontece sem conexão de internet?
- [ ] E com conexão lenta (imagens não carregando)?
- [ ] E se a API demorar mais de 10 segundos?
- [ ] E se o usuário fechar e reabrir o app no meio de um processo?
- [ ] E se perder a sessão durante uma ação crítica?

### Permissões e estados de conta

- [ ] O que o usuário vê se não tiver permissão para esta ação?
- [ ] E se a conta estiver suspensa ou em estado especial?
- [ ] E se o usuário tentar acessar um recurso que não existe mais?
- [ ] E se o link for compartilhado com alguém sem acesso?

### Multi-dispositivo e contexto

- [ ] O fluxo funciona no menor breakpoint suportado?
- [ ] E em orientação landscape no mobile?
- [ ] E com zoom de acessibilidade aumentado para 200%?
- [ ] E se o usuário usar o botão "voltar" no meio do fluxo?

### Concorrência e timing

- [ ] O que acontece se o usuário clicar duas vezes rapidamente no CTA?
- [ ] E se dois usuários editarem o mesmo recurso simultaneamente?

## Priorizando Edge Cases

| Nível | Critério | Ação |
|-------|----------|------|
| **Crítico** | Pode causar perda de dados ou bloqueio total | Design obrigatório antes do dev |
| **Importante** | Experiência significativamente degradada | Design antes do lançamento |
| **Bom ter** | Melhoria incremental | Registrar para iteração futura |
| **Irrelevante** | Improvável e baixo impacto | Documentar como descartado |

## Documentando Edge Cases

```
EDGE CASE: [Descrição da situação]
PROBABILIDADE: [Alta / Média / Baixa]
IMPACTO: [Crítico / Importante / Baixo]
TRATAMENTO PROPOSTO: [Como o design responde]
PRIORIDADE: [Implementar agora / Iteração futura / Descartado]
```
