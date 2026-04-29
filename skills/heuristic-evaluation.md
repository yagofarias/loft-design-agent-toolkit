---
name: heuristic-evaluation
description: >
  Framework completo para avaliação heurística de interfaces, combinando
  as 10 heurísticas de Nielsen, princípios de design contemporâneo e
  avaliação aprofundada de acessibilidade (WCAG 2.1). Inclui critérios
  de avaliação, escala de severidade e checklist por tipo de componente.
---

# Skill: Heuristic Evaluation

## Propósito

Avaliação heurística é uma forma estruturada de encontrar problemas de usabilidade sem precisar de usuários reais. Quando aplicada com rigor, captura a maioria dos problemas antes de qualquer teste.

---

## As 10 Heurísticas de Nielsen

### H1 — Visibilidade do Status do Sistema
O sistema sempre mantém o usuário informado sobre o que está acontecendo.

**O que verificar:**
- Existe feedback visual para toda ação que leva mais de 1 segundo?
- O usuário sabe em qual etapa está em fluxos de múltiplos passos?
- Uploads, downloads e processamentos têm indicadores de progresso?
- Ações de background são comunicadas quando concluídas?

**Sinais de problema:** Usuário clica, nada aparece. Processamento sem indicador. Progresso invisível.

---

### H2 — Correspondência com o Mundo Real
O sistema fala a língua do usuário, com palavras e conceitos familiares ao público-alvo.

**O que verificar:**
- Os termos usados correspondem ao vocabulário do usuário, não do time técnico?
- Metáforas visuais fazem sentido para o contexto do produto?
- A ordenação lógica dos conteúdos corresponde à ordem mental do usuário?

**Sinais de problema:** Jargão técnico exposto. Metáforas sem contexto. Ordem que confunde.

---

### H3 — Controle e Liberdade do Usuário
Usuários frequentemente escolhem ações por engano. Saídas claras e desfazimento são essenciais.

**O que verificar:**
- Ações destrutivas têm confirmação?
- É possível desfazer a última ação?
- O usuário consegue sair de qualquer estado sem perder progresso?
- Existe forma de cancelar processos em andamento?

**Sinais de problema:** Deleção sem confirmação. Sem botão de cancelar. Sem undo. Sem "X" em modais.

---

### H4 — Consistência e Padrões
Usuários não deveriam ter que adivinhar se diferentes palavras ou ações significam a mesma coisa.

**O que verificar:**
- A mesma ação tem o mesmo nome em toda a interface?
- Componentes similares têm comportamento similar?
- Padrões do sistema operacional ou plataforma são respeitados?
- A hierarquia visual é consistente entre telas similares?

**Sinais de problema:** "Salvar" em uma tela, "Confirmar" em outra para a mesma ação.

---

### H5 — Prevenção de Erros
Melhor do que boas mensagens de erro é um design que previne o erro de acontecer.

**O que verificar:**
- Formulários validam em tempo real antes do submit?
- Ações perigosas são separadas das ações comuns?
- Inputs têm máscaras, formatos ou exemplos que guiam o preenchimento?
- O sistema confirma antes de ações irreversíveis?

**Sinais de problema:** Erro só aparece após submit. Botão de deletar ao lado de salvar.

---

### H6 — Reconhecimento em vez de Memorização
Minimize a carga cognitiva tornando objetos, ações e opções visíveis.

**O que verificar:**
- O contexto da etapa atual está visível sem precisar navegar para trás?
- Opções relevantes são apresentadas visivelmente em vez de escondidas em menus?
- O usuário consegue completar o fluxo sem lembrar de informações de telas anteriores?

**Sinais de problema:** Usuário precisa memorizar código de uma tela e digitar em outra.

---

### H7 — Flexibilidade e Eficiência de Uso
Atalhos permitem que usuários experientes completem tarefas mais rapidamente.

**O que verificar:**
- Usuários recorrentes têm formas mais rápidas de completar ações frequentes?
- Existem atalhos de teclado para ações comuns em desktop?
- Personalizações permitem adaptar o fluxo ao uso individual?

**Sinais de problema:** Todo usuário passa pelo mesmo fluxo longo independente de frequência.

---

### H8 — Design Estético e Minimalista
Interfaces não devem conter informações irrelevantes.

**O que verificar:**
- Toda informação exibida é necessária para o usuário tomar a próxima decisão?
- A hierarquia visual comunica claramente o que é primário, secundário e terciário?
- Existe conteúdo adicionado "por precaução" mas raramente usado?

**Sinais de problema:** Múltiplas CTAs de igual peso. Visual poluído.

---

### H9 — Ajuda para Reconhecer, Diagnosticar e Recuperar de Erros
Mensagens de erro devem indicar o problema e sugerir uma solução.

**O que verificar:**
- Mensagens de erro identificam o problema específico (não apenas "deu errado")?
- A mensagem sugere o próximo passo do usuário?
- Erros de validação aparecem próximos ao campo causador?

**Sinais de problema:** "Erro 500". "Tente novamente mais tarde". Mensagem genérica sem orientação.

---

### H10 — Ajuda e Documentação
Embora o melhor sistema não precise de documentação, pode ser necessário fornecer ajuda contextual.

**O que verificar:**
- Funcionalidades complexas têm tooltips ou explicações contextuais?
- A ajuda é contextual (sobre o que está na tela) e não genérica?
- Existe forma de o usuário pedir ajuda sem sair do fluxo?

---

## Princípios Complementares Contemporâneos

### P1 — Mobile First e Touch-Friendly
- Targets de toque mínimos de 44x44pt (iOS) / 48x48dp (Android)
- Ações críticas alcançáveis com o polegar em uma mão
- Conteúdo não depende de hover para ser compreendido
- Gestos padrão da plataforma são respeitados (swipe, pinch, long press)

