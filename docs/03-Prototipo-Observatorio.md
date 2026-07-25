# 🔭 Protótipo Visual — Observatório

**Laboratório de Simbologia — Navegação Principal**

**Fase 03 — Prototipagem Visual**

---

## 🎭 Conceito: O Observatório

Você não "clica" em um menu. Você "orbita" para uma constelação.

```
                    📚 BIBLIOTECA
                    (Conhecimento)
                         ↑
                         |
    📜 GRIMÓRIOS ←  [LABORATÓRIO]  →  🔍 FICHAS
   (Exploração)      (Centro)      (Estrutura)
                         |
                         ↓
           🕸️ MAPA DE CONEXÕES + 🧪 DIÁRIO
              (Revelação + Reflexão)
```

---

## 📱 Tela Mobile — Estado Inicial (Home)

```
┌─────────────────────────────────────┐
│ 🔍 Laboratório    ⚙️ Menu           │ Header (simple)
├─────────────────────────────────────┤
│                                     │
│          Bem-vindo!                 │
│                                     │
│    Escolha uma constelação:         │
│                                     │
│              📚                     │ Body
│         (Biblioteca)                │ (Observatório)
│                                     │
│      📜  ⭕  🔍                     │
│   (Grimórios) (Lab) (Fichas)        │
│                                     │
│      🕸️      🧪                    │
│   (Mapa) (Diário)                   │
│                                     │
├─────────────────────────────────────┤
│ 📚  📜  ⭕  🔍  🧪  (Bottom Tabs)    │ Navigation
└─────────────────────────────────────┘
```

**Animação:** Ícones orbitam suavemente (subtle rotation)

---

## 📚 Estado: Biblioteca Ativa

```
┌─────────────────────────────────────┐
│ ← Biblioteca         [+ Novo Livro]  │
├─────────────────────────────────────┤
│  [Buscar livro...]                  │
├─────────────────────────────────────┤
│                                     │
│ • The Rider-Waite Tarot ⭐⭐⭐⭐⭐ │
│   Arthur Waite & Pam Colman (1909)  │
│   Tags: Tarô, Arcanos, Clássico     │
│                                     │
│ • Dreams: A Very Short... ⭐⭐⭐    │
│   Carl Jung (1964)                  │
│   Tags: Jung, Psicologia, Símbolos  │
│   → Symbols found: 12               │
│                                     │
│ • The Golden Bough ⭐⭐⭐⭐        │
│   J.G. Frazer (1890)                │
│   Tags: Mitologia, Religião         │
│   → Reading: 34% (Chapter 8)        │
│                                     │
├─────────────────────────────────────┤
│ 📚  📜  ⭕  🔍  🧪                  │
└─────────────────────────────────────┘

Interaction:
├─ Tap livro → Ver detalhes + PDF
├─ Swipe left → Editar / Deletar
├─ Long press → Ver símbolos dentro
└─ Busca por autor/tema (rápida)
```

---

## 📜 Estado: Grimórios Ativa — COM REGISTRO DE ESTUDOS ✨

```
┌─────────────────────────────────────┐
│ ← Tarô              [+ Nova Entrada] │
├─────────────────────────────────────┤
│ Tipo: Tarô (22 Arcanos Maiores)    │
│ 9 Entradas totais                   │
├─────────────────────────────────────┤
│                                     │
│ 25/07/2026                          │
│ ✍️ "Os Arcanos Maiores"            │ Entry
│  Texto: "Começando estudo..."       │ (with Study)
│                                     │
│  📊 REGISTRO DE ESTUDO              │ ← NEW!
│     Status: 🔵 em_progresso        │
│     Objetivo: Memorizar 22 Arcanos  │
│     [████████    ] 65% (14/22)      │
│     ⏱️ 8.5 horas investidas         │
│     ✅ Aprendizados: 5              │
│     📝 Próximos passos: 3           │
│                                     │
│ 22/07/2026                          │
│ ✍️ "Primeira impressão"            │
│  Texto: "Cartas bonitas..."         │
│                                     │
│ 20/07/2026                          │
│ ✍️ "Dúvidas sobre O Mago"          │
│  Tags: O Mago, significado          │
│                                     │
├─────────────────────────────────────┤
│ 📚  📜  ⭕  🔍  🧪                  │
└─────────────────────────────────────┘

Interaction:
├─ Tap entry → Editar
├─ Tap "Registro de Estudo" → Modal com detalhes
├─ Swipe left → Opções
└─ + Botão para:
   - Criar nova entrada
   - Criar novo Registro de Estudo
   - Ver Timeline visual
```

