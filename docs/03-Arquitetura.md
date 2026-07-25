# 🏗️ Arquitetura Técnica

**Laboratório de Simbologia — Decisões de Tech Stack**

---

## 📌 Informações Gerais

| Campo | Valor |
|-------|-------|
| **Documento** | Architecture Decision Record (ADR) |
| **Data** | 25/07/2026 (Versão Preliminar) |
| **Status** | DRAFT (Fase 04 finaliza) |
| **Gate** | Deve ser aprovado antes de Fase 05 |

---

## ⚠️ AVISO IMPORTANTE

Este documento é **hipotético para Fase 03**. Decisões finais em **Fase 04 (até 2026-10-15)**.

---

## 🎯 Princípios de Arquitetura

1. **Mobile-First** — Usuário segura no bolso
2. **Escalabilidade** — 10,000+ símbolos
3. **Performance** — Grafo interativo fluido
4. **Segurança** — LGPD compliant
5. **Manutenibilidade** — Código limpo, documentado
6. **Offline-First (possível)** — Trabalha sem internet

---

## 🏛️ Arquitetura Geral

```
┌─────────────────────────────────────────────────────────┐
│                    FRONTEND MOBILE                       │
│  React Native / Flutter (iOS + Android + Web)            │
│  ┌──────────────────────────────────────────────────┐   │
│  │  UI Layer (Componentes)                           │   │
│  │  • Fichas de Pesquisa                            │   │
│  │  • Grimórios                                      │   │
│  │  • Biblioteca                                     │   │
│  │  • Mapa de Conexões (D3/Cytoscape)               │   │
│  │  • Diário                                         │   │
│  └──────────────────────────────────────────────────┘   │
│  ┌──────────────────────────────────────────────────┐   │
│  │  State Management (Redux/MobX)                    │   │
│  │  • Símbolos                                       │   │
│  │  • Relacionamentos                                │   │
│  │  • User data                                      │   │
│  └──────────────────────────────────────────────────┘   │
│  ┌──────────────────────────────────────────────────┐   │
│  │  Local Storage (SQLite / Realm)                   │   │
│  │  • Cache offline                                 │   │
│  │  • Sync quando retorna online                    │   │
│  └──────────────────────────────────────────────────┘   │
└──────────────────┬──────────────────────────────────────┘
                   │ HTTPS/TLS 1.3
                   │ GraphQL ou REST
┌──────────────────▼──────────────────────────────────────┐
│                  BACKEND (Node.js)                       │
│  Express / Fastify                                       │
│  ┌──────────────────────────────────────────────────┐   │
│  │  API Layer (GraphQL ou REST)                      │   │
│  │  • Query símbolos                                │   │
│  │  • Mutate fichas                                 │   │
│  │  • Upload arquivo                                │   │
│  └──────────────────────────────────────────────────┘   │
│  ┌──────────────────────────────────────────────────┐   │
│  │  Business Logic                                   │   │
│  │  • Ontologia engine                              │   │
│  │  • Relacionamentos (grafo)                        │   │
│  │  • Busca + indexação                             │   │
│  │  • Auth (OAuth2)                                 │   │
│  └──────────────────────────────────────────────────┘   │
│  ┌──────────────────────────────────────────────────┐   │
│  │  Cache Layer (Redis)                              │   │
│  │  • Query cache                                    │   │
│  │  • Session storage                                │   │
│  └──────────────────────────────────────────────────┘   │
└──────────────────┬──────────────────────────────────────┘
                   │
┌──────────────────▼──────────────────────────────────────┐
│              DATABASE (Supabase PostgreSQL)              │
│  ┌──────────────────────────────────────────────────┐   │
│  │  Tabelas:                                         │   │
│  │  • usuarios (auth)                               │   │
│  │  • simbolos                                       │   │
│  │  • significados                                   │   │
│  │  • relacionamentos (grafo)                        │   │
│  │  • contextos                                      │   │
│  │  • observacoes_pessoais                           │   │
│  │  • fontes                                         │   │
│  │  • bibliotecas (livros)                           │   │
│  │  • grimorio_entradas                              │   │
│  │  • audit_logs                                     │   │
│  └──────────────────────────────────────────────────┘   │
│  ┌──────────────────────────────────────────────────┐   │
│  │  Segurança (Supabase):                            │   │
│  │  • Row-Level Security (RLS)                       │   │
│  │  • Encryption at rest                             │   │
│  │  • Automatic backups                              │   │
│  └──────────────────────────────────────────────────┘   │
└──────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────┐
│              INFRAESTRUTURA (Cloud)                       │
│  ┌──────────────────────────────────────────────────┐   │
│  │  Frontend: Vercel (Next.js web)                   │   │
│  │  Backend: Vercel Functions / Railway             │   │
│  │  Database: Supabase Cloud                        │   │
│  │  Storage: Supabase Storage (PDFs)                 │   │
│  │  CDN: Vercel Edge / Cloudflare                    │   │
│  │  Monitoring: Sentry + LogRocket                   │   │
│  └──────────────────────────────────────────────────┘   │
└──────────────────────────────────────────────────────────┘
```

