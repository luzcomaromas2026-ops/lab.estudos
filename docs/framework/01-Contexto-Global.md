# Fase 01 — Contexto Global

> **Documento mestre do GPS.** Deve ser lido sempre antes de qualquer decisão de fase, arquitetura ou implementação.

## 1. Por que essa fase existe?

O Contexto Global é a fonte única de verdade sobre o projeto: visão, restrições, stakeholders, critérios de sucesso e o estado atual do GPS. Sem ele, cada conversa reinicia do zero e as fases posteriores divergem. Tudo o que for decisão permanente ou restrição dura deve viver (ou ser referenciado) aqui.

## 2. Respostas às Perguntas Críticas

### Qual é a visão do projeto em uma frase?

> **Laboratório de Simbologia** — um app mobile que funciona como Obsidian + Wikipedia pessoal para símbolos, integrando Biblioteca, Grimórios, Fichas de Pesquisa e um Mapa Visual de Conexões entre símbolos.

### Quais objetivos mensuráveis definem sucesso?

1. **Tempo:** Pesquisadores economizam 5-10 horas/semana em pesquisa
2. **Descoberta:** Mapa de conexões revela 3+ relações novas por símbolo
3. **Adoção:** 50 early users ativos na Fase 06 (comunidades de tarô/simbologia)
4. **Retenção:** 70%+ mantêm uso após 3 meses
5. **Satisfação:** NPS > 60 em Q1 2027
6. **Viabilidade:** Cria base para v2 (comunidade, IA, exportação)

### Quem são os stakeholders e qual o papel de cada um?

| Stakeholder | Papel | Canal |
|---|---|---|
| Daany (você) | **Lead User + Decisor** — define produto, testa, aprova | Daily |
| Designer (UI/UX) | **Executor** — interfaces, prototipagem, design system | Sprints |
| Tech Lead (Full-Stack) | **Arquiteto** — tech stack, mobile, banco, API | PR reviews |
| Community (Tarô/Simbologia) | **Early Users** — feedback, validação de features | Discord/comunidades |
| Legal/Compliance | **Bloqueador potencial** — LGPD, dados pessoais | Conforme necessário |

### Quais restrições são inegociáveis?

| Restrição | Tipo | Impacto |
|---|---|---|
| MVP em 16 semanas | **Prazo** | Fase 05 começa 2026-11-05 (GATE Fase 04 até 2026-10-15) |
| Serverless/Free tier | **Orçamento** | Pessoal — sem investimento inicial grande |
| App Mobile-first | **Funcional** | React Native ou Flutter (decisão Fase 04) |
| LGPD compliance | **Compliance** | Criptografia de dados em repouso + em trânsito |
| Open Knowledge | **Filosofia** | Possibilidade de export/backup (não é lock-in) |

### O que já foi descartado e por quê?

- ❌ **Comunidade social** → v2; MVP = conhecimento pessoal
- ❌ **IA generativa** → Complexidade alta, hypotese não validada para v1
- ❌ **E-commerce/Marketplace** → Fora de escopo
- ❌ **Desktop app nativa** → Mobile-first, web como secondary
- ❌ **Múltiplas linguagens (v1)** → Português Brasil apenas

### Onde estão os documentos das demais fases?

| Fase | Documento | Status |
|---|---|---|
| 00 Descoberta | [`docs/framework/00-Descoberta.md`](./00-Descoberta.md) | ✅ Completo |
| 01 Contexto Global | [`docs/framework/01-Contexto-Global.md`](./01-Contexto-Global.md) | 🔄 **EM PROGRESSO** |
| 02 Estrutura Documental | [`docs/framework/02-Estrutura-Documental.md`](./02-Estrutura-Documental.md) | ⏳ Planejado Fase 02 |
| 03 Descoberta do Produto | [`docs/framework/03-Descoberta-do-Produto.md`](./03-Descoberta-do-Produto.md) | ⏳ Planejado Fase 03 |
| 04 Arquitetura | [`docs/framework/04-Arquitetura.md`](./04-Arquitetura.md) | ⏳ Planejado Fase 04 (GATE) |
| 05 Implementação | [`docs/framework/05-Implementacao.md`](./05-Implementacao.md) | ⏳ Planejado Fase 05 |
| 06 Evolução | [`docs/framework/06-Evolucao.md`](./06-Evolucao.md) | ⏳ Planejado Fase 06 |

