# 📖 Laboratório de Simbologia

> Um app mobile que funciona como **Obsidian + Wikipedia pessoal** para pesquisadores de símbolos, tarô, mitologia, alquimia e psicologia junguiana.

**Integra:** Biblioteca, Grimórios temáticos, Fichas de Pesquisa, Mapa Visual de Conexões e Diário do Laboratório.

---

## 📜 Documentos Fundamentais

### **MANIFESTO.md** — Por que existe
Propósito, missão, visão, valores, o que é/não é, público-alvo, princípios, limites éticos.
**Impede que o projeto perca sua identidade.**

### **ONTOLOGIA.md** — Como funciona (O CORAÇÃO)
Define a estrutura de dados fundamental que torna possível o Mapa de Conexões.
- É um → Tipos de símbolos
- Representa → Significados
- Relacionado a → Grafo de conexões
- Aparece em → Contextos
- Origem → Rastreabilidade histórica
- Observações → Seu insight pessoal

**Esta é a diferença entre um app genérico e uma ferramenta de descoberta.**

---

## 🎯 Visão em Uma Frase

Criar um espaço digital onde cada símbolo cadastrado automaticamente se conecta aos livros, cartas de tarô, mitologias, arquétipos e anotações, formando um **atlas vivo de simbologia** construído ao longo do tempo.

---

## 📊 Por Que Existe Este Projeto?

Pesquisadores em simbologia (você incluído) gastam 5-10 horas/semana em pesquisa fragmentada:
- 📓 Anotações espalhadas em Notion/Obsidian (sem visualização de conexões)
- 🌐 Pesquisas em Wikipedia, blogs, sites acadêmicos (sem integração)
- 📖 Livros impressos (sem busca cross-tema)
- 🔗 Perdem-se conexões valiosas entre símbolos

**Solução:** Um app onde cada símbolo é um nó em um grafo, mostrando:
- Origem, significados, culturas, mitologias
- Relação com Tarô, Jung, Alquimia, Astrologia
- Grimórios temáticos (Tarô, Sonhos, Cores, Animais, Arquétipos, etc.)
- Mapa visual de todas as conexões

---

## 🏗️ Componentes Principais

### 📚 Biblioteca
Fichário de livros, artigos, PDFs com metadados:
- Autor, tema, resumo, conceitos
- Símbolos encontrados
- Avaliação pessoal

### 📜 Grimórios (Cadernos Temáticos)
- Grimório do Tarô
- Grimório dos Sonhos
- Grimório das Cores
- Grimório dos Animais
- Grimório dos Arquétipos
- Grimório da Mitologia
- Grimório da Alquimia
- Grimório das Religiões
- Grimório da Psicologia Analítica

Cada um registra: descobertas, hipóteses, conexões, interpretações, dúvidas, mapas mentais.

### 🔍 Fichas de Pesquisa
Estrutura de dados para cada símbolo (ex. "Coruja"):
- Origem, significados, culturas
- Mitologias, Tarô, Jung, Alquimia, Astrologia
- Obras onde aparece
- Observações pessoais

### 🕸️ Mapa de Conexões (O Core!)
Clique em "Lua" e veja conectado a:
- A Sacerdotisa (Tarô)
- Ártemis, Hécate (mitologia)
- Yin (filosofia)
- Inconsciente, Água, Feminino (psicologia)
- Sonhos, Ciclos, Marés

**Wikipedia pessoal mostrando como um símbolo conversa com muitos outros.**

### 🧪 Diário do Laboratório
Registro cronológico de descobertas:
```
24/07/2026
"Hoje encontrei relação entre serpente da alquimia e Ouroboros,
que aparece em Jung como renovação..."
```

---

## 🎯 Objetivos Mensuráveis

| Métrica | Target | Prazo |
|---------|--------|-------|
| Economia de tempo | 5-10h/semana ganhas | 3 meses pós-launch |
| Descoberta | 3+ relações novas/símbolo | MVP |
| Early Users | 50 ativos (comunidades tarô) | Fase 06 |
| Retenção | 70%+ após 3 meses | Fase 06 |
| Satisfação | NPS > 60 | Q1 2027 |

---

## 📱 Stack Tecnológico

**A decidir na Fase 04:**
- **Mobile:** React Native (JS cross-platform) OU Flutter (Dart)
- **Backend:** Node.js + Supabase (PostgreSQL + GraphQL)
- **Grafo de Conexões:** D3.js, Cytoscape.js ou similiar
- **Web:** Next.js + React (secondary, para pesquisa)
- **Auth:** OAuth2 (Google, GitHub)
- **Compliance:** LGPD — criptografia em repouso + trânsito

---

## 📚 Documentação Mestre

**⭐ Leia sempre:** [`docs/framework/01-Contexto-Global.md`](./docs/framework/01-Contexto-Global.md)

Contém:
- ✅ Visão, objetivos, stakeholders
- ✅ Restrições (móbile-first, LGPD, 16 semanas)
- ✅ Status do GPS (fases, prazos)
- ✅ Matriz de riscos + mitigações

---

## 🚀 Fases do GPS (16 semanas até MVP)

| Fase | Status | Quando | Documento |
|------|--------|--------|-----------|
| 00 Descoberta | ✅ Completo | 2026-07-24 | [`00-Descoberta.md`](./docs/framework/00-Descoberta.md) |
| 01 Contexto Global | 🔄 Em Progresso | 2026-07-25 | [`01-Contexto-Global.md`](./docs/framework/01-Contexto-Global.md) |
| 02 Estrutura Documental | ⏳ Planejado | 2026-08-08 | [`02-Estrutura-Documental.md`](./docs/framework/02-Estrutura-Documental.md) |
| 03 Descoberta do Produto | ⏳ Planejado | 2026-08-22 | [`03-Descoberta-do-Produto.md`](./docs/framework/03-Descoberta-do-Produto.md) |
| 04 Arquitetura | ⏳ Planejado | 2026-10-15 | [`04-Arquitetura.md`](./docs/framework/04-Arquitetura.md) |
| 05 Implementação | ⏳ Bloqueado | 2026-11-05 | [`05-Implementacao.md`](./docs/framework/05-Implementacao.md) |
| 06 Evolução | ⏳ Futuro | 2027-02-05 | [`06-Evolucao.md`](./docs/framework/06-Evolucao.md) |

**⛔ GATE CRÍTICO:** Fase 04 deve ser aprovada antes de começar desenvolvimento!

---

## 🎯 Primeiros Passos

1. **Leia:** [`docs/framework/01-Contexto-Global.md`](./docs/framework/01-Contexto-Global.md) — MESTRE
2. **Valide:** Stack técnico (React Native vs Flutter?)
3. **Protótipo:** Validar Mapa de Conexões na Fase 03
4. **Conecte:** Com comunidades de Tarô/Simbologia para feedback

---

## 🔐 Inegociáveis

- ✅ **Móbile-first** — app para celular, não desktop
- ✅ **LGPD compliance** — criptografia obrigatória
- ✅ **Grafo visual** — mapa de conexões é core, não optional
- ✅ **Conhecimento pessoal** — v1 não é comunidade/rede social
- ✅ **Open knowledge** — possibilidade de export (não é lock-in)

---

## 📞 Contatos

| Papel | Responsável |
|-------|-------------|
| **Lead User + Decisor** | Você (Daany) |
| **Designer** | — (a definir) |
| **Tech Lead** | — (a definir) |
| **Early Users** | Comunidades de Tarô/Simbologia |

---

Para Cursor/Claude: leia `.claude/CLAUDE.md` e `.cursorrules`
