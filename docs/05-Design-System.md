# 🎨 Design System

**Laboratório de Simbologia — Visual Identity**

---

## 📌 Conceito Central: O Observatório

A navegação não é um menu tradicional. É um **Observatório** — um círculo central (Laboratório) rodeado por 5 constelações (módulos principais).

```
                    📚 BIBLIOTECA
                    (Conhecimento)
                         ↑
                         |
    📜 GRIMÓRIOS ←  [LABORATÓRIO]  →  🔍 FICHAS
   (Exploração)      (Centro)      (Estrutura)
                         |
                         ↓
           🕸️ MAPA DE CONEXÕES
              (Revelação)
                    
           🧪 DIÁRIO DO LABORATÓRIO
              (Reflexão)
```

**Filosofia:**
- O Laboratório é o coração
- Cada constelação é um ramo do conhecimento
- A navegação reforça conceitual: você não "clica" em um botão, você "orbita" para uma constelação
- A interface sussurra: "você está explorando"

---

## 🎨 Paleta de Cores

### Filosofia de Cores
- ✅ Minimalista
- ✅ Elegante
- ✅ Não místico
- ✅ Neutra com acentos sutis
- ❌ Sem preto puro
- ❌ Sem roxo dominante
- ❌ Sem dourado exagerado

### Cores Primárias

```
Neutras (Base):
├── Branco Puro:        #FFFFFF
├── Cinza Claro:        #F8F9FA  (backgrounds)
├── Cinza Médio:        #E9ECEF  (dividers, borders)
├── Cinza Escuro:       #495057  (texto secundário)
└── Cinza Muito Escuro: #212529  (texto primário)

Acentos Sutis:
├── Azul Puro:          #0066FF  (ações, focus)
├── Verde Calmo:        #2D8659  (sucesso, confirmação)
├── Laranja Suave:      #FF8C42  (avisos, destaque)
├── Vermelho Discreto:  #D32F2F  (erro, deletar)
└── Cinza Azulado:      #6C757D  (desabilitado)
```

### Aplicação

```
Fundo:           #F8F9FA ou #FFFFFF
Texto Primário:  #212529
Texto Secundário: #495057
Bordas/Dividers: #E9ECEF
Ação Principal:  #0066FF
Ação Secundária: #6C757D
Sucesso:         #2D8659
Alerta:          #FF8C42
Erro:            #D32F2F
```

### Modos Light/Dark

**Light Mode (padrão):**
```
Background: #FFFFFF
Text:       #212529
Accents:    Azul #0066FF
Borders:    #E9ECEF
```

**Dark Mode:**
```
Background: #0F1419
Text:       #E9ECEF
Accents:    Azul #4D9FFF (mais claro)
Borders:    #495057
```

---

## 🔤 Tipografia

### Fontes (Em Ordem de Preferência)

```
1. Inter (gratuita, Google Fonts)
   └─ Perfeita para corpo de texto
   └─ Altamente legível em telas pequenas
   └─ Pesos: Regular (400), Medium (500), Bold (700)

2. Manrope (gratuita, Google Fonts)
   └─ Alternativa moderna, um pouco mais "design"
   └─ Pode ser usada em headings
   └─ Pesos: Regular (400), Medium (500), Bold (700)

3. Geist (Vercel, gratuita)
   └─ Ultra-moderna, excelente em mobile
   └─ Opção para interfaces mais contemporâneas
   └─ Pesos: Regular (400), Medium (500), Bold (700)
```

### Escala Tipográfica

```
Display (Hero):
├── Font:   Manrope Bold
├── Size:   28-32px (mobile), 40-48px (desktop)
├── Weight: 700
├── Line:   1.2
└── Uso:    Títulos principais, nome do app

Heading 1:
├── Font:   Inter Bold
├── Size:   24px (mobile), 32px (desktop)
├── Weight: 700
└── Uso:    Títulos de telas

Heading 2:
├── Font:   Inter Medium
├── Size:   18px (mobile), 24px (desktop)
├── Weight: 600
└── Uso:    Subtítulos, nomes de seções

Body:
├── Font:   Inter Regular
├── Size:   14px (mobile), 16px (desktop)
├── Weight: 400
├── Line:   1.6
└── Uso:    Texto principal, descrições

Small:
├── Font:   Inter Regular
├── Size:   12px
├── Weight: 400
└── Uso:    Labels, captions, metadata

Caption:
├── Font:   Inter Regular
├── Size:   11px
├── Weight: 400
└── Uso:    Datas, fontes, notas

Mono (Código):
├── Font:   "SF Mono", "Monaco", monospace
├── Size:   12px
└── Uso:    Exemplos JSON, código
```

