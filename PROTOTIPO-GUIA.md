# 🎨 Guia do Prototipo Interativo

**Laboratório de Simbologia — Observatório (HTML/CSS)**

---

## 🚀 Como Usar

### Opção 1: Abrir no Navegador (Recomendado)

```bash
# No seu computador:
1. Vá para a pasta do projeto
2. Abra o arquivo: prototipo-observatorio.html
3. Duplo-clique para abrir no navegador
   (Ou: arrastar para Chrome/Firefox/Safari)
```

### Opção 2: Servidor Local (se quiser)

```bash
# Terminal na pasta do projeto:
python -m http.server 8000
# Depois acesse: http://localhost:8000/prototipo-observatorio.html
```

---

## 🎯 O Que Explorar

### 1. **Tela Inicial (Observatório)**

```
Você vê:
├─ 📚 BIBLIOTECA (topo)
├─ 📜 GRIMÓRIOS (esquerda)
├─ ⭕ LABORATÓRIO (centro)
├─ 🔍 FICHAS (direita)
├─ 🕸️ MAPA (embaixo esquerda)
└─ 🧪 DIÁRIO (embaixo direita)
```

**Teste:** Clique em qualquer ícone para navegar

---

### 2. **Biblioteca**

Mostra livros encontrados com:
- Título + Autor + Ano
- Tags (Tarô, Psicologia, etc)
- Rating (⭐⭐⭐⭐⭐)

**Teste:** Clique em um livro (ainda não faz nada, apenas demonstração)

---

### 3. **Grimórios** ✨ IMPORTANTE

**Este é o coração do prototipo!**

Mostra entradas de um Grimório com **REGISTRO DE ESTUDOS integrado:**

```
📜 Os Arcanos Maiores (25/07/2026)
│
└─ 📊 REGISTRO DE ESTUDO
   ├─ Status: 🔵 em_progresso
   ├─ Objetivo: Memorizar 22 Arcanos
   ├─ [████████  ] 65% (14/22)
   ├─ ⏱️ 8.5 horas
   └─ ✅ 14 Arcanos aprendidos
```

**Teste:** Clique em "Os Arcanos Maiores"
- Abre modal com detalhes completos
- Ver aprendizados principais
- Ver próximos passos
- Botões para Atualizar ou Marcar Concluído

---

### 4. **Fichas de Pesquisa**

Mostra símbolos cadastrados:
- 🌙 Lua (Divindade | Elemento | Arquétipo)
- 🦉 Coruja (Animal | Divindade)
- 🏺 A Sacerdotisa (Carta de Tarô)

**Teste:** Clique para ver detalhes (WIP - será completo em Fase 05)

---

### 5. **Mapa de Conexões**

Espaço reservado para o grafo visual (D3.js/Cytoscape).

```
🕸️ Grafo visual de conexões

Prototipo técnico será criado em Fase 04-05
Mostrará símbolos conectados
```

**Status:** Conceitual apenas (implementação em Fase 05)

---

### 6. **Diário do Laboratório**

Timeline cronológica de reflexões:

```
28/07/2026 — "Descoberta: Lua aparece em A Sacerdotisa!"
25/07/2026 — "Comecei a aprender Tarô. 14 já memorizados!"
22/07/2026 — "Sonho com coruja branca..."
```

**Teste:** Navegue pelas entradas

---

## 📱 Navegação

### Bottom Tabs (Fixos na Base)

```
📚  📜  ⭕  🔍  🧪
Bib Gri Lab Fic Diár
```

Tap em qualquer ícone para mudar de seção.

### Voltar (← Seta Esquerda)

Quando estiver em qualquer seção, clique em `←` no header para voltar ao Observatório.

---

## 🎨 Design System Aplicado

| Elemento | Cor | Uso |
|----------|-----|-----|
| Fundo | #FFFFFF (branco) | Panels principais |
| Texto | #212529 (cinza muito escuro) | Legibilidade |
| Borders | #E9ECEF (cinza claro) | Divisão visual |
| Ação | #0066FF (azul) | Botões, status ativo |
| Sucesso | #2D8659 (verde) | Completo, validação |
| Alerta | #FF8C42 (laranja) | Atenção |

