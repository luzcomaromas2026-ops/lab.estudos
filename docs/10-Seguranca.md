# 🔒 Segurança & Compliance (LGPD)

**Laboratório de Simbologia — Política de Segurança**

---

## 📌 Informações Gerais

| Campo | Valor |
|-------|-------|
| **Compliance** | LGPD (Brasil) |
| **Criptografia** | AES-256 em repouso, TLS 1.3 em trânsito |
| **Auth** | OAuth2 + JWT |
| **Audit** | Logs de todas as ações |
| **DPIA** | Realizado antes de produção |

---

## 🚨 Princípios Fundamentais

1. **Privacy by Design** — Privacidade desde o início
2. **Data Minimization** — Coletar apenas necessário
3. **Purpose Limitation** — Usar dados só para o propósito
4. **Accountability** — Rastreabilidade total

---

## 🔐 LGPD Compliance

### Consentimento

**Signup Flow:**
```
1. Usuário vê termos + política de privacidade
2. Marca checkbox "Concordo com os Termos"
3. Confirma email (double opt-in)
4. Dados de consentimento são registrados
```

**Dados Coletados:**
- Email (obrigatório)
- Nome (obrigatório)
- Dados de símbolos (voluntário)

**O que NÃO coletamos:**
- ❌ Localização
- ❌ Dados biométricos
- ❌ Histórico de navegação
- ❌ Dados de terceiros

### Direitos do Usuário

#### 1. Direito de Acesso

```sql
-- Query para exportar tudo de um usuário
SELECT * FROM symbols WHERE user_id = $1;
SELECT * FROM observations WHERE user_id = $1;
SELECT * FROM grimorio_entries WHERE user_id = $1;
SELECT * FROM library_items WHERE user_id = $1;
```

**API:**
```graphql
query ExportMyData {
  me {
    email
    symbols { ... }
    observations { ... }
    grimorio { ... }
  }
}
```

#### 2. Direito ao Esquecimento (Exclusão)

```sql
-- Soft delete (não apaga, marca como deletado)
UPDATE symbols SET deleted_at = now() WHERE user_id = $1;
UPDATE observations SET deleted_at = now() WHERE user_id = $1;

-- Hard delete após 30 dias (irreversível)
DELETE FROM symbols WHERE user_id = $1 AND deleted_at < now() - INTERVAL '30 days';
```

#### 3. Direito de Retificação

```graphql
mutation UpdateMyProfile($input: UpdateProfileInput!) {
  updateProfile(input: $input) {
    email
    name
  }
}
```

#### 4. Direito de Portabilidade

```
GET /api/export/my-data.json
# Retorna JSON com todos os dados do usuário
```

---

## 🔑 Autenticação

### OAuth2 (Recomendado)

```
Provedores:
├── Google
├── GitHub
└── (Microsoft em v2)

Flow:
1. Usuário clica "Login com Google"
2. Redireciona para Google OAuth
3. Google valida
4. Retorna com JWT
5. App armazena JWT no secure storage
```

### JWT

```json
{
  "iss": "https://auth.lab-simbologia.com",
  "sub": "uuid-user",
  "email": "user@example.com",
  "iat": 1656095400,
  "exp": 1656181800,  // 24 horas
  "aud": "app.lab-simbologia.com"
}
```

**Validação:**
```typescript
// Backend valida JWT em cada request
const decoded = jwt.verify(token, process.env.JWT_SECRET);
```

### Session

```
Timeout: 24 horas
Refresh: Automático com novo login
Logout: Invalidar JWT, deletar cookie
```

---

## 🔐 Criptografia

### Em Trânsito (TLS 1.3)

**Todos os requests HTTPS:**
```
Client ──────HTTPS/TLS 1.3────→ Server
              (256-bit encryption)
```

**Certificado:**
- Provedor: Let's Encrypt (gratuito, automático)
- Renewal: Automático (90 dias)
- Policy: Mínimo TLS 1.3

### Em Repouso (AES-256)

**Supabase Encrypted Columns:**
```sql
-- Criptografar campo sensível
CREATE TABLE symbols (
  id UUID PRIMARY KEY,
  name TEXT,
  -- Supabase criptografa automaticamente
  encrypted_data TEXT ENCRYPTED BY SECRET_KEY,
  ...
);
```

**Dados Criptografados:**
- Observações pessoais (Diário)
- PDFs na Biblioteca
- Anotações em Grimórios

**Dados NÃO criptografados (para performance):**
- Nomes de símbolos (precisa ser buscável)
- Tipos de símbolos
- Metadados públicos

---

## 🚨 Auditoria (Audit Logs)

**Tudo é registrado:**

```sql
INSERT INTO audit_logs (user_id, action, resource_type, resource_id, details, ip_address, timestamp)
VALUES ($1, $2, $3, $4, $5, $6, now());
```

**Eventos rastreados:**
- Login / Logout
- Criação de símbolo
- Edição de símbolo
- Deletação de símbolo
- Acesso a dados sensíveis
- Upload de arquivo
- Export de dados

**Retenção:** 2 anos (após 2 anos, purgar)

**Query para auditoria:**
```sql
-- Ver atividades de um usuário
SELECT * FROM audit_logs WHERE user_id = $1 ORDER BY timestamp DESC LIMIT 100;
```

---

## 🔒 Autorização (RBAC)