### Regras de Legibilidade

- ✅ Contraste mínimo WCAG AA (4.5:1 para texto)
- ✅ Line-height mínimo 1.5 para corpo de texto
- ✅ Sem mais de 2 fontes diferentes por tela
- ✅ Títulos sempre sans-serif
- ✅ Serif nunca para UI

---

## 🎯 Ícones

### Filosofia

```
✅ Traço fino (stroke 1.5-2px)
✅ Minimalistas (essência visual)
✅ Sem elementos "místicos" (sem estrelas, fases da lua, cristais desenhados)
✅ Funcionais (comunicam ação, não decoração)
✅ Consistentes (mesmo visual em todos)
✅ Inclusivos (reconhecíveis por usuários com deficiência visual)
```

### Biblioteca de Ícones Recomendada

```
Opção 1: Heroicons (Tailwind)
├─ 24px por padrão
├─ Stroke 1.5
├─ Customizáveis
└─ Perfeito para nosso estilo

Opção 2: Feather Icons
├─ Minimalistas
├─ Traço fino
└─ Open source

Opção 3: Lucide
├─ Baseado em Feather
├─ Melhorado e expandido
└─ Community-driven
```

### Ícones Principais (Observatório)

```
BIBLIOTECA:
├─ Ícone: Livro aberto (simple outline)
├─ Stroke: 1.5px
└─ Cores: Azul #0066FF

GRIMÓRIOS:
├─ Ícone: Caderno/journal (simple outline)
├─ Stroke: 1.5px
└─ Cores: Verde #2D8659

FICHAS:
├─ Ícone: Card/ficha (simple outline)
├─ Stroke: 1.5px
└─ Cores: Laranja #FF8C42

MAPA:
├─ Ícone: Node/network (simple outline)
├─ Stroke: 1.5px
└─ Cores: Roxo suave #7C3AED (único roxo permitido: no mapa!)

DIÁRIO:
├─ Ícone: Pen/pencil (simple outline)
├─ Stroke: 1.5px
└─ Cores: Cinza #6C757D
```

---

## 🧬 O Observatório (Navegação)

### Estrutura Visual

```
        TOPO
    (Logo + Info)
         |
    [Conteúdo]
    (Central)
         |
    ┌─────────────┐
    │  OBSERVATÓRIO │ (Bottom Navigation)
    │             │
    │      📚      │  (Biblioteca - Top)
    │      |      │
    │ 📜 - ⭕ - 🔍│  (Grimórios - Center - Fichas)
    │      |      │
    │    🕸️  🧪   │  (Mapa - Diário)
    └─────────────┘
```

### Interação

**Desktop (Sidebar):**
```
┌─────────────┐
│ 📚 Biblioteca│
│ 📜 Grimórios│
│ 🔍 Fichas    │ ← Navegação vertical
│ 🕸️ Mapa      │
│ 🧪 Diário    │
└─────────────┘
    [Conteúdo]
```

**Mobile (Bottom Tab):**
```
    [Conteúdo]
┌───────────────────┐
│  📚 📜 ⭕ 🔍 🧪 │  ← Observatório
└───────────────────┘
```

### Animações

```
Tab Ativo:
├─ Scale: 1.1 (levemente maior)
├─ Duration: 200ms
└─ Easing: ease-out-cubic

Hover:
├─ Opacity: 0.8
├─ Scale: 1.05
└─ Duration: 150ms

Transição de Tela:
├─ Fade: 150ms
├─ Slide: 0 (apenas fade, sem movimento)
└─ Easing: ease-in-out
```

---

## 🧩 Componentes Base

### Button

