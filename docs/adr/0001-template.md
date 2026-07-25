# ADR NNNN — Título da decisão

**Data:** YYYY-MM-DD  
**Status:** Proposta | Aprovada | Recusada | Substituída  
**Fase:** 00-06  
**Owner:** (seu nome)  
**Revisor:** (quem aprova)

---

## 📌 Resumo Executivo

Uma frase clara sobre a decisão. Ex: "Usar PostgreSQL com Supabase em vez de Firebase por requisitos LGPD."

---

## 🎯 Contexto

**O Problema:**
Descreva o problema técnico, operacional ou arquitetural que levou à decisão.

**Constraints:**
- Requisito 1 (ex: LGPD compliance obrigatório)
- Requisito 2 (ex: mobile-first)
- Restrição 1 (ex: budget, timeline)

**Impacto de não decidir:**
O que acontece se não resolvermos?

---

## 🤔 Alternativas Consideradas

### Opção A: (Nome da tecnologia/abordagem)
**Prós:**
- ✅ Benefício 1
- ✅ Benefício 2

**Contras:**
- ❌ Risco/custo 1
- ❌ Risco/custo 2

**Effort:** X semanas | **Cost:** $ | **Risk:** Alto/Médio/Baixo

---

### Opção B: (Nome da tecnologia/abordagem)
**Prós:**
- ✅ Benefício 1

**Contras:**
- ❌ Risco/custo 1

**Effort:** X semanas | **Cost:** $ | **Risk:** Alto/Médio/Baixo

---

## ✅ Decisão

**Escolhemos:** [Opção A/B/C]

**Razão:** Atende melhor aos constraints de [LGPD/Performance/Timeline] com [XYZ] trade-off aceitável.

---

## 📊 Comparação Final

| Critério | Opção A | Opção B | **Escolhida** |
|----------|---------|---------|--------------|
| LGPD compliance | ✅ | ❌ | ✅ |
| Performance | ✅ | ✅ | ✅ |
| Timeline (16 sem) | ⏱️ 12 | ⏱️ 8 | ✅ 8 |
| Custo | $10k | $5k | (🤝) |

---

## 🔄 Impacto & Trade-offs

**Benefícios:**
- Descrição de por que isso resolve o problema

**Sacrifícios:**
- O que perdemos (se houver)

**Arquivos/Componentes Afetados:**
- `backend/db/schema.sql`
- `frontend/api/client.ts`
- Etc.

**Operações & Deploy:**
- Plano de rollout
- Fallback strategy
- Monitoramento

---

## 🚀 Plano de Implementação

**Fase 1 (Semana X):** Setup / Prototipagem  
**Fase 2 (Semana Y):** Integração  
**Fase 3 (Semana Z):** Testing & Validação  

**Milestones:**
- [ ] Milestone 1
- [ ] Milestone 2
- [ ] Milestone 3

---

## ⚠️ Riscos & Mitigações

| Risco | Probabilidade | Impacto | Mitigation |
|-------|---------------|---------|-----------|
| Risco 1 | Alta | Alto | Ação 1 |
| Risco 2 | Média | Médio | Ação 2 |

---

## 📋 Critério de Sucesso

- [ ] Critério 1 (measurable)
- [ ] Critério 2 (testable)
- [ ] Critério 3 (verifiable)

**Quando:** Data target

---

## 🔗 Referências

- Link para issue/PR/doc
- RFC ou spec externa
- Precedente similar

---

## ✍️ Histórico de Decisões

| Data | Evento | Detalhes |
|------|--------|----------|
| YYYY-MM-DD | Proposta | Contexto inicial |
| YYYY-MM-DD | Review 1 | Feedback de X |
| YYYY-MM-DD | Aprovada | Por [Daany/Tech Lead] |

---

## 👥 Aprovações

- [ ] **Daany** (Lead User) — _____ data
- [ ] **Tech Lead** (Arquitetura) — _____ data
- [ ] **Designer** (UI/UX) — _____ data (se aplicável)

---

## 📝 Notas

Observações adicionais, discussions, ou follow-ups.

---

**Status:** ✅ Aprovada | ⏳ Aguardando | ❌ Recusada

**Próxima revisão:** [Data ou "Nunca — decisão permanente"]

