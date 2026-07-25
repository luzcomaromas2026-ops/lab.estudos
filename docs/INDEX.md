# 📚 Índice de Documentação — Laboratório de Simbologia

> Guia de navegação para toda documentação do projeto.

---

## 🎯 Leitura Recomendada por Perfil

### **Para Entender o Projeto (Todos)**
1. [`00-Manifesto.md`](00-Manifesto.md) — Por que existe
2. [`01-Visao-Produto.md`](01-Visao-Produto.md) — O que será feito
3. [`12-Glossario.md`](12-Glossario.md) — Termos padrão

### **Para Stakeholders / Decisores**
1. [`01-Visao-Produto.md`](01-Visao-Produto.md)
2. [`02-PRD.md`](02-PRD.md) — Requisitos funcionais
3. [`11-Roadmap.md`](11-Roadmap.md) — Timeline

### **Para Designers (UI/UX)**
1. [`04-UX.md`](04-UX.md) — Fluxos e experiência
2. [`05-Design-System.md`](05-Design-System.md) — Componentes e tokens
3. [`07-Ontologia.md`](07-Ontologia.md) — Estrutura de dados visual

### **Para Engenheiros**
1. [`03-Arquitetura.md`](03-Arquitetura.md) — Decisões técnicas
2. [`06-Banco-de-Dados.md`](06-Banco-de-Dados.md) — Schema
3. [`07-Ontologia.md`](07-Ontologia.md) — Estrutura de dados
4. [`09-API.md`](09-API.md) — Endpoints
5. [`10-Seguranca.md`](10-Seguranca.md) — LGPD, auth, criptografia

### **Para Agentes IA (Claude, Cursor)**
[`CLAUDE.md`](CLAUDE.md) — Instruções, gates, regras

---

## 📖 Documentação Completa

### **00-Manifesto.md** — Identidade do Projeto
**O que é:** Manifesto declarativo  
**Quem lê:** Todos  
**Contém:**
- Propósito (por que existe)
- Missão (o que fazer)
- Visão (onde chegar)
- Valores (como fazer)
- O que é / O que não é
- Público-alvo
- Princípios científicos/filosóficos
- Limites éticos

**Leitura:** 10 min | **Frequência:** Antes de qualquer decisão material

---

### **01-Visao-Produto.md** — Visão Executiva
**O que é:** Documento de produto high-level  
**Quem lê:** Stakeholders, product managers, todos  
**Contém:**
- Visão em uma frase
- Problema + solução
- Componentes principais (Biblioteca, Grimórios, Fichas, Mapa, Diário)
- Personas (4)
- Objetivos mensuráveis
- Sucesso definido
- Diferenciação (vs. Obsidian, Wikipedia, Notion)

**Leitura:** 15 min | **Frequência:** Semanal de referência

---

### **02-PRD.md** — Product Requirements Document
**O que é:** Especificação funcional detalhada  
**Quem lê:** Designers, engenheiros, product  
**Contém:**
- Requisitos funcionais (features)
- Requisitos não-funcionais (performance, escalabilidade)
- Critérios de aceitação
- Dependências
- Riscos e mitigações
- User stories
- Casos de uso

**Leitura:** 30 min | **Frequência:** Referência contínua durante dev

---

### **03-Arquitetura.md** — Decisões Técnicas
**O que é:** Architecture Decision Record (ADR) + tech stack  
**Quem lê:** Engenheiros, tech lead  
**Contém:**
- Tech stack (frontend, backend, banco, deploy)
- Decisões técnicas com justificativa
- Diagramas de arquitetura
- Fluxos de dados
- Escalabilidade
- Plano de deploy

**Leitura:** 30 min | **Frequência:** Referência contínua

---

### **04-UX.md** — User Experience
**O que é:** Fluxos de usuário, wireframes, journeys  
**Quem lê:** Designers, product, engenheiros  
**Contém:**
- Personas e seus objetivos
- User journeys
- User stories
- Wireframes de telas principais
- Fluxos de interação
- Testes de usabilidade
- Acessibilidade

**Leitura:** 20 min (wireframes) + diagramas

---

### **05-Design-System.md** — Sistema de Design
**O que é:** Tokens de design, componentes, padrões  
**Quem lê:** Designers, frontend  
**Contém:**
- Paleta de cores
- Tipografia
- Espaçamento
- Componentes reutilizáveis
- Padrões de interação
- Temas (light/dark)
- Acessibilidade (WCAG)

**Leitura:** 20 min | **Frequência:** Referência contínua

---

### **06-Banco-de-Dados.md** — Schema e Modelos de Dados
**O que é:** Especificação de banco de dados  
**Quem lê:** Backend, engenheiro de dados  
**Contém:**
- Diagrama ER (Entity-Relationship)
- Schema SQL (todas as tabelas)
- Índices
- Relacionamentos
- Migrations
- Backup strategy
- Performance considerations

**Leitura:** 25 min | **Frequência:** Referência durante implementação

---

### **07-Ontologia.md** — Estrutura de Dados de Símbolos
**O que é:** O CORAÇÃO do sistema — semântica de símbolos  
**Quem lê:** Todos (conceitual), Engenheiros (implementação)  
**Contém:**
- Por que ontologia é necessária
- 7 propriedades fundamentais (É um, Representa, Relacionado a, etc.)
- 11 tipos de símbolos
- 10 tipos de relacionamentos
- Exemplos completos (Lua, Coruja, Ametista)
- JSON schema
- GraphQL schema
- Algoritmo de visualização do grafo

**Leitura:** 40 min (teórico) + exemplos práticos

---

