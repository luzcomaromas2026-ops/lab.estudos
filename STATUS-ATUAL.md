# 📖 Status do Projeto: Laboratório de Simbologia

**Última atualização:** 25/07/2026 | **Fase:** 01 em Progresso

---

## ✅ O que foi completado

### Fase 00 — Descoberta ✅ COMPLETO
- [x] Problema definido e validado
- [x] Público-alvo identificado (pesquisadores, curiosos, estudiosos)
- [x] Evidências coletadas (visão clara, comunidades, precedentes)
- [x] Hipótese de valor documentada
- [x] Decisão GO registrada (Daany)
- [x] Escopo negativo listado

**Arquivo:** `docs/framework/00-Descoberta.md`

**Resumo:** Pesquisadores em simbologia (você, estudantes, curiosos) gastam 5-10h/semana em pesquisa fragmentada. Solução: app mobile integrado com Biblioteca, Grimórios, Fichas de Pesquisa e **Mapa Visual de Conexões** entre símbolos.

---

### Fase 01 — Contexto Global 🔄 EM PROGRESSO
- [x] Visão consolidada
- [x] Objetivos mensuráveis definidos (5 métricas)
- [x] Stakeholders mapeados (5 pessoas)
- [x] Restrições documentadas (mobile-first, LGPD, 16 semanas)
- [x] Tabela de status do GPS preenchida
- [x] Riscos e mitigações identificados (5 riscos)
- [x] Timeline estabelecida (25/07/2026 → 05/02/2027)
- [ ] Próxima: Fase 02 (2026-08-08)

**Arquivo:** `docs/framework/01-Contexto-Global.md` ⭐ **MESTRE — sempre consultar**

---

## 📋 Artefatos Criados

### Documentação Executiva
✅ **README.md** — Visão completa do projeto + fases + stack
✅ **ROADMAP.md** — Timeline visual (Gantt-like) com milestones
✅ **STATUS-ATUAL.md** — Você está lendo agora!

### Regras do Projeto
✅ **.cursorrules** — Regras para Cursor IDE (mobile, grafo, LGPD)
✅ **.claude/CLAUDE.md** — Instruções para Claude Code (visão, fases, riscos)
✅ **.claude/settings.json** — Setup de permissões

### Framework GPS Completo
```
docs/framework/
├── 00-Descoberta.md ✅ COMPLETO
├── 01-Contexto-Global.md 🔄 EM PROGRESSO (MESTRE)
├── 02-Estrutura-Documental.md ⏳ (2026-08-08)
├── 03-Descoberta-do-Produto.md ⏳ (2026-08-22)
├── 04-Arquitetura.md ⏳ (2026-10-15 ⛔ GATE)
├── 05-Implementacao.md ⏳ (2026-11-05)
└── 06-Evolucao.md ⏳ (2027-02-05)
```

### Templates Adicionais
```
docs/
├── adr/ → Architecture Decision Records (vazio, pronto)
├── templates/
│   ├── MVP-Canvas.md
│   ├── SRS.md
│   └── UX-Journey.md
└── produto/ (para Fase 03)
```

---

## 🎯 A Visão do Projeto

**Laboratório de Simbologia** é um app mobile que funciona como:

### 🏗️ Cinco Componentes Principais

1. **📚 Biblioteca**
   - Fichário de livros, artigos, PDFs
   - Metadados: autor, tema, resumo, conceitos
   - Símbolos encontrados + avaliação pessoal

2. **📜 Grimórios (9 cadernos temáticos)**
   - Tarô, Sonhos, Cores, Animais, Arquétipos
   - Mitologia, Alquimia, Religiões, Psicologia
   - Cada um registra: descobertas, hipóteses, conexões

3. **🔍 Fichas de Pesquisa**
   - Exemplo: Coruja
   - Origem, significados, culturas, mitologias
   - Relações com Tarô, Jung, Alquimia, Astrologia
   - Observações pessoais

4. **🕸️ Mapa de Conexões (CORE!)**
   - Clique em "Lua" → vê conectado a: A Sacerdotisa, Ártemis, Hécate, Yin, Inconsciente, Água, Feminino, Sonhos, Ciclos, Marés
   - Grafo visual interativo
   - Wikipedia pessoal de símbolos

5. **🧪 Diário do Laboratório**
   - Timeline cronológica
   - Registro de descobertas
   - "24/07/2026: Encontrei relação entre serpente da alquimia e Ouroboros..."

---

## 📊 Métricas de Sucesso

| Métrica | Target | Prazo |
|---------|--------|-------|
| Economia de tempo | 5-10h/semana ganhas | 3 meses pós-launch |
| Descoberta | 3+ relações novas/símbolo | MVP |
| Early Users | 50 ativos (comunidades tarô) | Fase 06 |
| Retenção | 70%+ após 3 meses | Fase 06 |
| Satisfação | NPS > 60 | Q1 2027 |

