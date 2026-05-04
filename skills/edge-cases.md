---
name: edge-cases
description: >
  Checklist para identificar cenários além do happy path que precisam de
  tratamento de design. Cobre edge cases universais e específicos de
  fluxos financeiros, de aprovação e B2B da Loft.
---

# Skill: Edge Cases

## Propósito

Edge cases são os casos que "nunca acontecem" — até acontecerem em produção. Esta skill força uma revisão sistemática antes da implementação, quando corrigir ainda é barato.

**Distinção com `user-flows`:**
- **Fluxo alternativo** (user-flows) → o usuário faz uma escolha diferente, comportamento válido
- **Edge case** (esta skill) → condição técnica, de timing ou de volume que causa comportamento inesperado

---

## Checklist Universal

### Dados e conteúdo

- [ ] O que acontece com texto muito longo? (nome de imóvel, razão social, endereço)
- [ ] E com campos obrigatórios vazios no submit?
- [ ] E com números extremos? (0 itens, 1 item, 9.999 itens)
- [ ] E com datas no passado, futuras ou inválidas?
- [ ] E com valores monetários zerados ou extremamente altos?
- [ ] E com caracteres especiais? (acentos, ç, ñ, emojis em campos de texto)

### Conectividade e performance

- [ ] O que acontece sem conexão de internet?
- [ ] E com conexão lenta — imagens, documentos e PDFs não carregando?
- [ ] E se a API demorar mais de 10 segundos?
- [ ] E se o usuário fechar e reabrir o app no meio de um processo crítico?
- [ ] E se perder a sessão durante uma ação irreversível?

### Permissões e estados de conta

- [ ] O que o usuário vê sem permissão para esta ação?
- [ ] E se a conta estiver suspensa ou em estado especial?
- [ ] E se o recurso que está sendo acessado não existe mais (foi deletado por outro usuário)?
- [ ] E se um link direto for acessado por alguém sem o contexto necessário?

### Multi-dispositivo

- [ ] O usuário iniciou no desktop e precisa continuar no mobile — o estado foi salvo?
- [ ] O fluxo funciona no menor breakpoint suportado?
- [ ] E com zoom de acessibilidade em 200%?
- [ ] E se o usuário apertar "voltar" do navegador no meio de um fluxo com múltiplos passos?

### Concorrência e timing

- [ ] O que acontece se o usuário clicar duas vezes rapidamente no CTA (duplo envio)?
- [ ] E se dois usuários acessarem e modificarem o mesmo recurso simultaneamente?
- [ ] E se uma ação em segundo plano alterar o estado enquanto o usuário está na tela?

---

## Edge Cases Específicos da Loft

### Upload de documentos

Crítico em fluxos de fiança, contratos e análise de crédito.

- [ ] Arquivo excede o limite de tamanho — qual é o limite? A mensagem diz o limite?
- [ ] Formato de arquivo não suportado — quais formatos são aceitos? A mensagem diz?
- [ ] Upload corrompido ou ilegível — o sistema detecta e avisa?
- [ ] Documento expirado (ex: RG antigo, comprovante de renda desatualizado) — o sistema valida?
- [ ] Usuário faz upload do arquivo errado — pode substituir sem perder o que enviou antes?
- [ ] Upload interrompido no meio — o que foi salvo? O usuário precisa recomeçar?

### Fluxos financeiros e cálculos

- [ ] Valor de aluguel zerado ou negativo — o sistema aceita? Bloqueia?
- [ ] Percentual de garantia que resulta em valor centavos — como arredonda?
- [ ] Múltiplas cobranças no mesmo período — o sistema detecta duplicidade?
- [ ] Moeda ou locale diferente em campos monetários — o produto opera só em R$?
- [ ] Mudança de valor durante análise — o que acontece se o proprietário altera o aluguel enquanto a fiança está em análise?

### Fluxos de aprovação com prazo

- [ ] Proposta expira enquanto o gestor está preenchendo o formulário de análise — o que acontece ao submeter?
- [ ] Prazo vence durante o fim de semana ou feriado — o sistema considera?
- [ ] Aprovador não age dentro do prazo — quem é notificado? O que acontece automaticamente?
- [ ] Aprovação feita por alguém que perdeu a permissão após iniciar a análise — é aceita?

### Multi-perfil B2B (gestor, corretor, admin)

- [ ] Corretor inicia uma proposta e o gestor da imobiliária desativa a conta do corretor antes da conclusão — o que acontece?
- [ ] Dois gestores aprovam a mesma proposta simultaneamente — qual aprovação prevalece?
- [ ] Gestor tenta aprovar proposta criada por corretor que saiu da imobiliária — o acesso existe?
- [ ] Imobiliária muda de plano enquanto corretor está no meio de um fluxo que usa feature do plano anterior — o que acontece?
- [ ] Usuário com múltiplos vínculos (gestor em imobiliária A e corretor em imobiliária B) — o contexto atual está claro?

### LGPD e dados sensíveis

- [ ] Usuário solicita exclusão de conta com processos ativos — o que bloqueia a exclusão?
- [ ] Dados pessoais exibidos em URL ou em logs — verificar exposição acidental de PII?
- [ ] Sessão expirada durante preenchimento de dados sensíveis — os dados foram descartados?

---

## Priorizando Edge Cases

| Nível | Critério | Ação |
|-------|----------|------|
| **Crítico** | Perda de dados, bloqueio total ou risco legal | Design obrigatório antes do dev |
| **Importante** | Experiência significativamente degradada | Design antes do lançamento |
| **Bom ter** | Melhoria incremental, baixo impacto | Registrar para iteração futura |
| **Irrelevante** | Improvável e baixo impacto | Documentar como descartado — não ignorar silenciosamente |

---

## Documentando um Edge Case

```
EDGE CASE: [Descrição objetiva da situação]
PROBABILIDADE: [Alta / Média / Baixa]
IMPACTO: [Crítico / Importante / Baixo]
TRATAMENTO PROPOSTO: [Como o design responde]
PRIORIDADE: [Crítico / Importante / Bom ter / Irrelevante]
```
