---
name: heuristic-evaluation
description: >
  Framework completo para avaliação heurística de interfaces, combinando
  as 10 heurísticas de Nielsen com princípios de design de produto
  contemporâneo. Inclui critérios de avaliação e escala de severidade.
---

# Skill: Heuristic Evaluation

## Propósito

Avaliação heurística é uma forma estruturada de encontrar problemas de usabilidade sem precisar de usuários reais. Quando aplicada com rigor, captura a maioria dos problemas antes de qualquer teste.

## As 10 Heurísticas

### H1 — Visibilidade do Status do Sistema
O sistema sempre mantém o usuário informado sobre o que está acontecendo.

**O que verificar:**
- Existe feedback visual para toda ação que leva mais de 1 segundo?
- O usuário sabe em qual etapa está em fluxos de múltiplos passos?
- Uploads, downloads e processamentos têm indicadores de progresso?

### H2 — Correspondência com o Mundo Real
O sistema fala a língua do usuário, com palavras e conceitos familiares ao público-alvo.

**O que verificar:**
- Os termos usados correspondem ao vocabulário do usuário, não do time técnico?
- Metáforas visuais fazem sentido para o contexto do produto?

### H3 — Controle e Liberdade do Usuário
Usuários frequentemente escolhem ações por engano. Saídas claras e desfazimento são essenciais.

**O que verificar:**
- Ações destrutivas têm confirmação?
- É possível desfazer a última ação?
- O usuário consegue sair de qualquer estado sem perder progresso?

### H4 — Consistência e Padrões
Usuários não deveriam ter que adivinhar se diferentes palavras ou ações significam a mesma coisa.

**O que verificar:**
- A mesma ação tem o mesmo nome em toda a interface?
- Componentes similares têm comportamento similar?

### H5 — Prevenção de Erros
Melhor do que boas mensagens de erro é um design que previne o erro de acontecer.

**O que verificar:**
- Formulários validam em tempo real antes do submit?
- Ações perigosas são separadas das ações comuns?

### H6 — Reconhecimento em vez de Memorização
Minimize a carga cognitiva tornando objetos, ações e opções visíveis.

**O que verificar:**
- O contexto da etapa atual está visível sem precisar navegar para trás?
- O usuário consegue completar o fluxo sem lembrar de informações de telas anteriores?

### H7 — Flexibilidade e Eficiência de Uso
Atalhos permitem que usuários experientes completem tarefas mais rapidamente.

**O que verificar:**
- Usuários recorrentes têm formas mais rápidas de completar ações frequentes?

### H8 — Design Estético e Minimalista
Interfaces não devem conter informações irrelevantes.

**O que verificar:**
- Toda informação exibida é necessária para o usuário tomar a próxima decisão?
- A hierarquia visual comunica claramente o que é primário, secundário e terciário?

### H9 — Ajuda para Reconhecer, Diagnosticar e Recuperar de Erros
Mensagens de erro devem indicar o problema e sugerir uma solução.

**O que verificar:**
- Mensagens de erro identificam o problema específico (não apenas "deu errado")?
- A mensagem sugere o próximo passo do usuário?

### H10 — Ajuda e Documentação
Embora o melhor sistema não precise de documentação, pode ser necessário fornecer ajuda.

**O que verificar:**
- Funcionalidades complexas têm tooltips ou explicações contextuais?
- A ajuda é contextual (sobre o que está na tela) e não genérica?

## Princípios Complementares Contemporâneos

### P1 — Mobile First e Touch-Friendly
- Targets de toque mínimos de 44x44pt
- Ações críticas alcançáveis com o polegar

### P2 — Performance Percebida
- Skeleton screens em vez de spinners genéricos
- Feedback otimista onde aplicável

### P3 — Acessibilidade Estrutural
- Hierarquia comunicada por estrutura, não só por cor
- Contraste mínimo de 4.5:1 para texto normal

## Escala de Severidade

| Nível | Descrição |
|-------|-----------|
| **0** | Não é um problema de usabilidade |
| **1** | Cosmético — só corrigir se houver tempo |
| **2** | Menor — baixa prioridade |
| **3** | Maior — importante corrigir |
| **4** | Catastrófico — deve ser corrigido antes do lançamento |
