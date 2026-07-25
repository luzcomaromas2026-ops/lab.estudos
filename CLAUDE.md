# 🤖 Instruções para Claude/Cursor

**Laboratório de Simbologia — Regras para Agentes IA**

---

## 📌 Leia Primeiro (OBRIGATÓRIO)

**Antes de qualquer trabalho neste projeto:**

1. [`docs/01-Visao-Produto.md`](docs/01-Visao-Produto.md) — O que é o projeto
2. [`docs/00-Manifesto.md`](docs/00-Manifesto.md) — Por que existe
3. [`ONTOLOGIA.md`](ONTOLOGIA.md) — Como funciona (CORE!)

**Depois, conforme necessário:**
- [`docs/02-PRD.md`](docs/02-PRD.md) — Requisitos funcionais
- [`docs/03-Arquitetura.md`](docs/03-Arquitetura.md) — Decisões técnicas
- [`docs/05-Design-System.md`](docs/05-Design-System.md) — Visual + componentes
- [`docs/10-Seguranca.md`](docs/10-Seguranca.md) — LGPD + auth
- [`docs/12-Glossario.md`](docs/12-Glossario.md) — Termos

---

## 🎯 Visão em Uma Frase

Um app mobile que funciona como **Obsidian + Wikipedia pessoal** para pesquisadores de símbolos. O **Mapa de Conexões** (grafo visual) é o core que diferencia de ferramentas genéricas.

---

## 🏗️ Stack Técnico (OBRIGATÓRIO)

```
Frontend:
├─ React Native ou Flutter (decidir em Fase 04)
├─ TypeScript (strict mode)
├─ Tailwind CSS (estilos)
└─ D3.js ou Cytoscape (grafo)

Backend:
├─ Node.js 18+
├─ Express / Fastify
├─ TypeScript
├─ GraphQL (recomendado)
└─ Prisma (ORM)

Database:
├─ PostgreSQL 14+
├─ Supabase (managed)
├─ Row-Level Security (RLS)
└─ Encrypted columns (para dados sensíveis)

Deploy:
├─ Frontend: Vercel
├─ Backend: Railway ou Vercel Functions
└─ Database: Supabase Cloud

Auth:
├─ OAuth2 (Google + GitHub)
├─ JWT (tokens)
└─ NextAuth.js (facilita)
```

**NUNCA mude stack sem aprovação do Tech Lead.**

---

## 🎨 Design (DO's & DON'Ts)

### ✅ DO's

```
✅ Use tipografia: Inter, Manrope, Geist (sans-serif)
✅ Use cores neutras + acentos: azul #0066FF, verde #2D8659
✅ Ícones: traço fino, minimalistas (Heroicons)
✅ Componentes: simples, reutilizáveis
✅ Acessibilidade: WCAG 2.1 AA mínimo
✅ Tema claro como padrão (dark mode é v2)
✅ Design System: consulte docs/05-Design-System.md
```

### ❌ DON'Ts

```
❌ Não use preto puro (#000000)
❌ Não use roxo dominante (roxo só no mapa!)
❌ Não use dourado exagerado
❌ Não use fontes góticas/serifas
❌ Não use ícones "místicos" (estrelas, luas desenhadas)
❌ Não invente componentes (use design system)
❌ Não sacrifique acessibilidade por estética
```

---

## 🎭 Observatório (CORE VISUAL)

A navegação não é um menu tradicional. É um **Observatório**:

```
Círculo central = Laboratório (o app)
5 constelações ao redor = 5 módulos:

         📚 BIBLIOTECA
              ↑
📜 GRIMÓRIOS ←|→ 🔍 FICHAS
              ↓
        🕸️ MAPA + 🧪 DIÁRIO
```

**Implementação:**
- Bottom tabs (mobile)
- Sidebar (desktop)
- Cada módulo tem ícone + label
- Ícone ativo faz scale 1.1
- Animação fade entre módulos (150ms)

**NUNCA mude a ordem ou nomes dos módulos.**

---

## 🔐 Segurança & LGPD (CRÍTICO)

### Princípios (Não Negociáveis)

```
✅ Dados pessoais NUNCA hardcoded
✅ LGPD compliant sempre (v1 já!)
✅ Criptografia: TLS 1.3 + AES-256
✅ Auth: OAuth2 + JWT
✅ RLS: Row-Level Security no banco
✅ Audit logs: todas as ações
✅ Soft delete: direito ao esquecimento
```

### Código Seguro

```typescript
// ✅ CORRETO
const secret = process.env.JWT_SECRET;
const user = await db.symbols.findMany({
  where: { userId: auth.uid() }  // Sempre filtrar por user!
});

// ❌ ERRADO
const secret = "abc123";  // Secret em código!
const user = await db.symbols.findMany();  // Sem filtro!
const sql = `SELECT * FROM users WHERE id = ${userId}`;  // SQL injection!
```

---

## 🧬 Ontologia (COMO FUNCIONA)

**Todo símbolo tem esta estrutura:**

