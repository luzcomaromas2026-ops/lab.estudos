# 🗄️ Banco de Dados

**Schema PostgreSQL — Laboratório de Simbologia**

---

## 📌 Informações Gerais

| Campo | Valor |
|-------|-------|
| **Engine** | PostgreSQL (via Supabase) |
| **ORM** | Prisma ou Raw SQL |
| **Timezone** | UTC |
| **Encoding** | UTF-8 |
| **Backup** | Automático (Supabase) |

---

## 🗂️ Tabelas Principais

### 1. `users` — Usuários (Autenticação)

```sql
CREATE TABLE users (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  email VARCHAR(255) UNIQUE NOT NULL,
  name VARCHAR(255) NOT NULL,
  avatar_url VARCHAR(255),
  auth_provider VARCHAR(50),  -- 'google', 'github'
  auth_provider_id VARCHAR(255),
  created_at TIMESTAMP DEFAULT now(),
  updated_at TIMESTAMP DEFAULT now(),
  
  CHECK (auth_provider IN ('google', 'github'))
);

CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_users_auth ON users(auth_provider, auth_provider_id);
```

---

### 2. `symbols` — Símbolos

```sql
CREATE TABLE symbols (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  name VARCHAR(255) NOT NULL,
  description TEXT,
  types TEXT[] NOT NULL,  -- ARRAY de tipos
  created_at TIMESTAMP DEFAULT now(),
  updated_at TIMESTAMP DEFAULT now(),
  
  CHECK (array_length(types, 1) > 0),
  
  -- Cada usuário tem nome de símbolo único
  UNIQUE(user_id, name)
);

CREATE INDEX idx_symbols_user ON symbols(user_id);
CREATE INDEX idx_symbols_name ON symbols(name);
```

**Tipos Válidos:**
```sql
-- Check que garante tipos válidos
ALTER TABLE symbols ADD CONSTRAINT valid_types CHECK (
  types <@ ARRAY['animal', 'divindade', 'carta', 'elemento', 'cor', 
                   'numero', 'planta', 'cristal', 'lugar', 'acao', 
                   'arquetipo', 'geometria']::text[]
);
```

---

### 3. `meanings` — Significados de Símbolos

```sql
CREATE TABLE meanings (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  symbol_id UUID NOT NULL REFERENCES symbols(id) ON DELETE CASCADE,
  meaning TEXT NOT NULL,
  tradition VARCHAR(255),      -- Ex: "Mitologia Grega"
  context TEXT,                 -- Contexto do significado
  source VARCHAR(255),          -- Livro/artigo
  created_at TIMESTAMP DEFAULT now(),
  updated_at TIMESTAMP DEFAULT now()
);

CREATE INDEX idx_meanings_symbol ON meanings(symbol_id);
```

**Exemplo:**
```sql
INSERT INTO meanings (symbol_id, meaning, tradition, context, source)
VALUES (
  'uuid-coruja',
  'Sabedoria',
  'Mitologia Grega',
  'Atena é a deusa da sabedoria e tem coruja como símbolo',
  'Bulfinch''s Mythology'
);
```

---

### 4. `relations` — Relacionamentos (CORE DO GRAFO!)

```sql
CREATE TABLE relations (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  origin_symbol_id UUID NOT NULL REFERENCES symbols(id) ON DELETE CASCADE,
  target_symbol_id UUID NOT NULL REFERENCES symbols(id) ON DELETE CASCADE,
  relation_type VARCHAR(50) NOT NULL,
  description TEXT,
  created_at TIMESTAMP DEFAULT now(),
  
  -- Evitar duplicatas
  UNIQUE(origin_symbol_id, target_symbol_id, relation_type),
  
  -- Validação de tipos
  CHECK (relation_type IN (
    'origem_de', 'equivalente_a', 'oposto_de', 'complementar_de',
    'aspecto_de', 'governado_por', 'habita', 'relacionado_psicologicamente',
    'sincronicidade_com', 'expressa_qualidade_de'
  ))
);

-- ÍNDICES CRÍTICOS PARA PERFORMANCE DE GRAFO
CREATE INDEX idx_relations_origin ON relations(origin_symbol_id);
CREATE INDEX idx_relations_target ON relations(target_symbol_id);
CREATE INDEX idx_relations_type ON relations(relation_type);
CREATE INDEX idx_relations_both ON relations(origin_symbol_id, target_symbol_id);
```

