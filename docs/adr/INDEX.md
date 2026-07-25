# 🏛️ Architecture Decision Records (ADRs)

**Laboratório de Simbologia — Decisões Arquiteturais Documentadas**

---

## 📌 O que é ADR?

Um **Architecture Decision Record** documenta decisões técnicas importantes:
- **Por que** foi tomada
- **O que** foi considerado
- **Como** afeta o projeto
- **Quem** aprovou

Criamos um registro permanente para:
- ✅ Evitar rediscussões
- ✅ Rastrear evolução técnica
- ✅ Onboard novos devs
- ✅ Justificar trade-offs

---

## 📋 ADRs Atuais

### Status Legend
- 🟢 **Aprovada** — Decisão final, implementar
- 🟡 **Proposta** — Aguardando review
- 🔴 **Recusada** — Rejeitada, não usar
- 🔵 **Substituída** — Superada por ADR mais nova

---

### Fase 04 (Arquitetura) — Em Planejamento

**Decisões esperadas em Fase 04 (até 15/10/2026):**

#### Mobile Framework Decision
- [ ] ADR-0002: React Native vs Flutter
  - **Owner:** Tech Lead
  - **Target:** Decidir qual framework antes de Fase 05
  - **Impacto:** Toda arquitetura frontend

#### Database & ORM
- [ ] ADR-0003: Prisma vs Raw SQL vs TypeORM
  - **Owner:** Backend Lead
  - **Target:** Escolher ORM para PostgreSQL
  - **Impacto:** Todas as queries, migrations

#### Graph Visualization Library
- [ ] ADR-0004: D3.js vs Cytoscape.js vs Babylon.js
  - **Owner:** Frontend Lead
  - **Target:** Selecionar lib para Mapa de Conexões
  - **Impacto:** Performance, interatividade do grafo

#### Authentication Strategy
- [ ] ADR-0005: NextAuth.js vs Manual OAuth2
  - **Owner:** Daany + Tech Lead
  - **Target:** Definir fluxo de login/session
  - **Impacto:** Segurança, compliance LGPD

#### API Rate Limiting & Caching
- [ ] ADR-0006: Redis vs Built-in cache vs CDN
  - **Owner:** Backend Lead
  - **Target:** Performance sob load
  - **Impacto:** Infraestrutura, custo

#### Encryption Strategy
- [ ] ADR-0007: Field-level vs DB-level encryption para dados sensíveis
  - **Owner:** Security Lead + Daany
  - **Target:** LGPD compliance
  - **Impacto:** Performance, manageability

---

## 📚 Referências

- [ADR GitHub](https://adr.github.io/) — Standard ADR format
- [MADR Format](https://adr.github.io/madr/) — Markdown ADR variant

---

## 🎯 Como Criar uma Nova ADR

```bash
# 1. Copiar template
cp docs/adr/0001-template.md docs/adr/000N-descricao-curta.md

# 2. Preencher todas as seções

# 3. Submeter como PR
git checkout -b adr/seu-titulo
git add docs/adr/000N-descricao.md
git commit -m "adr: Adicionar ADR-000N — Seu título"
git push origin adr/seu-titulo
```

---

## ✅ Checklist para Aprovação

Um ADR é aprovado quando atende:

- [ ] Contexto claro (problema definido)
- [ ] Mínimo 2 alternativas consideradas
- [ ] Impacto documentado
- [ ] Plano de implementação
- [ ] Riscos e mitigações
- [ ] Critério de sucesso (testável)
- [ ] Aprovado por Tech Lead + Daany

---

**Última atualização:** 25/07/2026  
**Próxima revisão:** 15/10/2026 (Fase 04 - GATE)

