# 📋 PRD — Product Requirements Document

**Laboratório de Simbologia — MVP (v1.0)**

---

## 📌 Informações Gerais

| Campo | Valor |
|-------|-------|
| **Produto** | Laboratório de Simbologia |
| **Versão** | 1.0 (MVP) |
| **Data** | 2026-07-25 |
| **Owner** | Daany |
| **Status** | Em Desenvolvimento (Fase 03) |
| **Plataforma** | Mobile-first (React Native ou Flutter) + Web (Next.js) |

---

## 🎯 Visão de Produto

Um app mobile que funciona como **Obsidian + Wikipedia pessoal** para pesquisadores de símbolos, permitindo documentar, conectar e visualizar relacionamentos entre símbolos de forma integrada.

---

## 🎭 Personas

### Persona 1: O Pesquisador Apaixonado
- **Descrição:** Estuda tarô, mitologia, psicologia junguiana há 5+ anos
- **Comportamento:** Tem 10+ livros, toma notas em Notion/Obsidian
- **Dor:** Perde conexões valiosas; sem integração
- **Solução:** Mapa de conexões automático
- **Métrica de Sucesso:** Economia de 5h/semana

### Persona 2: O Curioso Iniciante
- **Descrição:** Interessado em tarô, Jung, mitologia; começando do zero
- **Comportamento:** Pesquisa dispersa em blogs, Wikipedia
- **Dor:** Informação conflitante; não sabe por onde começar
- **Solução:** Grimórios temáticos + fichas estruturadas
- **Métrica de Sucesso:** Aprende 1 símbolo por semana com confiança

### Persona 3: O Artista Buscador
- **Descrição:** Usa símbolos como referência criativa (ilustrador, escritor)
- **Comportamento:** Pulveriza pesquisa em múltiplas abas
- **Dor:** Lento achar símbolos + significados + variações
- **Solução:** Banco integrado com search eficiente
- **Métrica de Sucesso:** Pesquisa 10x mais rápida

### Persona 4: O Estudante Acadêmico
- **Descrição:** Pesquisa comparada de mitologias/religiões
- **Comportamento:** Precisa de rigor e citações
- **Dor:** Ferramentas acadêmicas caras e inflexíveis
- **Solução:** Estrutura flexível + export para academic formats
- **Métrica de Sucesso:** Cita 20+ símbolos com fontes validadas

---

## 🏗️ Componentes Principais (Features)

### 1. 📚 Biblioteca
**Objetivo:** Centralizar referências de livros, artigos, PDFs

**Requisitos Funcionais:**
- [x] Upload/fichário de livros (metadata)
- [x] Campos: Autor, Tema, Resumo, Conceitos
- [x] Tagging de símbolos encontrados
- [x] Rating/avaliação pessoal
- [x] Search por autor/tema
- [x] Export de referências (BibTeX)

**Critério de Aceitação:**
- Usuário consegue adicionar um livro em < 2 minutos
- Search retorna resultados em < 500ms
- Suporta 1000+ livros sem performance lag

---

### 2. 📜 Grimórios (9 Cadernos Temáticos)
**Objetivo:** Organizar pesquisa por tema

**Temas Padrão:**
- Grimório do Tarô
- Grimório dos Sonhos
- Grimório das Cores
- Grimório dos Animais
- Grimório dos Arquétipos
- Grimório da Mitologia
- Grimório da Alquimia
- Grimório das Religiões
- Grimório da Psicologia Analítica

**Requisitos Funcionais:**
- [x] Criar grimório (precisa nome + descrição)
- [x] Dentro de grimório: descobertas, hipóteses, conexões
- [x] Cada entrada é timestamped
- [x] Suporta texto + imagens
- [x] Tags para filtrar
- [x] Search dentro de grimório
- [x] **Registro de Estudos (NOVO)** — subsegmento de cada entrada
  - [x] Definir objetivo de aprendizado
  - [x] Rastrear status (pendente | em_progresso | concluído)
  - [x] Registrar horas investidas
  - [x] Manter lista de aprendizados principais
  - [x] Próximos passos
  - [x] Visualizar progresso (% de conclusão)

**Critério de Aceitação:**
- Usuário consegue criar entrada em < 1 minuto
- Busca dentro de grimório retorna em < 300ms
- Suporta 1000+ entradas por grimório
- Registro de Estudo é opcional (entrada funciona com ou sem)
- Progresso é salvo automaticamente

---

### 3. 🔍 Fichas de Pesquisa
**Objetivo:** Estrutura de dados para cada símbolo

**Campos Obrigatórios:**
- Nome do símbolo
- Tipo(s) (animal, divindade, carta, elemento, cor, número, planta, cristal, lugar, ação, arquétipo, geométrico)
- Significados (com tradição + contexto)
- Relacionamentos (links a outros símbolos)
- Contextos onde aparece (mitologia, tarô, psicologia, etc.)
- Origem (cultura, período histórico)
- Observações pessoais
- Fontes

**Requisitos Funcionais:**
- [x] Criar ficha com validação
- [x] Editar ficha
- [x] Deletar ficha (soft delete)
- [x] Search por nome/tipo
- [x] Autocomplete em relacionamentos
- [x] Visualizar como ficha ou como JSON

**Critério de Aceitação:**
- Criar ficha completa em < 5 minutos
- Search retorna em < 200ms
- Suporta 10,000+ símbolos

---

### 4. 🕸️ Mapa de Conexões (CORE!)
**Objetivo:** Grafo visual interativo de símbolos conectados