```
Roles:
├── user (padrão)
│   ├── Ler/editar próprios dados
│   ├── Acessar grafo
│   └── Fazer observações
│
├── admin (futuro)
│   ├── Gerenciar usuários
│   ├── Acessar audit logs
│   └── Moderação
│
└── moderator (futuro)
    ├── Revisar conteúdo
    └── Suporte
```

**Row-Level Security (RLS):**
```sql
-- Usuário só vê seus dados
CREATE POLICY "Users see own symbols"
  ON symbols FOR SELECT
  USING (user_id = auth.uid());
```

---

## 🛡️ Rate Limiting & DDoS

```
Rate Limits:
├── API: 1000 req/min por usuário
├── Auth: 5 tentativas/5 min
├── Upload: 100MB/dia por usuário
└── Download: 1GB/dia por usuário

DDoS Protection:
├── Cloudflare (layer 7)
├── WAF (Web Application Firewall)
└── IP blocking (manual se necessário)
```

---

## 🔑 Gestão de Secrets

**Secrets NÃO vão em código:**
```
❌ Errado:
const SECRET = "abc123def456";

✅ Correto:
const SECRET = process.env.JWT_SECRET;  // Em .env ou Vercel env
```

**Secrets Suportados:**
- JWT_SECRET
- DATABASE_URL
- OAUTH_GOOGLE_ID
- OAUTH_GOOGLE_SECRET
- STRIPE_API_KEY (futuro)

**Rotação:** A cada 90 dias

---

## 🧪 Testes de Segurança

**Antes de produção:**

```bash
# 1. OWASP Top 10
☐ SQL Injection (usar ORMs/prepared statements)
☐ XSS (sanitizar input)
☐ CSRF (tokens CSRF)
☐ Authentication bypass
☐ Privilege escalation
☐ Insecure deserialization
☐ XXE (XML External Entity)
☐ Insecure Direct Object References (IDOR)
☐ Insufficient logging & monitoring
☐ Using components with known vulnerabilities

# 2. Penetration Testing
☐ Teste manual por security firm

# 3. Dependency Scanning
☐ npm audit
☐ snyk.io (CI/CD)

# 4. Static Analysis
☐ Sonarqube
☐ ESLint security plugins
```

---

## 📋 LGPD Checklist

### Antes de Produção

- [ ] Termo de Serviço atualizado
- [ ] Política de Privacidade (português claro)
- [ ] Data Processing Agreement (DPA)
- [ ] DPIA (Data Protection Impact Assessment)
- [ ] Gestão de consentimento implementada
- [ ] Direito ao esquecimento implementado
- [ ] Export de dados implementado
- [ ] Audit logs funcionando
- [ ] Criptografia em repouso + trânsito
- [ ] Pentesting realizado
- [ ] Data Officer designado
- [ ] Contato de privacidade publicado (privacy@lab-simbologia.com)

### Anual

- [ ] Audit externo de segurança
- [ ] Revisão de policies
- [ ] Treinamento de team sobre LGPD
- [ ] Teste de disaster recovery
- [ ] Revisão de vendor compliance

---

## 🚨 Incident Response

**Se houver breach:**

```
1. Detectar (automated alerts + manual review)
   └─ Verificar audit logs

2. Contenção (< 1 hora)
   └─ Isolar sistema afetado
   └─ Revocar credenciais comprometidas

3. Investigação (< 24 horas)
   └─ Quais dados foram afetados?
   └─ Quem acessou?
   └─ Como entrou?

4. Notificação (< 72 horas)
   └─ Notificar usuários afetados
   └─ Notificar autoridades (ANPD)
   └─ Publicar comunicado

5. Recovery (contínuo)
   └─ Patchear vulnerabilidade
   └─ Monitorar revolta
   └─ Suporte a usuários

6. Learning
   └─ Post-mortem interno
   └─ Atualizar policies
```

---

## 📞 Contato de Privacidade

**Email:** privacy@lab-simbologia.com  
**Resposta SLA:** 48 horas

**Assuntos:**
- Pedidos de acesso
- Pedidos de exclusão
- Reclamações de privacidade
- Notificação de breach (interno)

---

## 📚 Referências Legais

- [LGPD - Lei 13.709/2018](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.html)
- [ANPD - Autoridade Nacional de Proteção de Dados](https://www.gov.br/cidadania/pt-br/acesso-a-informacao/lgpd)
- [GDPR (referência internacional)](https://gdpr-info.eu/)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)

---

## 🎯 Princípios de Segurança (Desenvolvimento)

```typescript
// ✅ CORRETO
const user = await db.symbols.findMany({
  where: { userId: auth.uid() }  // Filtrar por user
});

// ❌ ERRADO
const user = await db.symbols.findMany();  // Tudo!
```

```typescript
// ✅ CORRETO
const input = sanitizeHTML(userInput);
db.save(input);

// ❌ ERRADO
db.save(userInput);  // XSS!
```

```sql
-- ✅ CORRETO (prepared statement)
SELECT * FROM symbols WHERE user_id = $1 AND name = $2;

-- ❌ ERRADO (SQL Injection!)
SELECT * FROM symbols WHERE user_id = ${userId} AND name = '${name}';
```

---

**Criado em:** 25/07/2026  
**Versão:** 1.0  
**Status:** Implementação Fase 05