**Query de Exemplo (buscar todas conexões de um símbolo):**
```sql
-- Buscar todos os símbolos conectados a "Lua"
SELECT 
  rs.id as symbol_id,
  rs.name,
  r.relation_type,
  r.description
FROM relations r
JOIN symbols rs ON (r.target_symbol_id = rs.id OR r.origin_symbol_id = rs.id)
WHERE (r.origin_symbol_id = $1 OR r.target_symbol_id = $1)
  AND rs.id != $1;
```

---

### 5. `contexts` — Contextos (Aparece em)

```sql
CREATE TABLE contexts (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  symbol_id UUID NOT NULL REFERENCES symbols(id) ON DELETE CASCADE,
  context_type VARCHAR(255) NOT NULL,  -- Ex: "Mitologia Grega"
  description TEXT,
  created_at TIMESTAMP DEFAULT now(),
  
  UNIQUE(symbol_id, context_type)
);

CREATE INDEX idx_contexts_symbol ON contexts(symbol_id);
CREATE INDEX idx_contexts_type ON contexts(context_type);
```

---

### 6. `observations` — Observações Pessoais (Diário)

```sql
CREATE TABLE observations (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  symbol_id UUID REFERENCES symbols(id) ON DELETE CASCADE,
  text TEXT NOT NULL,
  observation_date DATE NOT NULL,
  created_at TIMESTAMP DEFAULT now(),
  updated_at TIMESTAMP DEFAULT now()
);

CREATE INDEX idx_observations_user ON observations(user_id);
CREATE INDEX idx_observations_date ON observations(observation_date);
CREATE INDEX idx_observations_symbol ON observations(symbol_id);
```

---

### 7. `library_items` — Biblioteca (Livros/Referências)

```sql
CREATE TABLE library_items (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  title VARCHAR(255) NOT NULL,
  author VARCHAR(255),
  topic VARCHAR(255),
  summary TEXT,
  rating INTEGER CHECK (rating >= 0 AND rating <= 5),
  pdf_url VARCHAR(512),  -- URL no Supabase Storage
  created_at TIMESTAMP DEFAULT now(),
  updated_at TIMESTAMP DEFAULT now()
);

CREATE INDEX idx_library_user ON library_items(user_id);
CREATE INDEX idx_library_author ON library_items(author);
CREATE INDEX idx_library_topic ON library_items(topic);
```

---

### 8. `grimorio_entries` — Grimórios (Cadernos Temáticos)

```sql
CREATE TABLE grimorio_entries (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  grimorio_type VARCHAR(255) NOT NULL,  -- "Tarô", "Sonhos", etc
  title VARCHAR(255) NOT NULL,
  content TEXT NOT NULL,
  entry_date DATE NOT NULL,
  tags TEXT[],  -- ARRAY de tags
  created_at TIMESTAMP DEFAULT now(),
  updated_at TIMESTAMP DEFAULT now(),
  
  -- Validação de tipos
  CHECK (grimorio_type IN (
    'tarot', 'sonhos', 'cores', 'animais', 'arquetipos',
    'mitologia', 'alquimia', 'religioes', 'psicologia', 'custom'
  ))
);

CREATE INDEX idx_grimorio_user ON grimorio_entries(user_id);
CREATE INDEX idx_grimorio_type ON grimorio_entries(grimorio_type);
CREATE INDEX idx_grimorio_date ON grimorio_entries(entry_date);
```

---

### 9. `study_records` — Registro de Estudos (Subsegmento de Grimórios)