```
Estados:
├─ Default:    Bg #0066FF, Text #FFFFFF
├─ Hover:      Bg #0052CC (mais escuro)
├─ Pressed:    Bg #003D99 + scale 0.98
├─ Disabled:   Bg #E9ECEF, Text #6C757D
└─ Loading:    Spinner animation

Tamanhos:
├─ Small:      12px padding, 32px height
├─ Medium:     16px padding, 40px height (padrão)
└─ Large:      20px padding, 48px height

Variantes:
├─ Primary:    Background sólido azul
├─ Secondary:  Outline cinza
└─ Danger:     Background vermelho
```

### Input

```
Estados:
├─ Default:    Border #E9ECEF
├─ Focus:      Border #0066FF, Box-shadow 0 0 0 3px #0066FF20
├─ Error:      Border #D32F2F
└─ Disabled:   Bg #F8F9FA, Color #6C757D

Padding:
├─ Horizontal: 12px
├─ Vertical:   10px
└─ Font:       Inter 16px

Placeholder:
├─ Color:      #A8ACB1
└─ Opacity:    0.7
```

### Card

```
Background: #FFFFFF
Border:     1px solid #E9ECEF
Radius:     8px
Shadow:     0 1px 3px rgba(0,0,0,0.1)
Padding:    16px (mobile), 20px (desktop)

Hover:
├─ Shadow:    0 4px 12px rgba(0,0,0,0.08)
├─ Duration:  200ms
└─ Easing:    ease-out
```

### Modal

```
Overlay:    rgba(0,0,0,0.4)
Background: #FFFFFF
Radius:     12px
Max-width:  500px (mobile), 600px (desktop)
Padding:    24px (header), 20px (body), 16px (footer)

Animation:
├─ Fade in:  150ms
├─ Scale:    0.95 → 1
└─ Easing:   ease-out-cubic
```

### ProgressBar (Registro de Estudos)

```
Altura:        8px
Radius:        4px
Fundo:         #E9ECEF
Preenchido:    #0066FF (azul ativo)
Transição:     200ms ease-out

Estados:
├─ Em Progresso: #0066FF
├─ Concluído:    #2D8659 (verde)
└─ Pendente:     #6C757D (cinza)

Uso:
Mostrar % de conclusão em Registro de Estudo
```

### StudyCard (Entrada de Grimório com Registro)

```
Card padrão + Overlay de Estudo:

┌──────────────────────────┐
│ Título: "Os Arcanos"    │  Header
├──────────────────────────┤
│ 📊 Registro de Estudo    │  
│  Status: em_progresso    │  Study
│  Progresso: [====  ] 65% │  Badge
│  Horas: 8.5h            │
├──────────────────────────┤
│ Aprendizados: 3          │
│ Próximos passos: 2       │
└──────────────────────────┘

Background:  #FFFFFF
Border:      1px #E9ECEF
Padding:     16px
Badge Bg:    #F8F9FA
Badge Color: #495057

Interação:
├─ Tap em Study Badge → Abre modal com detalhes
├─ Swipe left → Editar/Deletar
└─ Long press → Ver aprendizados principais
```

### StatusBadge (Status de Estudo)

```
Tamanhos: Small (24px), Medium (32px), Large (40px)
Radius:   4px
Font:     Inter 12px Medium

Estados:
├─ Pendente:      Bg #F8F9FA, Text #6C757D
├─ Em Progresso:  Bg #E3F2FD, Text #0066FF
└─ Concluído:     Bg #E8F5E9, Text #2D8659

Exemplos:
[🟡 em_progresso]  [🟢 concluído]  [⚪ pendente]
```

---

## 📐 Espaçamento

### Escala

```
0px    = xs
4px    = sm
8px    = md
12px   = lg
16px   = xl
20px   = 2xl
24px   = 3xl
32px   = 4xl
40px   = 5xl
48px   = 6xl
```

### Aplicação

```
Padding de Card:    16px (móbile), 20px (desktop)
Margin entre items: 12px
Gap em Grid:        16px
Padding de Screen:  16px (mobile), 24px (desktop)
```

---

## 📱 Responsive Breakpoints

```
Mobile:    0px - 479px
Tablet:    480px - 1023px
Desktop:   1024px+

Exemplo:
@media (min-width: 480px) {
  .heading { font-size: 24px; }
}
```

