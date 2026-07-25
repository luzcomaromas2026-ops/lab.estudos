# 🤝 Guia de Contribuição

**Laboratório de Simbologia — Como Contribuir**

---

## 🚀 Setup Dev Environment

### Pré-requisitos

```bash
Node.js 18+
npm 9+
Git 2.40+
PostgreSQL 14+ (ou Supabase account)
```

### Clone & Install

```bash
git clone https://github.com/seu-repo/lab-simbologia.git
cd lab-simbologia

npm install
cp .env.example .env.local
# Configure DATABASE_URL, JWT_SECRET, etc
```

### Rodando Localmente

```bash
npm run dev

# Frontend: http://localhost:3000
# Backend: http://localhost:3001
# GraphQL: http://localhost:3001/graphql
```

---

## 📋 Fluxo de Contribução

### 1. Escolher Issue

```bash
# Procure issues com label "good first issue" ou "help wanted"
# Comente: "Vou trabalhar nessa"
# Owner confirma: "Vá em frente!"
```

### 2. Criar Branch

```bash
git checkout -b feature/seu-feature
# ou
git checkout -b fix/seu-bug

# Nomes: kebab-case, descritivo
# ✅ feature/map-zoom-controls
# ❌ fix1, new-stuff
```

### 3. Fazer Mudanças

```bash
# Editar código
# Testes? Use:
npm run test

# Linting:
npm run lint

# TypeScript:
npm run type-check
```

### 4. Commit

```bash
git add src/components/MyComponent.tsx
git commit -m "feat: add zoom controls to map

- Implement pinch-zoom for mobile
- Add +/- buttons for desktop
- Ensure accessibility (keyboard shortcuts)

Fixes #123"
```

**Formato:**
```
<type>: <subject>

<body (opcional)>

Fixes #<issue-number>
```

**Types:** feat, fix, docs, style, refactor, test, chore

### 5. Push & PR

```bash
git push origin feature/seu-feature

# GitHub CLI:
gh pr create --title "Add zoom controls" --body "..."
```

**PR Template:**
```markdown
## Descrição
O que foi feito? Por quê?

## Tipo de mudança
- [ ] Feature
- [ ] Bug fix
- [ ] Docs
- [ ] Refactor

## Testes
Como testar? Quais devices/browsers testou?

## Checklist
- [ ] Código passa linting
- [ ] Tests adicionados/atualizados
- [ ] Documentação atualizada
- [ ] Sem secrets em código
- [ ] Acessibilidade checada
```

### 6. Code Review

```
Reviewer comenta
└─ Você responde/ajusta
   └─ Reviewer aprova
      └─ Você faz merge (main -> prod) ou alguém mergieia
```

---

## ✅ Checklist Antes de Submeter

- [ ] `npm run lint` passa
- [ ] `npm run type-check` passa
- [ ] `npm run test` passa
- [ ] Sem console.log() debug
- [ ] Sem comments explicando "óbvio"
- [ ] Acessibilidade: keyboard + screen reader testado
- [ ] Nenhum secret (.env, API keys)
- [ ] Funciona mobile + desktop

---

## 🧪 Testing

### Unit Tests

```bash
npm run test MyComponent.test.tsx

# Watch mode:
npm run test:watch
```

### Integration Tests

```bash
npm run test:integration
```

### E2E Tests (Cypress)

```bash
npm run cypress:open  # UI
npm run cypress:run   # CI
```

---

## 📚 Documentação

Se adicionar feature nova, documente em:

```
docs/04-UX.md          ← User flows
docs/05-Design-System.md ← UI components
docs/12-Glossario.md   ← Novos termos
```

---

## 🔒 Segurança & LGPD

### Não fazer:

```typescript
// ❌ NEVER
const secret = "abc123def456";
const password = userInput;  // Sem sanitize
db.raw(`SELECT * FROM users WHERE id = ${userId}`);  // SQL Injection!
```

### Fazer:

```typescript
// ✅ CORRECT
const secret = process.env.JWT_SECRET;
const sanitized = DOMPurify.sanitize(userInput);
const query = await db.query('SELECT * FROM users WHERE id = ?', [userId]);
```

---

## 🚨 Reporting Bugs

```markdown
## Descrição
[Uma frase clara]

## Steps to Reproduce
1. [Passo 1]
2. [Passo 2]
3. [Resultado inesperado]

## Esperado
[O que deveria acontecer]

## Ambiente
- Device: iPhone 13
- Browser: Safari 15
- App version: 1.0.0-beta.1
```

---

## 💬 Code Review Guidelines

**Para Reviewers:**

```
✅ Ser construtivo, não crítico
✅ Perguntar em vez de afirmar
✅ Celebrar bom código
❌ Bloquear por "preferência de estilo"
❌ Pedir mudanças não relacionadas ao PR
```

**Para Autores:**

```
✅ Responder todas os comentários
✅ Pedir esclarecimento se não entender
✅ Re-request review após mudanças
❌ Ser defensivo
❌ Forçar merge sem acordo
```

---

## 🎓 Learning Resources

```
TypeScript:
└─ https://www.typescriptlang.org/docs/

React Native:
└─ https://reactnative.dev/docs/getting-started

GraphQL:
└─ https://graphql.org/learn/

PostgreSQL:
└─ https://www.postgresql.org/docs/
```

---

## 🆘 Precisa de Help?

```
💬 Slack: #dev-support
📧 Email: dev@lab-simbologia.com
📝 Discussions: GitHub Discussions
```

---

**Criado em:** 25/07/2026  
**Status:** Ativo - atualize conforme necessário