---

## 🏗️ Stack Técnico (A Decidir na Fase 04)

**Hipótese atual:**
- **Mobile:** React Native (JS multiplataforma) OU Flutter (Dart)
- **Backend:** Node.js + Supabase (PostgreSQL + GraphQL)
- **Grafo:** D3.js, Cytoscape.js OU THREE.js
- **Web:** Next.js + React (secundário)
- **Auth:** OAuth2 (Google, GitHub)
- **Compliance:** LGPD — criptografia obrigatória

---

## ⏰ Timeline (16 semanas: 25/07/2026 → 05/02/2027)

```
25/07      08/08      22/08      15/10      05/11      05/02
 |         |          |          |          |          |
 v         v          v          v          v          v
[Fase 01]-[Fase 02]-[Fase 03]-[Fase 04]⛔-[Fase 05]-[Fase 06]
  🔄        ⏳        ⏳        GATE        ⏳        ⏳
  Agora   Docs      Produto   Arquitetura  MVP      Métricas
            Setup   Design     + Aprovação  Dev
```

---

## 🚨 Riscos Identificados e Mitigações

| Risco | Severidade | Mitigação | Owner |
|-------|---|---|---|
| Visualização de grafo é complexa | 🔴 Alta | Prototipagem Fase 03, usar lib pronta | Tech Lead |
| Comunidade não adota app | 🟡 Média | Validar na Fase 03 com early adopters | Daany |
| LGPD compliance inadequado | 🔴 Alta | Audit externo semana 8 | Compliance |
| Você não tem tempo de manutenção | 🟡 Média | Roadmap realista, comunidade ajuda | Daany |
| GraphQL overhead em mobile | 🟡 Média | Performance testing Fase 04 | Tech Lead |

---

## 📞 Stakeholders

| Pessoa | Rol | Decisão |
|--------|-----|---------|
| **Você (Daany)** | Lead User + Decisor | Final |
| Designer | UI/UX + Design System | Interface |
| Tech Lead | Arquitetura + Mobile | Tech |
| Comunidade | Early Users | Feedback |
| Legal | LGPD Guard | Compliance |

---

## 🔐 Inegociáveis

- ✅ **Mobile-first** — App para celular, não desktop
- ✅ **Grafo Visual** — Mapa de conexões é core
- ✅ **LGPD Compliance** — Criptografia obrigatória
- ✅ **Conhecimento Pessoal** — v1 não é rede social
- ✅ **Open Knowledge** — Possibilidade de export

---

## 🚫 Decisões Já Tomadas (NÃO REABRIR)

- ❌ Comunidade social → v2 (MVP = pessoal)
- ❌ IA generativa → Complexidade alta, v2+
- ❌ Desktop-first → Mobile-first obrigatório
- ❌ E-commerce/Marketplace → Fora de escopo
- ❌ Múltiplas línguas v1 → Português Brasil only

---

## 📋 Próximos Passos (Próxima Semana)

### Imediato (Próximos 7 dias)
1. ✅ **Fase 01 finalizada** (você fez!)
2. ⏳ **Socializar Contexto Global** com: Designer, Tech Lead
3. ⏳ **Validar stack móbile:** React Native vs Flutter?
4. ⏳ **Contatar comunidades** de Tarô/Simbologia para feedback

### Fase 02 — Estrutura Documental (2026-08-08)
- Definir convenções de docs
- Setup CI/CD para Markdown
- Organizar ADRs (Architecture Decision Records)

### Fase 03 — Descoberta do Produto (2026-08-22)
- Personas e personas journey
- Feature matrix + priorização
- **Protótipo do Mapa de Conexões** (validar viabilidade)
- Wireframes iniciais

### Fase 04 — Arquitetura (2026-10-15) ⛔ GATE
- Decisões técnicas: React Native? Flutter? Supabase?
- Diagramas de arquitetura
- Plano de segurança LGPD
- **Aprovação obrigatória antes de Fase 05**

### Fase 05 — Implementação (2026-11-05)
- Desenvolvimento do MVP
- Integração de componentes
- Testes

### Fase 06 — Evolução (2027-02-05)
- Feedback de early users
- Métricas (NPS, DAU, retention)
- Roadmap v2

---

## 📚 Como Usar Este Projeto

1. **Consulte SEMPRE:** `docs/framework/01-Contexto-Global.md` (MESTRE)
2. **Regras:** `.cursorrules` + `.claude/CLAUDE.md`
3. **Templates:** `docs/templates/` (MVP Canvas, SRS, UX Journey)
4. **ADRs:** `docs/adr/` (para grandes decisões)

---

**STATUS GERAL:** ✅ Fases 00 e 01 COMPLETAS
**PRÓXIMA AÇÃO:** Socializar com Designer e Tech Lead
**TIMELINE:** 16 semanas até MVP (05/02/2027)

🚀 Projeto alinhado com GPS! Bora codar.