### Quais riscos abertos ainda não têm mitigação?

| Risco | Severidade | Mitigação | Owner |
|---|---|---|---|
| Visualização de grafo (mapa) é complexa | 🔴 Alta | Prototipagem Fase 03, usar lib pronta (D3/Cytoscape) | Tech Lead |
| Comunidade de simbologia não adota | 🟡 Média | Validar na Fase 03 com early adopters | Daany |
| LGPD compliance inadequado | 🔴 Alta | Audit externo semana 8, Legal review Fase 04 | Compliance |
| Você não tem tempo de manutenção | 🟡 Média | Planejar roadmap realista, comunidade ajuda | Daany |
| GraphQL tem overhead em mobile | 🟡 Média | Performance testing Fase 04, considerar REST | Tech Lead |

## 3. O GPS da Fase

1. ✅ Consolidar a saída da Descoberta (00) em visão e objetivos.
2. ✅ Listar stakeholders com papéis e canais de decisão.
3. ✅ Registrar restrições duras e premissas explícitas.
4. ✅ Definir critérios de sucesso e métricas iniciais.
5. ✅ Manter um quadro de status do GPS (fase atual + aprovações).
6. ✅ Linkar os documentos das fases 02–06 e indicar o que está vigente.
7. ⏳ Atualizar este arquivo a cada mudança material de escopo, restrição ou aprovação.

### Status do GPS (MESTRE — atualizar sempre)

| Fase | Status | Aprovado por | Data |
|------|--------|--------------|------|
| 00 Descoberta | ✅ Completo | Daany | 2026-07-24 |
| 01 Contexto Global | 🔄 Em Progresso | — | 2026-07-25 |
| 02 Estrutura Documental | ⏳ Planejado | — | 2026-08-08 |
| 03 Descoberta do Produto | ⏳ Planejado | — | 2026-08-22 |
| 04 Arquitetura | ⏳ Planejado (GATE) | — | 2026-10-15 |
| 05 Implementação | ⏳ Bloqueado (aguarda Fase 04) | — | 2026-11-05 |
| 06 Evolução | ⏳ Futuro | — | 2027-02-05 |

**Mestre atualizado em:** 2026-07-25 00:30

## 4. Controle de Qualidade/Checklist

- [x] Visão do projeto escrita e revisada
- [x] Objetivos e critérios de sucesso definidos
- [x] Stakeholders e papéis mapeados
- [x] Restrições e premissas documentadas
- [x] Tabela de status do GPS preenchida e atualizada
- [x] Links para as demais fases presentes e válidos
- [x] Decisões descartadas registradas (para não reabrir sem motivo)
- [ ] Documento marcado como mestre e referenciado nas regras do agente (`.cursorrules`) — **PRÓXIMO PASSO**
 
## Framework de Inicialização de Projetos (metodologia)

Este repositório adota o \"Framework de Inicialização de Projetos\" — uma metodologia em desenvolvimento para:

- Estruturar qualquer projeto de software desde a ideia até a implementação.
- Definir fases claras de trabalho (descoberta, contexto, arquitetura, desenvolvimento etc.).
- Usar documentação como base para orientar o desenvolvimento.
- Trabalhar em conjunto com IAs (Claude, Cursor e outras) de forma organizada e consistente.
- Refinar o método continuamente a partir da experiência em projetos reais.

O \"Framework de Inicialização de Projetos\" é o método: em vez de resolver um problema isolado, este projeto cria um processo reutilizável que poderá ser aplicado a projetos futuros.

Esta seção serve como declaração de intenção e fonte de verdade metodológica; qualquer alteração relevante do método deve ser registrada aqui e aprovada conforme as regras do GPS.