```graphql
type Symbol {
  id: ID!
  name: String!
  types: [SymbolType!]!           # Animal, Divindade, Carta, etc
  meanings: [Meaning!]!           # Sabedoria, Morte, Feminino, etc
  relationsFrom: [Relation!]!     # Símbolos que conecta
  relationsTo: [Relation!]!       # Símbolos que conectam nele
  contexts: [Context!]!           # Mitologia Grega, Tarô, etc
  observations: [Observation!]!   # Diário pessoal
}
```

**Tipos de símbolos válidos:**
```
ANIMAL, DIVINDADE, CARTA, ELEMENTO, COR, NUMERO,
PLANTA, CRISTAL, LUGAR, ACAO, ARQUETIPO, GEOMETRIA
```

**Tipos de relacionamentos válidos:**
```
ORIGEM_DE, EQUIVALENTE_A, OPOSTO_DE, COMPLEMENTAR_DE,
ASPECTO_DE, GOVERNADO_POR, HABITA,
RELACIONADO_PSICOLOGICAMENTE, SINCRONICIDADE_COM,
EXPRESSA_QUALIDADE_DE
```

**LEIA**: [`ONTOLOGIA.md`](ONTOLOGIA.md) para exemplos completos.

---

## 🚫 Decisões Já Tomadas (NÃO REABRA)

```
❌ Comunidade social → v2 (MVP = pessoal)
❌ IA generativa → v2+ (v1 = zero IA)
❌ Desktop-first → Mobile-first (obrigatório)
❌ E-commerce/Marketplace → Fora de escopo
❌ Múltiplas linguagens → v1 é PT-BR only
❌ Preto puro na UI → Cinza #212529
❌ Roxo dominante → Apenas no mapa
❌ Doubrado exagerado → Minimalista
```

Se quiser reabrir: peça ao Daany (decisor), não mude sozinho.

---

## ⏱️ Timeline & Gates (CRÍTICO)

```
Fase 02 (até 08/08): Estrutura Documental
Fase 03 (até 22/08): Descoberta do Produto
Fase 04 (até 15/10): ARQUITETURA ⛔ GATE OBRIGATÓRIO
  └─ Não codifique Fase 05 sem aprovação!
Fase 05 (até 16/12): Implementação
Fase 06 (até 05/02): Evolução & Métricas
```

**NÃO PODE pular gate:** Retrabalho é caro.

---

## 📊 Qualidade de Código

### Antes de Submeter PR

```bash
npm run lint          # ESLint debe passar
npm run type-check    # TypeScript strict
npm run test          # Testes verde
```

### Checklist de Qualidade

- [ ] TypeScript strict (sem `any`)
- [ ] Sem console.log() debug
- [ ] Sem secrets em código
- [ ] Acessibilidade: keyboard + screen reader
- [ ] Testes para lógica crítica
- [ ] Nomes descritivos (sem `x`, `temp`, `foo`)
- [ ] Sem comentários óbvios
- [ ] Funciona mobile + desktop

---

## 🎯 Objetivos (Para Alinhar Prioridades)

```
MVP (16 semanas):
├─ 50 early users ativos
├─ Mapa renderiza 1000 nós fluido
├─ LGPD compliant
├─ NPS > 50 (baseline)
└─ 70%+ retenção após 3 meses

Não é objetivo:
├─ 1000 users (é para depois)
├─ Comunidade social
├─ IA features
├─ Exportação em múltiplos formatos
```

---

## 🔗 Links Críticos

```
📋 INDEX: docs/INDEX.md (navegação de docs)
👁️ Visão: docs/01-Visao-Produto.md
📖 Manifesto: docs/00-Manifesto.md
🧬 Ontologia: ONTOLOGIA.md
🏗️ Arquitetura: docs/03-Arquitetura.md
🎨 Design: docs/05-Design-System.md
🗄️ DB: docs/06-Banco-de-Dados.md
🔌 API: docs/09-API.md
🔒 Segurança: docs/10-Seguranca.md
🎯 Roadmap: docs/11-Roadmap.md
📚 Glossário: docs/12-Glossario.md
🤝 Contribuição: docs/13-Contribuicao.md
```

---

## 👥 Stakeholders Críticos

```
Daany (you)
├─ Role: Lead User + Decisor
├─ Decisão: Final em scope/features
└─ Approval: Requerido para mudanças material

Designer
├─ Role: UI/UX + Design System
└─ Approval: Requerido para design changes

Tech Lead
├─ Role: Arquiteto
└─ Approval: GATE Fase 04 (obrigatório)
```

---

## 🚨 Quando Pedir Help

```
❓ Escopos de features: Pergunte ao Daany
❓ Decisões de tech stack: Pergunte ao Tech Lead
❓ Design system: Pergunte ao Designer
❓ Segurança: Pergunte ao Daany + Tech Lead
❓ Dúvida em ontologia: Leia ONTOLOGIA.md + Manifesto
```

---

## ✨ Bonus: Inspiração

Você está construindo **a ferramenta pessoal perfeita para pesquisadores de símbolos.**

O Mapa de Conexões revela relações que levaria alguém 5 livros para descobrir. Isso é *especial*.

Código que escreve aqui pode impactar milhares de pessoas explorando simbologia de forma profunda.

Mantenha isso em mente ao tomar decisões técnicas. 🌟

---

**Criado em:** 25/07/2026  
**Versão:** 1.0  
**Status:** ATIVO - Leia antes de trabalhar no projeto!