```sql
CREATE TABLE study_records (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  grimorio_entry_id UUID NOT NULL REFERENCES grimorio_entries(id) ON DELETE CASCADE,
  
  objective TEXT NOT NULL,                    -- Objetivo do estudo (ex: "Memorizar 22 Arcanos")
  status VARCHAR(50) NOT NULL DEFAULT 'pendente',  -- pendente | em_progresso | concluído
  progress INT DEFAULT 0,                     -- 0-100: Percentual de conclusão
  
  date_started DATE NOT NULL,
  date_completed DATE,
  hours_invested DECIMAL(10, 2) DEFAULT 0,    -- Horas totais investidas
  
  main_learnings TEXT[] DEFAULT '{}',         -- ARRAY de aprendizados principais
  next_steps TEXT[] DEFAULT '{}',             -- ARRAY de próximos passos
  
  created_at TIMESTAMP DEFAULT now(),
  updated_at TIMESTAMP DEFAULT now(),
  
  -- Validações
  CHECK (status IN ('pendente', 'em_progresso', 'concluído')),
  CHECK (progress >= 0 AND progress <= 100),
  CHECK (date_completed IS NULL OR date_completed >= date_started),
  CHECK (hours_invested >= 0)
);

CREATE INDEX idx_study_user ON study_records(user_id);
CREATE INDEX idx_study_grimorio ON study_records(grimorio_entry_id);
CREATE INDEX idx_study_status ON study_records(status);
```

**Exemplo:**
```sql
INSERT INTO study_records (
  user_id, grimorio_entry_id, objective, status, progress, 
  date_started, hours_invested, main_learnings, next_steps
) VALUES (
  'user-123',
  'entrada-42',
  'Memorizar os 22 Arcanos Maiores',
  'em_progresso',
  65,
  '2026-07-25',
  8.5,
  ARRAY[
    'O Louco = Inocência, Novo Começo',
    'O Mago = Manifestação, Poder Pessoal',
    'A Sacerdotisa = Intuição, Mistério'
  ],
  ARRAY[
    'Estudar Arcanos Menores',
    'Explorar spreads complexos',
    'Comparar com Cábala'
  ]
);
```

---

### 10. `audit_logs` — Logs de Auditoria (LGPD)

```sql
CREATE TABLE audit_logs (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID REFERENCES users(id),
  action VARCHAR(255) NOT NULL,          -- 'create', 'update', 'delete'
  resource_type VARCHAR(255) NOT NULL,   -- 'symbol', 'meaning', etc
  resource_id VARCHAR(255),
  details JSONB,  -- Dados adicionais
  ip_address INET,
  timestamp TIMESTAMP DEFAULT now(),
  
  CHECK (action IN ('create', 'read', 'update', 'delete', 'login', 'logout'))
);

CREATE INDEX idx_audit_user ON audit_logs(user_id);
CREATE INDEX idx_audit_timestamp ON audit_logs(timestamp);
CREATE INDEX idx_audit_action ON audit_logs(action);
```

---

## 🔒 Row-Level Security (RLS)

Protege dados: cada usuário só vê seus dados.

```sql
-- Ativar RLS
ALTER TABLE symbols ENABLE ROW LEVEL SECURITY;
ALTER TABLE meanings ENABLE ROW LEVEL SECURITY;
ALTER TABLE relations ENABLE ROW LEVEL SECURITY;
ALTER TABLE contexts ENABLE ROW LEVEL SECURITY;
ALTER TABLE observations ENABLE ROW LEVEL SECURITY;
ALTER TABLE library_items ENABLE ROW LEVEL SECURITY;
ALTER TABLE grimorio_entries ENABLE ROW LEVEL SECURITY;
ALTER TABLE study_records ENABLE ROW LEVEL SECURITY;

-- Policy: Usuários veem só seus símbolos
CREATE POLICY "Users see own symbols"
  ON symbols FOR SELECT
  USING (user_id = auth.uid());

CREATE POLICY "Users insert own symbols"
  ON symbols FOR INSERT
  WITH CHECK (user_id = auth.uid());

CREATE POLICY "Users update own symbols"
  ON symbols FOR UPDATE
  USING (user_id = auth.uid());

-- Cascade para meanings (vê meanings dos seus symbols)
CREATE POLICY "Users see own meanings"
  ON meanings FOR SELECT
  USING (
    symbol_id IN (
      SELECT id FROM symbols WHERE user_id = auth.uid()
    )
  );
```

---

## 📊 Diagrama ER (Simplificado)

```
users
├── 1 ── ∞ symbols
│         ├── 1 ── ∞ meanings
│         ├── 1 ── ∞ relations (origin)
│         ├── 1 ── ∞ relations (target)
│         ├── 1 ── ∞ contexts
│         └── ? ── observations
├── 1 ── ∞ observations
├── 1 ── ∞ library_items
├── 1 ── ∞ grimorio_entries
│         └── 1 ── ∞ study_records (Registro de Estudos)
└── 1 ── ∞ audit_logs
```