### P2 — Performance Percebida
- Skeleton screens em vez de spinners genéricos
- Carregamento progressivo de conteúdo — o mais importante aparece primeiro
- Feedback otimista onde a ação parece completar antes da API confirmar
- Imagens com lazy loading para não bloquear o conteúdo principal

### P3 — Consistência de Interação
- Padrões de navegação consistentes em toda a jornada
- Estados de hover, focus e active definidos para todos os elementos interativos
- Feedback háptico documentado para mobile onde aplicável

---

## Avaliação de Acessibilidade (WCAG 2.1)

A acessibilidade não é uma camada extra — é parte da avaliação heurística. Avalie em quatro dimensões:

### A1 — Perceptível (o conteúdo pode ser percebido por todos os sentidos)

**Contraste de cor:**
- [ ] Texto normal: contraste mínimo 4.5:1 contra o fundo
- [ ] Texto grande (18pt+ ou 14pt bold): contraste mínimo 3:1
- [ ] Elementos de UI e gráficos informativos: contraste mínimo 3:1
- [ ] Informação não é transmitida apenas por cor (ex: erro vermelho sem ícone ou texto)

**Conteúdo não-textual:**
- [ ] Imagens funcionais têm texto alternativo descritivo
- [ ] Imagens decorativas têm alt vazio (`alt=""`) para não poluir leitores de tela
- [ ] Ícones sem label têm aria-label ou tooltip
- [ ] Gráficos e charts têm descrição textual equivalente

**Texto:**
- [ ] Tamanho mínimo de fonte 16px para corpo de texto
- [ ] Espaçamento entre linhas de pelo menos 1.5x o tamanho da fonte
- [ ] Texto não está embarcado em imagem (inacessível para leitores de tela)

### A2 — Operável (a interface pode ser operada por qualquer pessoa)

**Navegação por teclado:**
- [ ] Todos os elementos interativos são acessíveis via Tab
- [ ] Ordem de foco é lógica e segue a hierarquia visual
- [ ] Foco visível está claramente indicado (outline, não apenas cor)
- [ ] Não há armadilhas de foco (modais que prendem o cursor sem saída via teclado)

**Tempo e movimento:**
- [ ] Timeouts têm aviso e opção de extensão
- [ ] Animações podem ser pausadas ou desabilitadas
- [ ] Conteúdo que pisca não excede 3 flashes por segundo (risco de convulsão)
- [ ] Auto-play de vídeo/áudio tem controle de pausa visível

**Área de toque e clique:**
- [ ] Área clicável mínima de 44x44px para alvos importantes
- [ ] Elementos clicáveis têm espaçamento suficiente entre si (mínimo 8px)

### A3 — Compreensível (a informação e operação são compreensíveis)

**Linguagem e leitura:**
- [ ] Linguagem da página está declarada no HTML (`lang="pt-BR"`)
- [ ] Abreviações e siglas têm expansão na primeira ocorrência
- [ ] Instruções não dependem apenas de características sensoriais ("clique no botão verde à direita")

**Previsibilidade:**
- [ ] Foco em um elemento não dispara mudança de contexto inesperada
- [ ] Componentes com mesmo nome têm mesmo comportamento em todo o produto
- [ ] Mudanças de contexto importantes são anunciadas para tecnologias assistivas

**Suporte a entrada:**
- [ ] Labels de formulário são persistentes (não desaparecem ao focar)
- [ ] Campos de erro identificam o campo com problema e explicam como corrigir
- [ ] Campos não exigem formato específico sem indicação prévia (ex: CPF com ou sem máscara)

### A4 — Robusto (funciona com tecnologias assistivas)

**Markup semântico:**
- [ ] Hierarquia de headings é lógica (h1 → h2 → h3, sem pular níveis)
- [ ] Listas são marcadas como `<ul>`, `<ol>` ou `<dl>` (não divs com bullets visuais)
- [ ] Tabelas têm `<th>` com escopo correto para cabeçalhos de linha e coluna
- [ ] Botões são `<button>` e links são `<a>` (não divs clicáveis)

**ARIA (quando HTML semântico não é suficiente):**
- [ ] Componentes customizados têm roles ARIA corretos (ex: `role="dialog"` para modais)
- [ ] Estados dinâmicos são comunicados (ex: `aria-expanded`, `aria-selected`, `aria-live`)
- [ ] ARIA não é usado para compensar HTML não semântico — corrija o HTML primeiro
- [ ] Labels e descriptions de formulário estão associados via `for`/`id` ou `aria-labelledby`

---

## Escala de Severidade

| Nível | Descrição | Ação |
|-------|-----------|------|
| **0** | Não é um problema de usabilidade | Ignorar |
| **1** | Cosmético — afeta a estética mas não o uso | Corrigir se houver tempo |
| **2** | Menor — causa leve frustração mas usuário consegue prosseguir | Baixa prioridade |
| **3** | Maior — impede ou dificulta significativamente o uso | Corrigir antes do lançamento |
| **4** | Catastrófico — bloqueia o usuário ou causa erro grave | Corrigir imediatamente |

> Problemas de acessibilidade que bloqueiam usuários com deficiência são automaticamente **nível 4**, independentemente de quantos usuários afetam.

---

## Como Reportar um Problema

```
PROBLEMA: [Descrição específica]
HEURÍSTICA / WCAG: [Qual princípio foi violado]
SEVERIDADE: [0-4]
TELA / MOMENTO: [Onde ocorre]
EVIDÊNCIA: [O que foi observado]
IMPACTO: [Quem é afetado e como]
SUGESTÃO: [Direção de solução]
```
