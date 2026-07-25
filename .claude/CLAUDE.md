# Instruções do Agente para Laboratório de Simbologia

## 📌 Leia Primeiro (OBRIGATÓRIO)

**[docs/framework/01-Contexto-Global.md](../docs/framework/01-Contexto-Global.md)** — Documento Mestre

Este é o documento central e atualizado. Consulte antes de qualquer decisão de escopo, arquitetura ou priorização.

---

## 🎯 Visão em uma Frase

Um app mobile que funciona como **Obsidian + Wikipedia pessoal** para pesquisadores de símbolos, com Biblioteca, Grimórios, Fichas de Pesquisa, Mapa Visual de Conexões e Diário do Laboratório.

---

## 📊 Objetivos Mensuráveis

1. **Tempo:** Pesquisadores economizam 5-10h/semana
2. **Descoberta:** Mapa revela 3+ relações novas/símbolo
3. **Adoção:** 50 early users ativos (comunidades tarô)
4. **Retenção:** 70%+ mantêm uso após 3 meses
5. **Satisfação:** NPS > 60 em Q1 2027

---

## ✅ Regras Principais

### 1. Contexto Global É Mestre
Antes de qualquer decisão:
> "Isto está alinhado com [`01-Contexto-Global.md`](../docs/framework/01-Contexto-Global.md)?"

Se não, consulte antes de prosseguir.

### 2. GATE Inegociável: Fase 04 → Fase 05
- **Fase 04 (Arquitetura):** Até 2026-10-15
- **GATE:** Aprovação obrigatória por Daany
- ❌ **Não codifique Fase 05 sem Fase 04 aprovada**
- **Risco:** Retrabalho, decisões técnicas não validadas, escolha de mobile framework errada

### 3. Inegociáveis Técnicos

#### Mobile-First Obrigatório
- App para celular (iOS + Android)
- React Native OU Flutter (Fase 04 decide)
- Grafo visual de conexões é core, não optional
- LGPD compliance em criptografia

#### Grafo de Conexões (Core)
- Visualização de símbolos conectados
- Clique em "Lua" mostra: A Sacerdotisa, Ártemis, Hécate, Yin, Inconsciente, Água, etc.
- Biblioteca de símbolos extensível
- D3.js, Cytoscape.js ou THREE.js (Fase 04)

#### LGPD Compliance
- ✅ Criptografia em repouso + trânsito
- ✅ Auditoria de acesso
- ✅ Direito ao esquecimento
- ✅ Política de privacidade

### 4. Mudanças Sensíveis (Auth / Dados / LGPD)
Para qualquer mudança em autenticação, schema de dados ou permissões:
1. **Explique:** Quem acessa? O quê? Como? Por quê?
2. **Peça confirmação:** Cite Daany (decisor)
3. **Depois implemente**

Não pule etapas.

### 5. Qualidade de Código

- ✅ Solução completa (não parcial)
- ✅ Arquivo e linha: `file.ts:42` ou `file.ts:42-51`
- ✅ **Riscos em negrito** (severidade + impacto)
- ✅ TypeScript strict mode (sem `any`)
- ✅ Testes para lógica crítica
- ✅ Grafo testado em desenvolvimento

---

## 📚 Documentação

| Fase | Status | Descrição | Documento |
|------|--------|-----------|-----------|
| 00 | ✅ Completo | Validação do problema | [00-Descoberta.md](../docs/framework/00-Descoberta.md) |
| 01 | 🔄 Em Progresso | **MESTRE — consultar sempre** | [01-Contexto-Global.md](../docs/framework/01-Contexto-Global.md) |
| 02 | ⏳ Planejado | Organização de docs | [02-Estrutura-Documental.md](../docs/framework/02-Estrutura-Documental.md) |
| 03 | ⏳ Planejado | Personas, features, wireframes | [03-Descoberta-do-Produto.md](../docs/framework/03-Descoberta-do-Produto.md) |
| 04 | ⏳ Planejado (GATE) | Decisões técnicas | [04-Arquitetura.md](../docs/framework/04-Arquitetura.md) |
| 05 | ⏳ Bloqueado | Desenvolvimento | [05-Implementacao.md](../docs/framework/05-Implementacao.md) |
| 06 | ⏳ Futuro | Feedback e métricas | [06-Evolucao.md](../docs/framework/06-Evolucao.md) |

---

## ⏰ Timeline Crítica (Começou 25/07/2026)

| Fase | Prazo | Responsável | Status |
|------|-------|-------------|--------|
| Fase 01 | 2026-07-25 | Daany | 🔄 Agora |
| Fase 02 | 2026-08-08 | Daany + Design | ⏳ Próximo |
| Fase 03 | 2026-08-22 | Daany + Comunidade | ⏳ |
| **Fase 04 (GATE)** | **2026-10-15** | **Tech Lead** | **⛔ CRÍTICO** |
| Fase 05 | 2026-11-05 | Eng Team | ⏳ Bloqueado |

---

## 🚫 Decisões Já Tomadas (NÃO REABRIR)

- ❌ Comunidade social → v2 (MVP = conhecimento pessoal)
- ❌ IA generativa → Hipótese não validada, v2+
- ❌ Desktop-first → Mobile-first obrigatório
- ❌ E-commerce/Marketplace → Fora de escopo
- ❌ Múltiplas línguas v1 → Português Brasil only

---

## 👥 Stakeholders Críticos

| Pessoa | Rol | Decisão | Contato |
|--------|-----|---------|---------|
| Daany | Lead User + Decisor | Final | Daily |
| Designer | UI/UX + Design System | Interface | Sprints |
| Tech Lead | Arquitetura + Mobile | Tech | PR reviews |
| Comunidade | Early Users | Feedback | Discord/comunidades |
| Legal | LGPD Guard | Compliance | Conforme necessário |

---

## 🔐 Componentes da MVP

### 📚 Biblioteca
- Upload/fichário de livros, artigos, PDFs
- Metadados: autor, tema, resumo, conceitos, símbolos
- Avaliação pessoal

### 📜 Grimórios (9 cadernos temáticos)
- Tarô, Sonhos, Cores, Animais, Arquétipos, Mitologia, Alquimia, Religiões, Psicologia Analítica
- Descobertas, hipóteses, conexões, interpretações, dúvidas

### 🔍 Fichas de Pesquisa
- Símbolo: Coruja
- Origem, significados, culturas, mitologias
- Relação com Tarô, Jung, Alquimia, Astrologia
- Observações pessoais

### 🕸️ Mapa de Conexões (CORE!)
- Clique em "Lua" → visualiza: A Sacerdotisa, Ártemis, Hécate, Yin, Inconsciente, Água, Feminino, Sonhos, Ciclos, Marés
- Grafo interativo
- Adicionar/editar conexões

### 🧪 Diário do Laboratório
- Timeline cronológica
- Registro de descobertas ao longo do tempo
- "24/07/2026: Encontrei relação entre serpente da alquimia e Ouroboros..."

---

## ✅ Checklist Antes de Commit

- [ ] Contexto Global foi consultado
- [ ] TypeScript strict (sem `any`)
- [ ] Nenhum secret em código
- [ ] Testes para lógica crítica
- [ ] Grafo visual testado (se aplicável)
- [ ] Se auth/dados/LGPD: explicou + confirmação antes de código
- [ ] PR com descrição clara + link para Contexto Global
