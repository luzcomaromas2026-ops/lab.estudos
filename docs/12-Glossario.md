# 📚 Glossário

**Laboratório de Simbologia — Termos do Projeto**

---

## 🔤 Termos Técnicos

**Ontologia**
Mapa de como símbolos se relacionam. Estrutura de dados que define: tipos, significados, relacionamentos, contextos.

**RLS (Row-Level Security)**
Política de banco que garante usuários só veem seus dados. CRÍTICO para LGPD.

**JWT**
Token de autenticação. Contém user ID + claims, assinado com secret.

**GraphQL**
Query language para API. Permite cliente pedir só campos necessários (vs REST que retorna tudo).

**PostgreSQL**
Banco de dados relacional. Usado via Supabase. Tem vetores (pgvector) para embeddings futuros.

---

## 🎯 Termos de Produto

**Laboratório**
O app em si. Espaço pessoal onde você pesquisa e conecta símbolos.

**Observatório**
A navegação central. Um círculo (Laboratório) com 5 constelações ao redor (5 módulos).

**Constelação**
Um dos 5 módulos principais: Biblioteca, Grimórios, Fichas, Mapa, Diário.

**Símbolo**
Qualquer coisa que representa algo além de si mesma. Coruja, Lua, Ametista, A Sacerdotisa, etc.

**Ficha de Pesquisa**
Documento estruturado sobre um símbolo. Contém: tipos, significados, relacionamentos, contextos, origem, observações.

**Significado**
O que um símbolo representa. Ex: "Coruja = Sabedoria". Pode ter múltiplos em diferentes tradições.

**Relacionamento**
Conexão entre dois símbolos. Ex: "Coruja origem_de A Sacerdotisa".

**Contexto**
Tradição/cultura onde símbolo aparece. Ex: "Mitologia Grega", "Tarô", "Psicologia Junguiana".

**Biblioteca**
Módulo para gerenciar referências (livros, artigos, PDFs).

**Grimório**
Caderno temático. 9 tipos padrão (Tarô, Sonhos, Cores, Animais, Arquétipos, Mitologia, Alquimia, Religiões, Psicologia) + custom.

**Entrada de Grimório**
Uma anotação dentro de um grimório. Cronológica, pessoal. Pode ter um Registro de Estudo associado.

**Registro de Estudo (Study Record)**
Subsegmento opcional de uma Entrada de Grimório. Rastreia o progresso de aprendizado sobre um tema específico.
Contém: objetivo, status (pendente/em_progresso/concluído), progresso (%), horas investidas, aprendizados, próximos passos.

**Diário do Laboratório**
Timeline cronológica de suas reflexões sobre símbolos.

**Mapa de Conexões**
Visualização de grafo mostrando como símbolos se conectam.

---

## 🏗️ Termos Arquiteturais

**React Native**
Framework para criar apps mobile em JavaScript. Funciona iOS + Android + Web.

**Flutter**
Framework para criar apps mobile em Dart. Alternativa a React Native.

**Supabase**
Backend as a Service. Providencia: PostgreSQL, Auth, Storage, Real-time.

**Vercel**
Platform para deploy. Usado para: Next.js (web), serverless functions (API).

**D3.js**
Biblioteca para visualizar dados. Perfeita para grafos de símbolos.

**Cytoscape.js**
Alternativa a D3 para grafos. Mais otimizada para network visualization.

**TLS 1.3**
Protocolo de criptografia. Garante dados em trânsito (HTTPS) seguros.

**AES-256**
Algoritmo de criptografia. Usado para dados em repouso (banco).

**OAuth2**
Protocolo de autenticação. Permite login com Google, GitHub, etc.

---

## 📊 Termos de Dados

**Usuário**
Pessoa que usa o app. Referenciada por `user_id` (UUID).

**Tabela**
Estrutura de dados em PostgreSQL. Contém rows com colunas.

**Query**
Pergunta ao banco de dados. Ex: "SELECT * FROM symbols WHERE user_id = X".

**Índice**
Estrutura que acelera buscas. Essencial para performance em tabelas grandes.

**Soft Delete**
Marcar com `deleted_at` em vez de remover fisicamente. Necessário para LGPD (direito ao esquecimento).

**Audit Log**
Registro de todas as ações de usuário. CRÍTICO para compliance.

---

## 🎨 Termos de Design

**Observatório**
A navegação principal. Conceito visual + funcional.

**Constelação**
Visual metaphor para cada módulo ao redor do Laboratório central.

**Dark Mode**
Tema escuro. Suportado mas não é MVP.

**Acessibilidade (a11y)**
Design inclusivo. WCAG 2.1 AA é o target.

**Micro-interação**
Animação pequena que comunica feedback. Ex: scale ao clicar.

**Design System**
Conjunto de componentes + regras de design reutilizáveis.

---

## ⚖️ Termos Legais/Compliance

**LGPD**
Lei Geral de Proteção de Dados (Brasil). Nosso compliance principal.

**GDPR**
Regulamento de proteção de dados europeu. Referência inspiradora.

**DPIA**
Data Protection Impact Assessment. Análise de risco de privacidade.

**DPA**
Data Processing Agreement. Contrato entre nós + qualquer processor de dados.

**Consentimento**
Usuário explicitamente concorda com termos. Gravado quando sign up.

**Direito ao Esquecimento**
Usuário pode pedir para apagar dados. Implementado via soft delete + purge.

**Direito de Portabilidade**
Usuário pode exportar seus dados. API: GET /api/export/my-data.json

**Audit Log**
Rastreamento de quem fez o quê, quando. Necessário para LGPD.

---

## 🎓 Termos de Simbologia

**Arquétipo**
Padrão universal do inconsciente humano. Jung: Herói, Sombra, Anima/Animus, Ancião.

**Significado Múltiplo**
Um símbolo pode ter muitos significados legítimos em contextos diferentes. Feature, não bug.

**Sincronicidade**
Coincidência significativa. Conceito Jung: quando eventos desconexos parecem conectados.

**Inconsciente**
Parte da mente fora de percepção consciente. Símbolos acessam isso.

**Tradição**
Sistema de conhecimento sobre símbolos. Ex: Tarô, Mitologia, Alquimia.

**Grimório**
Livro de conhecimento. Aqui = caderno digital temático.

---

**Criado em:** 25/07/2026  
**Status:** Vivo (atualizar conforme novo termos surgirem)