---

## 📱 Frontend (Mobile)

### Stack Recomendado

**Opção A: React Native (RECOMENDADO)**
```
✅ Vantagens:
  • JavaScript/TypeScript
  • Code sharing (até 70%)
  • Comunidade grande
  • UI performance OK
  
⚠️ Desvantagens:
  • Não é "truly native"
  • Grafo visual precisa lib extra
  • Deploy um pouco mais complexo
```

**Opção B: Flutter**
```
✅ Vantagens:
  • Performance nativa
  • Hot reload excelente
  • UI muito rápida
  • Suporte a desktop/web também
  
⚠️ Desvantagens:
  • Dart (nova linguagem)
  • Comunidade menor
  • Menos libs de grafo
```

**Decisão (Fase 04):** React Native (provavelmente), por ecossistema + JS expertise

### Arquitetura Frontend

```typescript
src/
├── components/        // Componentes reutilizáveis
│   ├── SymbolCard.tsx
│   ├── GraphViewer.tsx
│   ├── GrimorioEntry.tsx
│   └── ...
├── screens/          // Telas principais
│   ├── LibraryScreen.tsx
│   ├── GrimoriosScreen.tsx
│   ├── SymbolDetailsScreen.tsx
│   ├── MapScreen.tsx
│   └── DiaryScreen.tsx
├── store/            // State (Redux/MobX)
│   ├── symbolsSlice.ts
│   ├── relationsSlice.ts
│   ├── userSlice.ts
│   └── ...
├── services/         // API calls
│   ├── symbolService.ts
│   ├── graphService.ts
│   └── ...
├── hooks/            // Custom hooks
├── utils/            // Helpers
└── types/            // TypeScript types
```

### Dependências Críticas

```json
{
  "react-native": "^0.72",
  "react": "^18",
  "redux-toolkit": "^1.9",
  "react-native-svg": "^13",
  "d3": "^7",           // Para grafo
  "cytoscape": "^3",    // Alternativa a D3
  "axios": "^1"         // HTTP client
}
```

---

## 🔧 Backend (Node.js)

### Stack Recomendado

```
Framework: Express.js ou Fastify
Language: TypeScript
Auth: NextAuth.js (OAuth2)
ORM: Prisma (type-safe)
Cache: Redis
Queue: Bull (se houver async tasks)
Logging: Winston + Pino
```

### Arquitetura Backend

```
src/
├── routes/
│   ├── symbols.ts        // CRUD de símbolos
│   ├── relations.ts      // Grafo
│   ├── library.ts        // Livros
│   ├── grimorio.ts       // Grimórios
│   └── auth.ts           // OAuth2
├── controllers/          // Business logic
├── services/             // Data access
├── models/               // Interfaces TypeScript
├── middleware/           // Auth, CORS, etc
├── utils/                // Helpers
└── types/                // Tipos globais
```

### API (GraphQL vs REST)