### **08-IA.md** — Inteligência Artificial
**O que é:** Plano de IA (se houver)  
**Quem lê:** Tech lead, engenheiros ML (se aplicável)  
**Contém:**
- Escopo de IA (v1: nenhuma; v2: sugestões?)
- Modelos de IA considerados
- Limites éticos
- Privacidade
- Treinamento
- Monitoramento
- Alternativas não-IA

**Leitura:** 15 min | **Frequência:** Conforme necessário

---

### **09-API.md** — API Reference
**O que é:** Especificação de endpoints  
**Quem leia:** Backend, frontend, integradores  
**Contém:**
- Base URL
- Autenticação
- Endpoints (GET/POST/PUT/DELETE)
- Request/response schemas
- Status codes
- Rate limits
- Exemplos de uso
- Webhooks (se houver)

**Leitura:** 20 min (overview) + consulta contínua

---

### **10-Seguranca.md** — Segurança e Compliance
**O que é:** Estratégia de segurança  
**Quem lê:** Engenheiros, DevOps, compliance  
**Contém:**
- LGPD compliance
- Criptografia (repouso + trânsito)
- Autenticação (OAuth2)
- Autorização (RBAC)
- Audit logs
- Plano de incident response
- Penetration testing
- Data residency

**Leitura:** 25 min | **Frequência:** Antes de produção + anual

---

### **11-Roadmap.md** — Timeline e Fases
**O que é:** Roadmap de desenvolvimento  
**Quem lê:** Todos  
**Contém:**
- Timeline completa (fases 00-06)
- Milestones por fase
- Dependencies
- Resource allocation
- Go/no-go gates
- Risk timeline

**Leitura:** 10 min | **Frequência:** Semanal

---

### **12-Glossario.md** — Glossário de Termos
**O que é:** Dicionário do projeto  
**Quem lê:** Todos  
**Contém:**
- Termos de simbologia (símbolos, arquétipos, significados)
- Termos técnicos (ontologia, grafo, etc.)
- Termos de produto (grimórios, fichas, diário)
- Acrônimos

**Leitura:** Consulta conforme necessário

---

### **13-Contribuicao.md** — Guia de Contribuição
**O que é:** Como contribuir ao projeto  
**Quem lê:** Engenheiros, designers, comunidade  
**Contém:**
- Como setup dev environment
- Fluxo de branch/commit
- PR checklist
- Code style
- Review process
- Licença

**Leitura:** 15 min (primeira vez)

---

### **CLAUDE.md** — Instruções para Agentes IA
**O que é:** Prompt e regras para Claude/Cursor  
**Quem lê:** IA, humans coordinating with IA  
**Contém:**
- Leitura obrigatória (01-Contexto-Global)
- Stack técnico
- Visão e objetivos
- Regras principais (gates, compliance)
- Decisões já tomadas
- Stakeholders críticos

**Leitura:** 10 min (primeira vez) | **Frequência:** Antes de cada task

---

## 🗂️ Estrutura de Diretórios

```
docs/
├── INDEX.md (você está aqui)
│
├── 00-Manifesto.md
├── 01-Visao-Produto.md
├── 02-PRD.md
├── 03-Arquitetura.md
├── 04-UX.md
├── 05-Design-System.md
├── 06-Banco-de-Dados.md
├── 07-Ontologia.md
├── 08-IA.md
├── 09-API.md
├── 10-Seguranca.md
├── 11-Roadmap.md
├── 12-Glossario.md
├── 13-Contribuicao.md
│
└── CLAUDE.md
```

---

## 🔍 Busca Rápida

**Preciso entender o projeto:**
→ Comece com `00-Manifesto.md` + `01-Visao-Produto.md`

**Preciso implementar um feature:**
→ Consulte `02-PRD.md` (requisitos) + `03-Arquitetura.md` (tech) + `07-Ontologia.md` (dados)

**Preciso desenhar a UI:**
→ Comece em `04-UX.md` + `05-Design-System.md`

**Preciso construir a API:**
→ Consulte `06-Banco-de-Dados.md` (schema) + `09-API.md` (endpoints) + `10-Seguranca.md` (auth)

**Preciso fazer deploy:**
→ Consulte `03-Arquitetura.md` (tech stack) + `10-Seguranca.md` (compliance)

**Preciso trabalhar com IA (Claude/Cursor):**
→ Leia `CLAUDE.md`

---

## 📊 Matriz de Responsabilidade

| Documento | Product | Design | Backend | Frontend | Ops |
|-----------|---------|--------|---------|----------|-----|
| 00-Manifesto | RACI | R | I | I | I |
| 01-Visao | R | R | R | R | I |
| 02-PRD | R | R | R | R | I |
| 03-Arquitetura | A | I | R | R | R |
| 04-UX | C | R | I | R | I |
| 05-Design | I | R | I | R | I |
| 06-DB | I | — | R | I | R |
| 07-Ontologia | R | R | R | R | — |
| 08-IA | R | — | R | R | — |
| 09-API | C | I | R | R | I |
| 10-Seg | C | — | R | R | R |
| 11-Roadmap | R | R | R | R | R |
| 12-Glossario | R | R | R | R | — |
| 13-Contrib | — | — | R | R | R |

**R** = Responsible | **A** = Accountable | **C** = Consulted | **I** = Informed

---

## 🚀 Como Usar Este Índice

1. **Primeira vez no projeto?**
   - Leia este INDEX
   - Depois leia `00-Manifesto.md` + `01-Visao-Produto.md`

2. **Trabalha em uma feature específica?**
   - Use a tabela "Busca Rápida" acima
   - Consulte os documentos indicados

3. **Dúvida sobre um termo?**
   - Procure em `12-Glossario.md`

4. **Trabalha com IA?**
   - Leia `CLAUDE.md` antes de cada sessão

---

**Última atualização:** 25/07/2026  
**Versão:** 1.0  
**Status:** Estrutura definida, documentos em criação
