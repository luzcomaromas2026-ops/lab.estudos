# 🔌 API Reference

**Laboratório de Simbologia — GraphQL API**

---

## 📌 Informações Gerais

| Campo | Valor |
|-------|-------|
| **Base URL** | `https://api.lab-simbologia.com` |
| **API Style** | GraphQL (recomendado) + REST fallback |
| **Auth** | OAuth2 + JWT |
| **Rate Limit** | 1000 req/min por usuário |
| **Timeout** | 30s |

---

## 🔑 Autenticação

### Login

```graphql
mutation Login($email: String!, $provider: String!) {
  login(email: $email, provider: $provider) {
    token
    user {
      id
      email
      name
    }
  }
}
```

### Headers

```
Authorization: Bearer <JWT_TOKEN>
Content-Type: application/json
```

---

## 📡 GraphQL Endpoints

### Schema Completo

```graphql
type User {
  id: ID!
  email: String!
  name: String!
  avatarUrl: String
  createdAt: DateTime!
  symbols: [Symbol!]!
  observations: [Observation!]!
}

type Symbol {
  id: ID!
  name: String!
  types: [SymbolType!]!
  description: String
  meanings: [Meaning!]!
  relationsFrom: [Relation!]!  # Símbolos que ele conecta
  relationsTo: [Relation!]!    # Símbolos que conectam nele
  contexts: [Context!]!
  createdAt: DateTime!
  updatedAt: DateTime!
}

enum SymbolType {
  ANIMAL
  DIVINDADE
  CARTA
  ELEMENTO
  COR
  NUMERO
  PLANTA
  CRISTAL
  LUGAR
  ACAO
  ARQUETIPO
  GEOMETRIA
}

type Meaning {
  id: ID!
  symbolId: ID!
  meaning: String!
  tradition: String
  context: String
  source: String
  createdAt: DateTime!
}

type Relation {
  id: ID!
  originSymbolId: ID!
  originSymbol: Symbol!
  targetSymbolId: ID!
  targetSymbol: Symbol!
  relationType: RelationType!
  description: String
  createdAt: DateTime!
}

enum RelationType {
  ORIGEM_DE
  EQUIVALENTE_A
  OPOSTO_DE
  COMPLEMENTAR_DE
  ASPECTO_DE
  GOVERNADO_POR
  HABITA
  RELACIONADO_PSICOLOGICAMENTE
  SINCRONICIDADE_COM
  EXPRESSA_QUALIDADE_DE
}

type Context {
  id: ID!
  symbolId: ID!
  contextType: String!  # "Mitologia Grega", "Tarô", etc
  description: String
  createdAt: DateTime!
}

type Observation {
  id: ID!
  userId: ID!
  symbolId: ID
  text: String!
  observationDate: Date!
  createdAt: DateTime!
}

type LibraryItem {
  id: ID!
  title: String!
  author: String
  topic: String
  summary: String
  rating: Int
  pdfUrl: String
  createdAt: DateTime!
}

type GrimorioEntry {
  id: ID!
  grimorioType: String!  # "Tarô", "Sonhos", etc
  title: String!
  content: String!
  entryDate: Date!
  tags: [String!]!
  studyRecord: StudyRecord  # Subsegmento opcional
  createdAt: DateTime!
  updatedAt: DateTime!
}

type StudyRecord {
  id: ID!
  grimorioEntryId: ID!
  objective: String!
  status: StudyStatus!  # pendente | em_progresso | concluído
  progress: Int!  # 0-100
  dateStarted: Date!
  dateCompleted: Date
  hoursInvested: Float!
  mainLearnings: [String!]!
  nextSteps: [String!]!
  createdAt: DateTime!
  updatedAt: DateTime!
}

enum StudyStatus {
  PENDENTE
  EM_PROGRESSO
  CONCLUIDO
}

type Graph {
  nodes: [GraphNode!]!
  edges: [GraphEdge!]!
}

type GraphNode {
  id: ID!
  label: String!
  type: String!
  symbolTypes: [SymbolType!]!
}

type GraphEdge {
  source: ID!
  target: ID!
  relationshipType: RelationType!
}

# QUERIES
type Query {
  # Usuário
  me: User!
  
  # Símbolos
  symbol(id: ID!): Symbol
  symbols(limit: Int = 20, offset: Int = 0): [Symbol!]!
  searchSymbols(term: String!, limit: Int = 10): [Symbol!]!
  
  # Grafo
  graph(symbolId: ID!, depth: Int = 1): Graph!
  
  # Contextos
  contexts(symbolId: ID!): [Context!]!
  
  # Observações
  observations(limit: Int = 50, offset: Int = 0): [Observation!]!
  observationsBySymbol(symbolId: ID!): [Observation!]!
  
  # Biblioteca
  libraryItems(limit: Int = 20, offset: Int = 0): [LibraryItem!]!
  libraryItem(id: ID!): LibraryItem
  
  # Grimórios
  grimorioEntries(grimorioType: String!, limit: Int = 20): [GrimorioEntry!]!
  grimorioEntry(id: ID!): GrimorioEntry
  
  # Registro de Estudos
  studyRecords(status: StudyStatus, limit: Int = 20): [StudyRecord!]!
  studyRecord(id: ID!): StudyRecord
  studyRecordsByGrimorio(grimorioEntryId: ID!): [StudyRecord!]!
}

# MUTATIONS
type Mutation {
  # Símbolos
  createSymbol(input: CreateSymbolInput!): Symbol!
  updateSymbol(id: ID!, input: UpdateSymbolInput!): Symbol!
  deleteSymbol(id: ID!): Boolean!
  
  # Significados
  addMeaning(symbolId: ID!, input: AddMeaningInput!): Meaning!
  removeMeaning(id: ID!): Boolean!
  
  # Relações
  addRelation(input: AddRelationInput!): Relation!
  removeRelation(id: ID!): Boolean!
  
  # Contextos
  addContext(symbolId: ID!, contextType: String!): Context!
  
  # Observações
  addObservation(input: AddObservationInput!): Observation!
  updateObservation(id: ID!, text: String!): Observation!
  deleteObservation(id: ID!): Boolean!
  
  # Biblioteca
  addLibraryItem(input: AddLibraryItemInput!): LibraryItem!
  updateLibraryItem(id: ID!, input: UpdateLibraryItemInput!): LibraryItem!
  deleteLibraryItem(id: ID!): Boolean!
  
  # Grimórios
  addGrimorioEntry(input: AddGrimorioEntryInput!): GrimorioEntry!
  updateGrimorioEntry(id: ID!, input: UpdateGrimorioEntryInput!): GrimorioEntry!
  deleteGrimorioEntry(id: ID!): Boolean!
  
  # Registro de Estudos
  addStudyRecord(input: AddStudyRecordInput!): StudyRecord!
  updateStudyRecord(id: ID!, input: UpdateStudyRecordInput!): StudyRecord!
  deleteStudyRecord(id: ID!): Boolean!
}

# INPUT TYPES
input CreateSymbolInput {
  name: String!
  types: [SymbolType!]!
  description: String
}

input UpdateSymbolInput {
  name: String
  types: [SymbolType!]
  description: String
}

input AddMeaningInput {
  meaning: String!
  tradition: String
  context: String
  source: String
}

input AddRelationInput {
  originSymbolId: ID!
  targetSymbolId: ID!
  relationType: RelationType!
  description: String
}

input AddObservationInput {
  symbolId: ID
  text: String!
  observationDate: Date!
}

input AddLibraryItemInput {
  title: String!
  author: String
  topic: String
  summary: String
  rating: Int
  pdfUrl: String
}

input AddGrimorioEntryInput {
  grimorioType: String!
  title: String!
  content: String!
  entryDate: Date!
  tags: [String!]
}

input UpdateGrimorioEntryInput {
  title: String
  content: String
  entryDate: Date
  tags: [String!]
}

input AddStudyRecordInput {
  grimorioEntryId: ID!
  objective: String!
  status: StudyStatus = PENDENTE
  progress: Int = 0
  dateStarted: Date!
  dateCompleted: Date
  hoursInvested: Float = 0
  mainLearnings: [String!] = []
  nextSteps: [String!] = []
}

input UpdateStudyRecordInput {
  objective: String
  status: StudyStatus
  progress: Int
  dateCompleted: Date
  hoursInvested: Float
  mainLearnings: [String!]
  nextSteps: [String!]
}
```