**Requisitos Funcionais:**
- [x] Renderizar grafo (D3.js / Cytoscape)
- [x] Clicar em símbolo → mostra conexões
- [x] Zoom / pan
- [x] Drag nodes
- [x] Mostrar tipos de relação (cor / estilo diferente)
- [x] Filtrar por contexto (mostrar só Tarô, ou só mitologia)
- [x] Export como imagem

**Performance:**
- Renderizar 1000+ nós em < 2 segundos
- Interação fluida (60fps)

**Critério de Aceitação:**
- Usuário consegue explorar grafo intuitivamente
- Padrões emergem visualmente (ex: Lua + Coruja + A Sacerdotisa + Inconsciente)

---

### 5. 🧪 Diário do Laboratório
**Objetivo:** Timeline cronológica de descobertas pessoais

**Requisitos Funcionais:**
- [x] Criar entrada datada
- [x] Buscar por data
- [x] Timeline visual (scrollável)
- [x] Tags por símbolo mencionado
- [x] Export cronológico

**Critério de Aceitação:**
- Usuário vê evolução de pensamento ao longo do tempo
- Search por data + texto funcionam

---

## 🎯 Requisitos Não-Funcionais

### Performance
- MVP load time: < 3 segundos
- Busca: < 500ms
- Grafo com 1000 nós: render em < 2s

### Escalabilidade
- Suporta 10,000+ símbolos
- 1,000+ usuários concorrentes (depende de servidor)

### Segurança
- LGPD compliant
- Criptografia de dados em repouso + trânsito
- OAuth2 para auth
- Audit logs

### Acessibilidade
- WCAG 2.1 AA mínimo
- Keyboard navigation
- Screen reader compatible
- Dark mode

### Compatibilidade
- iOS 13+
- Android 9+
- Safari/Chrome web

---

## 📊 User Stories

### Epic 1: Pesquisa Integrada

**US-01:** Como pesquisador, quero adicionar um livro na Biblioteca para ter referências centralizadas
```
Given: Estou na tela de Biblioteca
When: Clico em "Adicionar Livro"
Then: Vejo formulário com campos (Autor, Tema, Resumo, Conceitos)
And: Posso fazer upload de PDF
And: Posso adicionar tags de símbolos
```

**US-02:** Como pesquisador, quero criar uma entrada no Grimório para documentar descobertas
```
Given: Estou na tela de Grimório
When: Clico em "Nova Entrada"
Then: Vejo editor de texto + campos (data, tags)
And: A entrada é salva automaticamente (autosave)
```

### Epic 2: Fichas de Símbolos

**US-03:** Como pesquisador, quero criar uma ficha para um símbolo (ex: Coruja)
```
Given: Estou na tela de Fichas
When: Clico em "Novo Símbolo"
Then: Vejo formulário com todos os campos
And: Campos obrigatórios são validados
And: Posso salvar como rascunho ou publicado
```

**US-04:** Como pesquisador, quero conectar dois símbolos para mapear relacionamentos
```
Given: Estou editando ficha de "Coruja"
When: Clico em "Adicionar Relação"
Then: Vejo search de símbolos
And: Posso escolher tipo de relação (origem_de, equivalente_a, etc.)
And: A conexão é bidirecional
```

### Epic 3: Mapa Visual

**US-05:** Como pesquisador, quero visualizar o grafo de um símbolo para ver suas conexões
```
Given: Estou na ficha de "Lua"
When: Clico em "Ver Mapa"
Then: Vejo grafo com Lua no centro
And: Vejo todos seus nós conectados (Sacerdotisa, Atena, Inconsciente, etc.)
And: Posso clicar em qualquer nó para explorar
And: Posso fazer zoom/pan
```

---

## 🚫 O Que NÃO É MVP (v2+)

- ❌ Comunidade social (v2)
- ❌ IA gerativa (v2+)
- ❌ Mobile app nativa (v1 é React Native/Flutter)
- ❌ Export em múltiplos formatos (apenas JSON/PDF v1)
- ❌ Sincronização cloud em tempo real (v1 é local-first)
- ❌ Multiplayer collaboration (v2)

---

## 📈 Métricas de Sucesso

| Métrica | Target | Como Medir |
|---------|--------|-----------|
| Tempo economia | 5-10h/semana | Survey usuário + time tracking |
| Padrões descobertos | 3+ por símbolo | Feedback usuário |
| Retenção | 70% após 3 meses | DAU/MAU |
| Satisfação | NPS > 60 | NPS survey |
| Performance | < 3s load | WebPageTest |

---

## 🎲 Dependências & Riscos

### Dependências
- Fase 04 Arquitetura deve definir: React Native vs Flutter
- Design System deve estar pronto para UI

### Riscos
| Risco | Probabilidade | Impacto | Mitigação |
|-------|---|---|---|
| Grafo é complexo de renderizar | Alta | Alto | Prototipagem D3 na Fase 03 |
| Comunidade não adota | Média | Alto | Validar com early users Fase 03 |
| Performance com 10k símbolos | Média | Médio | Load testing, caching strategy |

---

## 📅 Timeline Estimada

- **Fase 02 (até 2026-08-08):** Finalizar este PRD
- **Fase 03 (até 2026-08-22):** Validar com users + prototipagem
- **Fase 04 (até 2026-10-15):** Decisões técnicas
- **Fase 05 (2026-11-05):** Implementação (6 semanas)

---

## ✅ Aprovações

| Stakeholder | Aprovado? | Data |
|---|---|---|
| Daany (Product) | — | — |
| Designer Lead | — | — |
| Tech Lead | — | — |

---

**Criado em:** 25/07/2026  
**Versão:** 1.0  
**Status:** Draft (aguardando aprovações)