---

## 📊 Modal: Registro de Estudo (Detalhe)

```
┌─────────────────────────────────────┐
│ 📊 Registro de Estudo               │ (Modal)
│ ─────────────────────────────────── │
│                                     │
│ Objetivo:                           │
│ ┌───────────────────────────────┐   │
│ │ Memorizar 22 Arcanos em 4 sem │   │
│ └───────────────────────────────┘   │
│                                     │
│ Status:  🔵 em_progresso            │
│ Progresso: [████████  ] 65%         │ ← Progress bar
│            (14 de 22 cartasok)      │
│                                     │
│ 📅 Iniciado: 25/07/2026             │
│ ⏱️  Horas: 8.5                      │
│ 📍 Próximo milestone: 18 cartas      │
│                                     │
│ ✅ Aprendizados principais:         │
│ ├─ O Louco = Inocência, Novo Início│
│ ├─ O Mago = Poder Pessoal           │
│ ├─ A Sacerdotisa = Intuição, Mistério
│ ├─ A Imperatriz = Criatividade      │
│ └─ O Imperador = Autoridade         │
│                                     │
│ 📝 Próximos passos:                 │
│ ├─ [ ] Estudar Arcanos Menores     │
│ ├─ [ ] Comparar com Cábala         │
│ └─ [ ] Fazer um Spread             │
│                                     │
│ 🔗 Relacionado a:                   │
│ └─ Símbolo: "Lua" (conectado)       │
│    "A Sacerdotisa" (3 conexões)     │
│                                     │
│ [Editar]  [Marcar Concluído] [X]    │
└─────────────────────────────────────┘
```

---

## 🔍 Estado: Fichas de Pesquisa Ativa

```
┌─────────────────────────────────────┐
│ ← Fichas         [+ Nova Ficha]      │
├─────────────────────────────────────┤
│  [Buscar símbolo...]                │
├─────────────────────────────────────┤
│                                     │
│ 🌙 Lua                              │
│    Divindade | Elemento | Arquétipo │
│                                     │
│ 🦉 Coruja                           │
│    Animal | Divindade               │
│    "Sabedoria" em 7 contextos       │
│                                     │
│ 🏺 A Sacerdotisa (Tarô II)          │
│    Carta de Tarô | Arquétipo        │
│    [Ver no Mapa]                    │
│                                     │
│ 💜 Ametista                         │
│    Cristal | Elemento | Geométrico  │
│                                     │
├─────────────────────────────────────┤
│ 📚  📜  ⭕  🔍  🧪                  │
└─────────────────────────────────────┘
```

---

## 🕸️ Estado: Mapa de Conexões Ativa

```
┌─────────────────────────────────────┐
│ ← Mapa (A Sacerdotisa) [Filtro ⋮]   │
├─────────────────────────────────────┤
│                                     │
│              📚                     │
│           (Biblioteca)              │
│              |                      │
│          [Sabedoria]                │
│              |                      │
│     📜 - [A Sacerdotisa] - 🔍      │
│    (Grimório)  (Ficha)              │
│              |                      │
│              ↓                      │
│        [Intuição/Mistério]          │
│              |                      │
│     🌙       👑       💜            │
│    Lua   Hécate   Ametista          │
│                                     │
│  (Drag para mover)                  │
│  (Pinch para zoom)                  │
│  (Tap nó para detalhe)              │
│                                     │
├─────────────────────────────────────┤
│ 📚  📜  ⭕  🔍  🧪                  │
└─────────────────────────────────────┘

Cores dos nós:
├─ Azul (#0066FF) = Símbolo estudado
├─ Cinza (#6C757D) = Não estudado
├─ Verde (#2D8659) = Estudo concluído
└─ Laranja (#FF8C42) = Destaque/novo
```