---

## 🎬 Animações

### Transições
- **Fade-in (150ms):** Ao mudar de seção
- **Slide-up (200ms):** Ao abrir modal
- **Scale (200ms):** Ao hover em botões

### Paleta Observatório

```
📚 Biblioteca  → Azul (#0066FF)
📜 Grimórios   → Cinza (#6C757D)
🔍 Fichas      → Laranja (#FF8C42)
🕸️ Mapa       → Roxo (#9C27B0 suave)
🧪 Diário      → Verde (#2D8659)
```

---

## 📊 Registro de Estudos — CORE FEATURE

O modal de Registro mostra:

```
┌─────────────────────────────────┐
│ 📊 Registro de Estudo           │
├─────────────────────────────────┤
│ Objetivo: Memorizar 22 Arcanos  │
│ Status: 🔵 em_progresso        │
│ Progresso: [████████  ] 65%    │
│ ⏱️ 8.5 horas investidas        │
│                                 │
│ ✅ Aprendizados:               │
│ • O Louco = Inocência           │
│ • O Mago = Poder Pessoal        │
│ • A Sacerdotisa = Intuição      │
│ ...                             │
│                                 │
│ 📝 Próximos passos:            │
│ • [ ] Estudar Arcanos Menores   │
│ • [ ] Comparar com Cábala       │
│ • [ ] Fazer um Spread           │
│                                 │
│ [Atualizar]  [Marcar Concluído]│
└─────────────────────────────────┘
```

**Importância:** Isso responde ao seu pain-point de "rastrear progresso"

---

## ✅ Checklist: O Que Testar

Ao explorar o prototipo, valide:

- [ ] Observatório visual faz sentido? (5 constelações orbitando)
- [ ] Transições são suaves?
- [ ] Bottom tabs facilitam navegação?
- [ ] Registro de Estudos é claro? (65% progresso, aprendizados, próximos passos)
- [ ] Modal é informativo?
- [ ] Design minimalista agrada?
- [ ] Cores são legíveis?
- [ ] Funciona bem no mobile? (redimensione o navegador)

---

## 🎯 Feedback Esperado

Para validar com usuários (próximo passo):

**Faça perguntas como:**

1. "Você entende rapidamente o que cada seção faz?"
2. "O Registro de Estudos faz sentido para você?"
3. "Qual seção você usaria mais?"
4. "Falta algo importante?"
5. "Os ícones são claros?"
6. "A navegação é intuitiva?"

---

## 🔄 Próximas Fases

### Fase 03 (22/08)
- ✅ Prototipo visual (FEITO!)
- [ ] Feedback de usuários
- [ ] Iteração baseada em feedback
- [ ] Mockup Figma high-fidelity

### Fase 04 (15/10)
- [ ] Prototipo técnico (React Native)
- [ ] Navegação real
- [ ] Mapa de Conexões (D3.js)

### Fase 05 (05/11-16/12)
- [ ] Código completo
- [ ] Backend + GraphQL
- [ ] Banco de dados
- [ ] Deploy MVP

---

## 🐛 Limitações do Prototipo

O que AINDA NÃO é funcional:

- ❌ Search (busca) — apenas UI
- ❌ Botões "+ Novo" — apenas UI
- ❌ Mapa de Conexões — visual only
- ❌ Banco de dados — não persiste dados
- ❌ Backend — offline apenas

**Tudo será implementado em Fase 04-05.**

---

## 📞 Compartilhar Feedback

Depois de explorar:

**Envie:**
1. Printscreens das partes que mais gostou
2. Quais seções usaria mais
3. O que está confuso
4. Sugestões de melhoria

---

## 🚀 Próximo Passo

1. **Abra o prototipo no navegador** ← FAÇA ISSO AGORA
2. **Explore por 10-15 minutos**
3. **Teste no mobile** (redimensione ou vire o telefone)
4. **Envie feedback**

---

**Prototipo Status:** ✅ Versão 1 Completa  
**Criado em:** 25/07/2026  
**Para:** Fase 03 — Validação com Usuários