---

## 📈 Índices de Performance

```sql
-- CRÍTICOS para Grafo
CREATE INDEX idx_relations_origin ON relations(origin_symbol_id);
CREATE INDEX idx_relations_target ON relations(target_symbol_id);
CREATE INDEX idx_relations_type ON relations(relation_type);

-- CRÍTICOS para Busca
CREATE INDEX idx_symbols_name_search ON symbols USING GIN(to_tsvector('portuguese', name));

-- CRÍTICOS para User Data
CREATE INDEX idx_symbols_user ON symbols(user_id);
CREATE INDEX idx_observations_date ON observations(observation_date);

-- CRÍTICOS para Audit
CREATE INDEX idx_audit_timestamp ON audit_logs(timestamp);
```

---

## 🔐 Segurança

### Soft Delete (Direito ao Esquecimento - LGPD)

```sql
-- Adicionar coluna de soft delete
ALTER TABLE symbols ADD COLUMN deleted_at TIMESTAMP DEFAULT NULL;

-- Política: usuários não veem deletados
CREATE POLICY "Hide deleted symbols"
  ON symbols FOR SELECT
  USING (deleted_at IS NULL);

-- Trigger: soft delete
CREATE OR REPLACE FUNCTION soft_delete_symbol(id UUID)
RETURNS void AS $$
BEGIN
  UPDATE symbols SET deleted_at = now() WHERE id = $1;
  UPDATE meanings SET deleted_at = now() WHERE symbol_id = $1;
END;
$$ LANGUAGE plpgsql;
```

### Audit de Todas as Mudanças

```sql
-- Trigger automático para audit_logs
CREATE OR REPLACE FUNCTION log_audit()
RETURNS TRIGGER AS $$
BEGIN
  INSERT INTO audit_logs (user_id, action, resource_type, resource_id, details, timestamp)
  VALUES (
    auth.uid(),
    TG_OP,
    TG_TABLE_NAME,
    NEW.id::text,
    row_to_json(NEW),
    now()
  );
  RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER audit_symbols AFTER INSERT OR UPDATE OR DELETE ON symbols
  FOR EACH ROW EXECUTE FUNCTION log_audit();
```

---

## 📦 Migrations (Prisma Schema Exemplo)

```prisma
datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}

generator client {
  provider = "prisma-client-js"
}

model User {
  id        String     @id @default(cuid())
  email     String     @unique
  name      String
  symbols   Symbol[]
  audit     AuditLog[]
}

model Symbol {
  id          String      @id @default(cuid())
  userId      String
  user        User        @relation(fields: [userId], references: [id], onDelete: Cascade)
  name        String
  types       String[]
  meanings    Meaning[]
  relationsFrom Relation[] @relation("from")
  relationsTo   Relation[] @relation("to")
  contexts    Context[]
  
  @@unique([userId, name])
  @@index([userId])
  @@index([name])
}

model Relation {
  id               String   @id @default(cuid())
  originSymbolId   String
  originSymbol     Symbol   @relation("from", fields: [originSymbolId], references: [id], onDelete: Cascade)
  targetSymbolId   String
  targetSymbol     Symbol   @relation("to", fields: [targetSymbolId], references: [id], onDelete: Cascade)
  relationType     String   // origem_de, equivalente_a, etc
  description      String?
  
  @@unique([originSymbolId, targetSymbolId, relationType])
  @@index([originSymbolId])
  @@index([targetSymbolId])
}

// ... outros modelos
```

---

## 🧪 Testes de Performance

```sql
-- Query de grafo grande (10k símbolos)
EXPLAIN ANALYZE
SELECT * FROM relations
WHERE origin_symbol_id = 'uuid-lua'
LIMIT 1000;

-- Search full-text
EXPLAIN ANALYZE
SELECT * FROM symbols
WHERE to_tsvector('portuguese', name) @@ to_tsquery('portuguese', 'lua');
```

---

## 💾 Backup & Restore

```bash
# Supabase faz backup automático
# Mas você pode fazer manual:

# Exportar
pg_dump --url $DATABASE_URL --format custom > backup.dump

# Restaurar
pg_restore --url $DATABASE_URL --clean < backup.dump
```

---

**Criado em:** 25/07/2026  
**Versão:** 1.0  
**Status:** Implementação Fase 05