---

## 🧪 Estado: Diário do Laboratório Ativa

```
┌─────────────────────────────────────┐
│ ← Diário            [+ Nova Entrada] │
├─────────────────────────────────────┤
│ Filtro: [Todos ▼]                   │
├─────────────────────────────────────┤
│                                     │
│ 28/07/2026                          │
│ "Descoberta: Lua aparece em A      │
│  Sacerdotisa! Ambas = conhecimento  │
│  oculto. Sincronicidade?"           │
│  Tags: #sincronicidade #connections│
│                                     │
│ 25/07/2026                          │
│ "Comecei aprender Tarô. 14 Arcanos  │
│  já memorizados. Sinto progresso!"  │
│  Tags: #estudo #progresso           │
│  Linked to: Grimório Tarô           │
│                                     │
│ 22/07/2026                          │
│ "Sonho com coruja branca. Assustador.│
│  Reconsiderando sabedoria..."       │
│  Tags: #sonhos #arquétipos          │
│                                     │
├─────────────────────────────────────┤
│ 📚  📜  ⭕  🔍  🧪                  │
└─────────────────────────────────────┘
```

---

## 🎨 Comportamento de Navegação

### Transição entre Constelações

```
Usuário tapa em 📜 GRIMÓRIOS:

1. Content atual faz fade-out (150ms)
2. 📜 ícone faz scale 1.0 → 1.1 → 1.0 (200ms)
3. Novo conteúdo faz fade-in (150ms)
4. Focus no topo (smooth scroll)

Sensação: Suave, elegante, sem distração
```

### Botão de Ação Flutuante (+)

```
Canto inferior direito, acima da barra de tabs:

[+] Novo

Ao tocar (context menu):
├─ + Novo símbolo (Fichas)
├─ + Novo livro (Biblioteca)
├─ + Nova entrada (Grimório)
├─ + Observação (Diário)
└─ Cancelar
```

---

## 🌈 Paleta de Cores (Aplicada)

```
Background:     #FFFFFF (branco)
Text primário:  #212529 (cinza muito escuro)
Text secundário: #495057 (cinza escuro)
Borders:        #E9ECEF (cinza claro)

Ação Principal: #0066FF (azul)
Sucesso:        #2D8659 (verde)
Alerta:         #FF8C42 (laranja)
Erro:           #D32F2F (vermelho)

Observatório:
├─ Biblioteca:  #0066FF (azul)
├─ Grimórios:   #6C757D (cinza)
├─ Fichas:      #FF8C42 (laranja)
├─ Mapa:        #9C27B0 (roxo SUAVE)
└─ Diário:      #2D8659 (verde)
```

---

## ✅ Checklist de Prototipagem

- [x] Conceito Observatório definido
- [x] Estados de cada tela desenhados
- [x] Registro de Estudos visualizado
- [ ] Figma/mockup interativo (próximo: designer)
- [ ] Teste com usuários reais (próximo: validação)
- [ ] Prototipo técnico HTML/React (Fase 05)

---

## 🚀 Próximas Etapas

### Imediato (Fase 03)

1. **Figma/Sketch** — Design detalhado do Observatório
2. **Teste com usuários** — João (Iniciante) testa interface
3. **Iteração** — Feedback → melhorias

### Fase 04 (Arquitetura)

1. **React Native setup** — Implementar navegação real
2. **Prototipo técnico** — Observatório funcional
3. **Testes de performance** — Mobile fluido

### Fase 05 (Implementação)

1. **Código completo** — Cada tela
2. **Integração com Mapa** — D3/Cytoscape
3. **Polish final** — Animações, micro-interações

---

**Prototipo Visual Status:** ✅ CONCEITUAL COMPLETO  
**Próximo:** Design detalhado (Figma)