**GraphQL (RECOMENDADO para grafo)**
```graphql
type Símbolo {
  id: ID!
  nome: String!
  tipos: [TipoSímbolo!]!
  significados: [Significado!]!
  relacionadoA: [Relação!]!
  apareceEm: [Contexto!]!
}

type Query {
  símbolo(id: ID!): Símbolo
  buscarSímbolos(termo: String!): [Símbolo!]!
  grafo(idSímbolo: ID!): Grafo!
}

type Mutation {
  criarSímbolo(input: CreateSymbolInput!): Símbolo!
  conectarSímbolos(origem: ID!, destino: ID!, tipo: TipoRelação!): Relação!
}
```

**REST (alternativa)**
```
GET    /api/symbols              # List
GET    /api/symbols/:id          # Detail
POST   /api/symbols              # Create
PUT    /api/symbols/:id          # Update
DELETE /api/symbols/:id          # Delete
GET    /api/symbols/:id/graph    # Grafo
GET    /api/symbols/search?q=    # Busca
POST   /api/relations            # Conectar
```

---

## 🗄️ Banco de Dados (Supabase PostgreSQL)

### Schema Simplificado

```sql
-- Usuários (OAuth)
CREATE TABLE users (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  email VARCHAR(255) UNIQUE NOT NULL,
  name VARCHAR(255),
  created_at TIMESTAMP DEFAULT now()
);

-- Símbolos
CREATE TABLE symbols (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID REFERENCES users(id),
  name VARCHAR(255) NOT NULL,
  types TEXT[] NOT NULL,      -- ARRAY de tipos
  created_at TIMESTAMP DEFAULT now(),
  updated_at TIMESTAMP DEFAULT now()
);

-- Significados
CREATE TABLE meanings (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  symbol_id UUID REFERENCES symbols(id) ON DELETE CASCADE,
  meaning TEXT NOT NULL,
  tradition VARCHAR(255),
  context TEXT,
  source VARCHAR(255),
  created_at TIMESTAMP DEFAULT now()
);

-- Relacionamentos (CORE para grafo)
CREATE TABLE relations (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  origin_symbol_id UUID REFERENCES symbols(id) ON DELETE CASCADE,
  target_symbol_id UUID REFERENCES symbols(id) ON DELETE CASCADE,
  relation_type VARCHAR(50) NOT NULL,  -- origem_de, equivalente_a, etc
  description TEXT,
  created_at TIMESTAMP DEFAULT now(),
  -- Índice para performance de grafo
  UNIQUE(origin_symbol_id, target_symbol_id, relation_type)
);
CREATE INDEX idx_relations_origin ON relations(origin_symbol_id);
CREATE INDEX idx_relations_target ON relations(target_symbol_id);

-- Contextos (aparece em)
CREATE TABLE contexts (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  symbol_id UUID REFERENCES symbols(id) ON DELETE CASCADE,
  context_type VARCHAR(255),      -- Mitologia Grega, Tarô, etc
  description TEXT,
  created_at TIMESTAMP DEFAULT now()
);

-- Observações Pessoais (Diário)
CREATE TABLE observations (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID REFERENCES users(id),
  symbol_id UUID REFERENCES symbols(id) ON DELETE CASCADE,
  text TEXT NOT NULL,
  observation_date TIMESTAMP NOT NULL,
  created_at TIMESTAMP DEFAULT now()
);

-- Biblioteca (Livros/Referências)
CREATE TABLE library_items (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID REFERENCES users(id),
  title VARCHAR(255) NOT NULL,
  author VARCHAR(255),
  topic VARCHAR(255),
  summary TEXT,
  rating INTEGER,
  pdf_url VARCHAR(255),  -- URL no Supabase Storage
  created_at TIMESTAMP DEFAULT now()
);

-- Grimórios (Cadernos Temáticos)
CREATE TABLE grimorio_entries (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID REFERENCES users(id),
  grimorio_type VARCHAR(255),  -- Tarô, Sonhos, Cores, etc
  title VARCHAR(255),
  content TEXT,
  entry_date TIMESTAMP NOT NULL,
  tags TEXT[],  -- ARRAY de tags
  created_at TIMESTAMP DEFAULT now()
);

-- Audit Log (LGPD)
CREATE TABLE audit_logs (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID REFERENCES users(id),
  action VARCHAR(255),
  resource_type VARCHAR(255),
  resource_id VARCHAR(255),
  timestamp TIMESTAMP DEFAULT now()
);
```

