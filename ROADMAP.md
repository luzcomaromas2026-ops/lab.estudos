# 🚀 Roadmap GPS: Automação de Tarefas Slack

```
2026-07-24                    2026-10-23                   2027-01-23
   |                              |                            |
   v                              v                            v
┌─────────────────────────────────────────────────────────────────────────┐
│                                                                           │
│  Fase 00   Fase 01   Fase 02    Fase 03    FASE 04 ⛔    Fase 05  Fase 06 │
│ Descoberta Context. Estrutura  Produto   Arquitetura   Impl.   Evolução │
│   ✅       🔄        ⏳         ⏳         ⏳            ⏳       ⏳       │
│   |        |         |          |         |             |       |       │
│   |--------+         |          |         |             |       |       │
│            |---------|          |         |             |       |       │
│                      |----------|         |             |       |       │
│                                  |--------|             |       |       │
│                                           |-------------|       |       │
│                                                        |---------|       │
│                                                                  |-------│
│                                                                          │
│  12 weeks to MVP  ────────────────────────────────────────────────────┤
│                                                                           │
│  Hoje → 2026-08-07 → 2026-08-21 → 2026-10-01 → 2026-10-23 → 2027-01-23 │
│        (Fase 02)    (Fase 03)    (Fase 04)    (MVP/05)     (Métricas)  │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## 📅 Timeline Detalhada

### **Fase 00 — Descoberta** ✅
**Status:** Completo  
**Prazo:** 2026-07-24 (HOJE)  
**Owner:** Daany  

**Saídas:**
- ✅ Problema definido e validado
- ✅ Visão consolidada
- ✅ Decisão GO registrada

**Arquivo:** [`docs/framework/00-Descoberta.md`](docs/framework/00-Descoberta.md)

---

### **Fase 01 — Contexto Global** 🔄
**Status:** Em Progresso  
**Prazo:** 2026-07-31 (próxima semana)  
**Owner:** Daany  

**Atividades:**
- Compartilhar com Tech Lead + Pioneers + Legal
- Validar stack técnico
- Validar LGPD compliance
- Validar timeline com team

**Saídas:**
- Contexto Global aprovado
- Stakeholder alignment
- Go/no-go final

**Arquivo:** [`docs/framework/01-Contexto-Global.md`](docs/framework/01-Contexto-Global.md) (MESTRE)

---

### **Fase 02 — Estrutura Documental** ⏳
**Status:** Planejado  
**Prazo:** 2026-08-07 (2 semanas)  
**Owner:** Daany + Design  
**Bloqueador:** Fase 01 completa

**Atividades:**
- Definir convenções de documentação
- Setup CI/CD para docs (linting)
- Organizar templates ADR
- Setup de versionamento de docs

**Saídas:**
- Convenções documentadas
- CI/CD ativo
- ADR template pronto

**Arquivo:** [`docs/framework/02-Estrutura-Documental.md`](docs/framework/02-Estrutura-Documental.md)

---

### **Fase 03 — Descoberta do Produto** ⏳
**Status:** Planejado  
**Prazo:** 2026-08-21 (3 semanas)  
**Owner:** Daany + Design + Pioneers  
**Bloqueador:** Fase 02 completa

**Atividades:**
- Personas e personas journey
- Feature matrix + priorização
- Wireframes iniciais
- Validação com 2 Dev Pioneers
- Edge cases e negative scenarios

**Saídas:**
- Personas validadas
- Feature list com prioridades
- Wireframes aprovados
- Scenarios documentados

**Arquivo:** [`docs/framework/03-Descoberta-do-Produto.md`](docs/framework/03-Descoberta-do-Produto.md)

---

### **Fase 04 — Arquitetura** ⛔ **GATE INEGOCIÁVEL**
**Status:** Planejado  
**Prazo:** 2026-10-01 (8 semanas)  
**Owner:** Tech Lead + Daany  
**Bloqueador:** Fase 03 completa

**Atividades:**
- Decisões técnicas (Next.js, Supabase, etc.)
- Diagrama de arquitetura
- Plano de segurança e LGPD
- Plano de deployment (Vercel)
- Plano de testes

**Saídas:**
- ADRs (Architecture Decision Records)
- Arquitetura documentada
- Compliance plan aprovado por Legal
- **APROVAÇÃO de Daany**

**Arquivo:** [`docs/framework/04-Arquitetura.md`](docs/framework/04-Arquitetura.md)

**⛔ GATE:** Fase 05 SÓ começa com Fase 04 aprovada.

---

### **Fase 05 — Implementação** ⏳
**Status:** Bloqueado (aguarda Fase 04)  
**Prazo:** 2026-10-23 (6 semanas)  
**Owner:** Eng Team + Design  
**Bloqueador:** Fase 04 APROVADA

**Atividades (sprints):**
- Sprint 1-2: Frontend base (Next.js + Tailwind)
- Sprint 2-3: Backend base (Supabase + auth)
- Sprint 3-4: Integração Slack
- Sprint 4-5: Testes + refinement
- Sprint 5-6: Deploy + MVP

**Saídas:**
- MVP lançado em produção
- Integração Slack funcional
- Testes passando
- Documentação de API

**Arquivo:** [`docs/framework/05-Implementacao.md`](docs/framework/05-Implementacao.md)

---

### **Fase 06 — Evolução** ⏳
**Status:** Futuro  
**Prazo:** 2027-01-23 (12 semanas)  
**Owner:** Daany + Eng Team + Data Science  
**Bloqueador:** MVP em produção

**Atividades:**
- Recolher feedback de early users
- Medir NPS, DAU, retention, produtividade
- Identificar top issues/feature requests
- Planning de v2

**Saídas:**
- NPS > 50
- 80% DAU
- Roadmap v2

**Arquivo:** [`docs/framework/06-Evolucao.md`](docs/framework/06-Evolucao.md)

---

## 🎯 Milestones Críticos

| Data | Milestone | Status | Owner |
|------|-----------|--------|-------|
| 2026-07-31 | Fase 01 aprovada | ⏳ | Daany |
| 2026-08-07 | Fase 02 completa | ⏳ | Daany + Design |
| 2026-08-21 | Fase 03 completa | ⏳ | Daany + Pioneers |
| **2026-10-01** | **Fase 04 APROVADA** | **⏳ GATE** | **Tech Lead** |
| 2026-10-23 | **MVP LANÇADO** | ⏳ | Eng Team |
| 2027-01-23 | NPS > 50 medido | ⏳ | Daany |

---

## 📊 Métricas por Fase

### Fase 00: Validação
- ✅ Problema real identificado
- ✅ 3+ entrevistas coletadas
- ✅ Decisão GO/NO-GO

### Fase 01: Alignment
- ✅ Stakeholders mapeados
- ✅ Stack aprovado
- ✅ Timeline realista

### Fase 02: Organização
- ✅ Docs CI/CD setup
- ✅ Convenções definidas
- ✅ Team preparado

### Fase 03: Clareza
- ✅ Personas validadas
- ✅ Features priorizadas
- ✅ Designs aprovados

### Fase 04: Decisões Técnicas (GATE)
- ✅ Arquitetura documentada
- ✅ Compliance aprovado
- ✅ Plano de deployment

### Fase 05: MVP Funcional
- ✅ MVP lançado
- ✅ Integração Slack pronta
- ✅ Early users usando

### Fase 06: Métricas Reais
- ✅ NPS > 50
- ✅ DAU 80%+
- ✅ Roadmap v2 claro

---

## 🚨 Riscos e Mitigações

Ver `docs/framework/01-Contexto-Global.md` para matriz completa.

**Top 3 Riscos:**
1. **Integração Slack quebra** → Monitorar + testes automatizados
2. **LGPD não compliance** → Audit externo semana 8
3. **Team não engaja** → Onboarding interativo + suporte live

---

## 📞 Contatos Rápidos

| Papel | Pessoa |
|-------|--------|
| Decisor | Daany |
| Tech Lead | — (definir) |
| Early Users | 2 Dev Pioneers |
| Legal/Compliance | — (conforme necessário) |

---

**Documento criado:** 2026-07-24  
**Próxima atualização:** Após cada fase completada