---

## 📝 Exemplos de Queries

### Buscar símbolo com todas suas conexões

```graphql
query GetSymbolWithGraph($symbolId: ID!) {
  symbol(id: $symbolId) {
    id
    name
    types
    meanings {
      meaning
      tradition
      source
    }
    relationsFrom {
      targetSymbol {
        id
        name
      }
      relationType
      description
    }
    relationsTo {
      originSymbol {
        id
        name
      }
      relationType
    }
    contexts {
      contextType
      description
    }
  }
}

# Variáveis
{
  "symbolId": "uuid-lua"
}
```

### Buscar grafo completo (para visualização)

```graphql
query GetGraph($symbolId: ID!, $depth: Int) {
  graph(symbolId: $symbolId, depth: $depth) {
    nodes {
      id
      label
      type
    }
    edges {
      source
      target
      relationshipType
    }
  }
}
```

### Criar novo símbolo com significados

```graphql
mutation CreateSymbolWithMeanings($input: CreateSymbolInput!, $meanings: [AddMeaningInput!]!) {
  createSymbol(input: $input) {
    id
    name
    meanings {
      meaning
      tradition
    }
  }
}

# Variáveis
{
  "input": {
    "name": "Ametista",
    "types": ["CRISTAL", "ELEMENTO"],
    "description": "Cristal roxo de proteção"
  }
}
```

### Adicionar observação pessoal (Diário)

