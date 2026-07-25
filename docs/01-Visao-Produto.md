# 👁️ Visão de Produto

**Laboratório de Simbologia — Documento Executivo**

---

## 🎯 Visão em Uma Frase

Um app mobile que funciona como **Obsidian + Wikipedia pessoal** para pesquisadores de símbolos, permitindo documentar, conectar e descobrir relacionamentos antes invisíveis entre símbolos de forma integrada.

---

## 📊 O Problema

**Pesquisadores em simbologia gastos 5-10 horas/semana em pesquisa fragmentada:**

- 📓 Anotações espalhadas em Notion, Obsidian, papéis
- 🌐 Pesquisas em Wikipedia, blogs, sem integração
- 📖 Livros impressos sem busca cross-tema
- 🔗 Perdem conexões valiosas entre símbolos
- 😤 Retrabalho: pesquisam o mesmo símbolo várias vezes

**Nenhuma ferramenta integra Biblioteca + Grimórios + Fichas + Mapa Visual + Diário**

---

## 💡 A Solução

Um app com 5 módulos conectados (Observatório):

```
📚 BIBLIOTECA      → Centralizar referências
📜 GRIMÓRIOS      → Organizar por tema (9 tipos)
🔍 FICHAS         → Estruturar dados de símbolos
🕸️ MAPA           → Visualizar relacionamentos
🧪 DIÁRIO         → Registrar reflexões pessoais
```

**Core Magic:** O **Mapa de Conexões** mostra padrões que levaria 5 livros para descobrir.

---

## 🎭 Para Quem

**4 Personas:**

1. **O Pesquisador** (5+ anos, 10+ livros)
   - Dor: Sem visualização de conexões
   - Solução: Mapa automático

2. **O Iniciante** (começando, buscando estrutura)
   - Dor: Informação conflitante, onde começar
   - Solução: Grimórios temáticos guiados

3. **O Artista** (criador, usa como referência)
   - Dor: Pesquisa dispersa e lenta
   - Solução: Busca integrada + mapa

4. **O Acadêmico** (pesquisa comparada, precisa rigor)
   - Dor: Ferramentas caras/inflexíveis
   - Solução: Estrutura flexible + export

---

## 🎯 Objetivos (16 semanas até MVP)

| Métrica | Target | Prazo |
|---------|--------|-------|
| **Economia de Tempo** | 5-10h/semana ganhas | 3 meses |
| **Padrões Descobertos** | 3+ relações novas/símbolo | MVP |
| **Early Users** | 50 ativos | Fase 06 |
| **Retenção** | 70%+ após 3 meses | Fase 06 |
| **Satisfação** | NPS > 60 | Q1 2027 |

---

## 🚀 MVP Inclui

✅ Biblioteca (fichas de livros)
✅ Grimórios (9 tipos padrão + custom)
✅ Fichas de Pesquisa (estruturadas)
✅ Mapa de Conexões (core!)
✅ Diário do Laboratório
✅ Auth (OAuth2)
✅ Search + Filter
✅ LGPD Compliant

❌ Comunidade social (v2)
❌ IA Generativa (v2+)
❌ Mobile nativa (React Native v1)
❌ Múltiplas linguagens (v1 é PT-BR)

---

## 🏗️ Stack

- **Frontend:** React Native + Next.js (web)
- **Backend:** Node.js + GraphQL
- **Database:** PostgreSQL (Supabase)
- **Deploy:** Vercel (frontend) + Railway/Vercel Functions
- **Auth:** OAuth2 (Google, GitHub)

---

## 💰 Investimento

**Custo (Fase 05 - Desenvolvimento):**
- 1 Product Manager (você): Flex
- 1 Designer: ~R$15k
- 2-3 Engenheiros: ~R$60k
- Infra: ~R$5k
- **Total: ~R$80k**

**Receita Projetada:**
- v1 MVP: Gratuito (validação)
- v2 (Q2 2027): Freemium (Pro = R$10/mês)
- v3+ (2027): Marketplace, premium features

---

## ⏱️ Timeline

```
25/07    Fase 01 (Contexto) ✅
↓
08/08    Fase 02 (Estrutura Documental)
↓
22/08    Fase 03 (Descoberta do Produto)
↓
15/10    GATE Fase 04 (Arquitetura) ⛔
↓
05/11    Fase 05 (Implementação = 6 semanas)
↓
16/12    🎉 MVP Lançado
↓
05/02    Fase 06 (Evolução & Métricas)
```

---

## 🎨 Identidade Visual

**Observatório:** Navegação central onde 5 módulos orbitam como constelações
**Design:** Minimalista, elegante, sem elementos místicos
**Tipografia:** Inter, Manrope, Geist (sem serifas)
**Ícones:** Traço fino, minimalistas
**Cores:** Neutras + acentos sutis (azul, verde, laranja)

---

## 📈 Métricas de Sucesso

**Quantitativas:**
- Time-to-first-symbol: < 2 minutos
- Criação de ficha completa: < 5 minutos
- Renderização de mapa 1000 nós: < 2 segundos
- Task completion rate: > 90%

**Qualitativas:**
- "Descobri conexões que não sabia"
- "Interface é clara e intuitiva"
- "Fácil navegar entre módulos"
- NPS > 60

---

## ⚠️ Riscos & Mitigações

| Risco | Mitigation |
|-------|-----------|
| Grafo é complexo | Prototipagem D3 Fase 03 |
| Comunidade não adota | Validar com early users Fase 03 |
| LGPD compliance | Audit externo semana 8 |
| Retenção baixa | Onboarding + daily value |

---

## 🎬 Go/No-Go Decision Points

**Fase 04 Gate (15/10):** Deve passar arquitetura técnica
- ✅ Mapa renderiza fluido
- ✅ Segurança validada
- ✅ Tech stack aprovado

Se falhar: Replanejamento ou cancelamento

---

**Criado em:** 25/07/2026  
**Versão:** 1.0  
**Status:** Ativo - Consultado antes de decisões de escopo
