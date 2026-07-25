# 📅 Roadmap

**Laboratório de Simbologia — 16 semanas até MVP**

---

## 🎯 Timeline Completa

### **Fase 01 — Contexto (Até 25/07)** ✅

```
✅ Fase 01 concluída
└─ Contexto Global definido
   Stakeholders mapeados
   Riscos identificados
```

---

### **Fase 02 — Estrutura Documental (08/08)**

```
Duração: 2 semanas
Owner: Daany + Design

Entregas:
├─ Convenções de documentação
├─ CI/CD para Markdown linting
├─ Setup de ADRs (Architecture Decision Records)
└─ Todos documentos indexados

Critério de Sucesso:
└─ Documentação pronta para Fase 03
```

---

### **Fase 03 — Descoberta do Produto (22/08)**

```
Duração: 2 semanas
Owner: Daany + Design + Pioneers

Entregas:
├─ Personas finalizadas
├─ Feature matrix priorizada
├─ Wireframes (Observatório core)
├─ Prototipo de Mapa de Conexões (tech viability)
├─ Design System (Observatório visual)
└─ Validação com 5+ early adopters

Critério de Sucesso:
├─ Protótipo de mapa renderiza 1000 nós fluido
├─ Early users adoram conceito
└─ Nenhum blocker técnico identificado
```

---

### **Fase 04 — Arquitetura (15/10)** ⛔ GATE

```
Duração: 7 semanas
Owner: Tech Lead + Backend + Frontend

Entregas:
├─ Tech stack finalizado (React Native vs Flutter)
├─ Schema PostgreSQL completo
├─ GraphQL schema definido
├─ Decisões arquiteturais documentadas (ADRs)
├─ Diagrama de deployment
├─ Plano de segurança + LGPD checklist
├─ Pentesting completado
└─ Prototipo técnico (Hello World em stack real)

Critério de Sucesso:
├─ Tech Lead aprova arquitetura
├─ Nenhum blocker de segurança
├─ Performance targets atingidos em prototype
└─ ✅ APROVAÇÃO OBRIGATÓRIA ANTES FASE 05
```

---

### **Fase 05 — Implementação (05/11)**

```
Duração: 6 semanas (até 16/12)
Owner: Eng Team

Sprint Breakdown:

Sprint 1 (05/11-12/11): Base
├─ Setup project (React Native / Flutter)
├─ Auth (OAuth2 + JWT)
├─ PostgreSQL connection
└─ GraphQL API skeleton

Sprint 2 (13/11-19/11): Core Features
├─ CRUD símbolos
├─ CRUD fichas
├─ Significados + contextos
└─ Relacionamentos (grafo core)

Sprint 3 (20/11-26/11): UI
├─ Observatório (navigation)
├─ Fichas de pesquisa (UI)
├─ Biblioteca (livros)
└─ Theme (light mode completo)

Sprint 4 (27/11-03/12): Graph Visualization
├─ Mapa de conexões (D3/Cytoscape)
├─ Interatividade (zoom, drag)
├─ Performance optimization
└─ Export como imagem

Sprint 5 (04/12-10/12): Polish
├─ Grimórios + Diário
├─ Search + filtering
├─ Testes (unit + integration)
├─ Performance profiling
└─ Accessibility (WCAG AA)

Sprint 6 (11/12-16/12): Launch Prep
├─ Security audit
├─ Load testing
├─ Marketing assets
├─ App store setup
└─ Release notes

MVP Soft Launch: 16/12/2026
```

---

### **Fase 06 — Evolução (05/02/2027)**

```
Duração: 12 semanas
Owner: Product + Eng + Data

Entregas:
├─ NPS > 60
├─ 50 active users
├─ 70%+ retention (3 month)
├─ 1000+ símbolos em database
├─ Roadmap v2.0 (v2 features)
└─ Post-launch learnings documented
```

---

## 📊 Milestones Críticos

| Data | Milestone | Owner | Status |
|------|-----------|-------|--------|
| 2026-07-25 | Fase 01 completa | Daany | ✅ |
| 2026-08-08 | Fase 02 completa | Daany + Design | ⏳ |
| 2026-08-22 | Fase 03 completa | Daany + Design | ⏳ |
| **2026-10-15** | **GATE Fase 04** | **Tech Lead** | **⛔ CRÍTICO** |
| 2026-11-05 | Fase 05 inicia | Eng Team | ⏳ |
| 2026-12-16 | **MVP Lançado** | All | ⏳ |
| 2027-02-05 | Fase 06 métricas | Product | ⏳ |

---

## 🎯 Resource Allocation

```
Fase 02: 20% Daany, 40% Designer, 10% Tech Lead
Fase 03: 30% Daany, 50% Designer, 20% Tech Lead
Fase 04: 10% Daany, 5% Designer, 100% Tech Lead
Fase 05: 10% Daany, 20% Designer, 100% Eng Team (3-4 devs)
Fase 06: 50% Product, 50% Eng, 20% Data Science
```

---

## 🚨 Risks & Mitigation

| Risk | Probability | Impact | Mitigation |
|------|---|---|---|
| Graph rendering slow | High | High | Prototype early (Fase 03) |
| Team turnover | Medium | High | Knowledge sharing, docs |
| Scope creep | High | Medium | Gate at Fase 04, say NO |
| LGPD compliance | Low | Critical | Audit externo semana 8 |

---

## 📞 Governance

```
Weekly Sync:
├─ Monday: Status update (30 min)
├─ Thursday: Blockers only (15 min)
└─ As-needed: Emergency

Monthly Review:
├─ Phase progress
├─ Budget burn
├─ Team health
└─ Next phase readiness
```

---

**Última atualização:** 25/07/2026  
**Próxima revisão:** 01/08/2026