### Row-Level Security (RLS)

```sql
-- Usuários só veem seus dados
ALTER TABLE symbols ENABLE ROW LEVEL SECURITY;
CREATE POLICY "Users can only see their symbols"
  ON symbols FOR SELECT
  USING (user_id = auth.uid());
```

---

## 🔒 Segurança & LGPD

### Autenticação
- **OAuth2** via Google/GitHub
- **JWT** para sessões
- **NextAuth.js** para facilitar

### Criptografia
- **TLS 1.3** em trânsito
- **AES-256** em repouso (Supabase encrypted columns)
- **Supabase Vault** para secrets

### LGPD Compliance
- ✅ Consentimento explícito no signup
- ✅ Direito ao esquecimento (soft delete + purge após 30 dias)
- ✅ Data residency Brasil (Supabase region)
- ✅ Audit logs de acesso
- ✅ Política de privacidade + Termos

### Rate Limiting
```
- API: 100 req/min por IP
- Auth: 5 tentativas/5 min
- Upload: 100MB/dia por usuário
```

---

## 📊 Performance & Escalabilidade

### Otimizações Planejadas

**Frontend:**
- Code splitting por rota
- Image optimization (WebP)
- Lazy loading de componentes
- Grafo: lazy render de nós (mostrar 100, após scroll carregar mais)

**Backend:**
- GraphQL: seleção de campos (não carrega tudo)
- Índices de banco: búsca + grafo
- Cache Redis: queries frequentes (TTL 1 hora)
- Paginação: sempre paginar resultados

**Banco:**
- Índices em `relations` para grafo rápido
- Particionamento por `user_id` se crescer muito
- Read replicas se houver reads em escala

### Benchmarks Esperados

| Operação | Target | Como Testar |
|----------|--------|-------------|
| Load app | < 3s | Lighthouse |
| Buscar símbolo | < 200ms | API test |
| Renderizar grafo 1000 nós | < 2s | Performance profile |
| Query relacionamentos | < 500ms | GraphQL explorer |

---

## 🚀 Deploy & CI/CD

### Infraestrutura

```
┌─ Frontend (Vercel)
│  ├─ Next.js (web)
│  ├─ Auto-deploy on push
│  └─ CDN global
│
├─ Backend (Railway ou Vercel Functions)
│  ├─ Node.js
│  ├─ Auto-scale
│  └─ Environment variables
│
└─ Database (Supabase Cloud)
   ├─ PostgreSQL managed
   ├─ Automatic backups
   └─ SSL by default
```

### GitHub Workflow

```yaml
name: Deploy
on: [push to main]

jobs:
  lint:
    - Run ESLint
    - Run TypeScript check
    
  test:
    - Run unit tests
    - Run integration tests
    
  deploy:
    - Deploy frontend to Vercel
    - Deploy backend to Railway
    - Run migrations
```

---

## 🔄 Decisões Pendentes (Fase 04)

- [ ] React Native vs Flutter?
- [ ] GraphQL vs REST?
- [ ] Redis via Upstash ou outro provider?
- [ ] S3 vs Supabase Storage para PDFs?
- [ ] Qual lib de grafo? D3 vs Cytoscape vs Vis.js?
- [ ] Kafka para event streaming (quando crescer)?

---

## 📚 Referências & Recursos

- [Supabase Docs](https://supabase.com/docs)
- [React Native Architecture](https://reactnative.dev/docs/architecture-overview)
- [GraphQL Best Practices](https://graphql.org/learn/best-practices)
- [PostreSQL Performance](https://www.postgresql.org/docs/current/performance-tips.html)

---

**Criado em:** 25/07/2026  
**Versão:** 1.0 (Preliminar)  
**Status:** Aguardando aprovação Fase 04  
**Gate:** ⛔ CRÍTICO — Deve ser aprovado antes de desenvolvimento