---

## ♿ Acessibilidade (WCAG 2.1 AA)

```
Contraste:
├─ Texto normal: 4.5:1
├─ Texto grande (18px+): 3:1
└─ Componentes UI: 3:1

Keyboard Navigation:
├─ Tab order lógico
├─ Focus visível (outline 2px #0066FF)
└─ Teclas de atalho documentadas

Cores:
├─ Não use cor como único indicador
├─ Icones sempre com texto ou aria-label
└─ Diferenciação para daltonismo

Tipografia:
├─ Mínimo 14px (mobile)
├─ Line-height 1.5 mínimo
└─ Sem transformação de texto em ALL CAPS (use font-variant)
```

---

## 🌙 Modo Dark (Opcional v1)

```
Será implementado, mas não é MVP.
Suportará:
├─ Preservar tema escolhido
├─ Suporte a preferência do sistema (prefers-color-scheme)
└─ Toggle manualemente
```

---

## 📋 Implementação

### Frontend

```typescript
// Tokens como constantes
const colors = {
  primary: '#0066FF',
  success: '#2D8659',
  error: '#D32F2F',
  background: '#F8F9FA',
  text: '#212529',
};

const typography = {
  display: 'Manrope, sans-serif',
  body: 'Inter, sans-serif',
  mono: 'Monaco, monospace',
};

const spacing = {
  xs: '4px',
  sm: '8px',
  md: '12px',
  lg: '16px',
  // ...
};
```

### CSS Variables (Alternativa)

```css
:root {
  --color-primary: #0066FF;
  --color-text: #212529;
  --font-body: Inter, sans-serif;
  --space-md: 12px;
}

.button-primary {
  background: var(--color-primary);
  font: var(--font-body);
  padding: var(--space-md);
}
```

---

## 🎬 Animações & Micro-interações

```
Princípios:
├─ Rápido (< 200ms)
├─ Propositado (comunica, não distrai)
├─ Consistente (mesma duração/easing)
└─ Acessível (respeita prefers-reduced-motion)

Easing Functions:
├─ Entrada: ease-out-cubic
├─ Saída: ease-in-cubic
└─ Ciclo: ease-in-out

Exemplo:
@media (prefers-reduced-motion: reduce) {
  * { animation-duration: 0.01ms !important; }
}
```

---

## 📸 Exemplos de Telas (Wireframes Conceituais)

### Tela Inicial (Observatório Ativo)

```
┌──────────────────────────┐
│ 🔍 Laboratório           │ (Header)
├──────────────────────────┤
│                          │
│        CONTEÚDO          │
│                          │
│   Da constelação ativa   │
│                          │
├──────────────────────────┤
│  📚 📜 ⭕ 🔍 🧪         │ (Observatório)
└──────────────────────────┘
```

### Tela de Símbolo (Ficha)

```
┌──────────────────────────┐
│ ← Lua               ⋮    │
├──────────────────────────┤
│                          │
│  Tipos: Divindade, ...   │
│  Significados            │
│  ├─ Inconsciente         │
│  └─ Feminino             │
│                          │
│  Relacionado a:          │
│  ├─ A Sacerdotisa        │
│  └─ Atena                │
│                          │
│  Aparece em:             │
│  └─ Mitologia Grega      │
│                          │
├──────────────────────────┤
│  📚 📜 ⭕ 🔍 🧪         │
└──────────────────────────┘
```

### Mapa de Conexões (Observatório)

```
       🕸️ Mapa
        
        📚
        |
📜 - [⭕] - 🔍
        |
       🧪

(Nodes interativos, draggable, zoom enabled)
```

---

## 🔗 Recursos

- [Inter Font](https://fonts.google.com/specimen/Inter)
- [Manrope Font](https://fonts.google.com/specimen/Manrope)
- [Heroicons](https://heroicons.com)
- [WCAG 2.1](https://www.w3.org/WAI/WCAG21/quickref/)

---

**Criado em:** 25/07/2026  
**Versão:** 1.0  
**Status:** Implementação Fase 05  
**Identidade Visual:** O Observatório (CORE)