```graphql
mutation AddDiaryEntry($input: AddObservationInput!) {
  addObservation(input: $input) {
    id
    text
    observationDate
    createdAt
  }
}

# Variáveis
{
  "input": {
    "symbolId": "uuid-lua",
    "text": "Encontrei relação entre Lua e A Sacerdotisa. Ambas = conhecimento oculto.",
    "observationDate": "2026-07-25"
  }
}
```

### Criar Registro de Estudo em Grimório

```graphql
mutation CreateStudyRecord($input: AddStudyRecordInput!) {
  addStudyRecord(input: $input) {
    id
    objective
    status
    progress
    dateStarted
    hoursInvested
    mainLearnings
    nextSteps
    createdAt
  }
}

# Variáveis
{
  "input": {
    "grimorioEntryId": "entrada-42",
    "objective": "Memorizar os 22 Arcanos Maiores e seus significados em 4 tradições",
    "status": "EM_PROGRESSO",
    "progress": 65,
    "dateStarted": "2026-07-25",
    "hoursInvested": 8.5,
    "mainLearnings": [
      "O Louco = Inocência, Novo Começo",
      "O Mago = Manifestação, Poder Pessoal",
      "A Sacerdotisa = Intuição, Mistério"
    ],
    "nextSteps": [
      "Estudar Arcanos Menores (Espadas, Copas, Ouros, Paus)",
      "Explorar spreads mais complexos",
      "Comparar Tarot com Cábala (Árvore da Vida)"
    ]
  }
}
```

### Atualizar Progresso de Estudo

```graphql
mutation UpdateProgress($id: ID!, $input: UpdateStudyRecordInput!) {
  updateStudyRecord(id: $id, input: $input) {
    id
    progress
    hoursInvested
    mainLearnings
    status
    updatedAt
  }
}

# Variáveis
{
  "id": "study-42",
  "input": {
    "progress": 100,
    "status": "CONCLUIDO",
    "dateCompleted": "2026-08-01",
    "hoursInvested": 15.0,
    "mainLearnings": [
      "22 Arcanos Maiores aprendidos",
      "Conexões com Cábala identificadas",
      "Significados em 4 tradições consolidados"
    ]
  }
}
```

---

## 🔄 REST Fallback

Se preferir REST, tenemos estes endpoints:

```
# Símbolos
GET    /api/symbols                    # Listar
GET    /api/symbols/:id                # Detalhe
POST   /api/symbols                    # Criar
PUT    /api/symbols/:id                # Atualizar
DELETE /api/symbols/:id                # Deletar

# Busca
GET    /api/symbols/search?term=lua

# Grafo
GET    /api/symbols/:id/graph?depth=1

# Significados
POST   /api/symbols/:id/meanings
GET    /api/symbols/:id/meanings

# Relações
POST   /api/relations
GET    /api/relations?origin=:id

# Observações
GET    /api/observations
POST   /api/observations
```

---

## 📊 Respostas Padrão

### Sucesso

```json
{
  "data": {
    "symbol": {
      "id": "uuid-lua",
      "name": "Lua",
      "types": ["DIVINDADE", "ELEMENTO", "ARQUETIPO"]
    }
  }
}
```

### Erro

```json
{
  "errors": [
    {
      "message": "Symbol not found",
      "extensions": {
        "code": "NOT_FOUND",
        "statusCode": 404
      }
    }
  ]
}
```

### Paginação

```json
{
  "data": {
    "symbols": [
      { "id": "1", "name": "Lua" },
      { "id": "2", "name": "Sol" }
    ],
    "pageInfo": {
      "totalCount": 1000,
      "hasNextPage": true,
      "endCursor": "abc123"
    }
  }
}
```

---

## ⚡ Rate Limiting

```
Rate Limit: 1000 req/min
Remaining: 999
Reset: 2026-07-25T23:57:00Z
```

Headers retornados:
```
X-RateLimit-Limit: 1000
X-RateLimit-Remaining: 999
X-RateLimit-Reset: 1656099420
```

---

## 🔍 Error Codes

| Code | Meaning | HTTP |
|------|---------|------|
| `UNAUTHORIZED` | Sem autenticação | 401 |
| `FORBIDDEN` | Sem permissão | 403 |
| `NOT_FOUND` | Recurso não existe | 404 |
| `VALIDATION_ERROR` | Input inválido | 400 |
| `CONFLICT` | Violação de constraint | 409 |
| `RATE_LIMITED` | Limite excedido | 429 |
| `INTERNAL_ERROR` | Erro interno | 500 |

---

## 📚 Webhooks (v2)

```
POST /webhooks/symbol:created
POST /webhooks/symbol:updated
POST /webhooks/relation:added
POST /webhooks/observation:added
```

---

## 🧪 Testing

```bash
# Query com curl
curl -X POST https://api.lab-simbologia.com/graphql \
  -H "Authorization: Bearer TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "query": "query { symbol(id: \"uuid\") { id name } }"
  }'
```

---

**Criado em:** 25/07/2026  
**Versão:** 1.0  
**Status:** Implementação Fase 05
