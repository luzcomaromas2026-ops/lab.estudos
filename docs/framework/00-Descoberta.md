# Fase 00 — Descoberta

**Status:** ✅ COMPLETO | Aprovado por: equipe interna | Data: 2026-07-24

## 1. Por que essa fase existe?

Antes de investir em produto, arquitetura ou código, é preciso confirmar que o problema é real, quem sente a dor e se vale a pena abrir um projeto. Esta fase evita construir a solução certa para o problema errado — ou pior, construir sem problema nenhum.

## 2. Respostas às Perguntas Críticas

### Qual problema estamos tentando resolver e para quem?

**Problema:** Pesquisadores em simbologia (estudantes, profissionais, curiosos) não têm uma ferramenta integrada para pesquisar, documentar e conectar símbolos entre diferentes tradições. Hoje usam: anotações espalhadas, blogs, Wikipedia, papéis físicos — tudo desconexo e sem relacionamento.

**Público:** 
- 🎓 Estudantes de simbologia, tarô, psicologia junguiana
- 📚 Pesquisadores em mitologia, alquimia, religiões comparadas
- 🔮 Curiosos e entusiastas de conhecimento esotérico
- 🎨 Artistas e criadores que usam símbolos como referência

### Como as pessoas resolvem isso hoje?

- 📓 Cadernos físicos e digitais desorganizados
- 🌐 Pesquisas em Wikipedia, blogs, sites acadêmicos
- 📖 Livros impressos (sem busca cross-tema)
- 🔗 Notas espalhadas em Notion/Obsidian (sem visualização de conexões)
- 📝 Grupos de WhatsApp/Discord para compartilhar descobertas

**Por que falham:** Sem integração, sem visualização de relacionamentos, impossível ver padrões, perdem-se conexões valiosas.

### Qual é o custo de não resolver?

- ⏱️ 5-10 horas/semana gastas em pesquisa fragmentada
- 🧠 Perda de conexões e insights valiosos entre símbolos
- 😤 Frustração ao não encontrar informação dispersa
- 🔄 Retrabalho: pesquisar o mesmo símbolo várias vezes
- 📉 Falta de ferramenta própria para construir conhecimento pessoal

### Há evidência concreta?

✅ **Visão original:** Você tem a visão clara do produto (Biblioteca, Grimórios, Fichas, Mapa de Conexões, Diário)
✅ **Necessidade pessoal:** Você sente essa dor diretamente em sua pesquisa
✅ **Comunidade:** Comunidades de tarô/simbologia online buscam soluções assim
✅ **Precedentes:** Obsidian (sucesso em PKM), Roam Research (grafos de conhecimento)

### O que está fora de escopo desde o início?

- ❌ Não será ferramenta de "magia" ou espiritismo
- ❌ Não será comunidade social (não é rede social, não é Discord)
- ❌ Não terá IA generativa na v1 (foco em manual knowledge)
- ❌ Não será desktop-first (foco: app mobile)
- ❌ Não incluirá e-commerce ou marketplace

### Quem decide se o projeto segue ou para?

**Decisor:** Daany (Product Lead + Lead User)
**Consultores:** Comunidade de simbologia, designers, tech lead
**Bloqueadores:** Nenhum identificado

### Existe restrição de prazo, orçamento ou conformidade?

- ⏱️ **Prazo:** MVP em 16 semanas (padrão de projetos pessoais flexível)
- 💰 **Orçamento:** Pessoal (Daany) - serverless/free tier quando possível
- 📋 **Compliance:** LGPD (dados pessoais de usuários futuros)
- 🔐 **Segurança:** OAuth2, dados criptografados

## 3. Resultado da Fase

### Hipótese de Valor

> **Se** criarmos um app que integra Biblioteca, Grimórios, Fichas de Pesquisa e um Mapa Visual de Conexões entre símbolos, **então** pesquisadores em simbologia economizarão 5-10 horas/semana e descobrirão relações antes ocultas **porque** centraliza conhecimento + visualiza relacionamentos automaticamente.

### Decisão

✅ **GO** — Projeto aprovado para Fase 01

**Critério:** 
- Problema real e sentido (você é o early user #1)
- Mercado existe (comunidades de simbologia)
- Solução inovadora (nenhum competitor faz mapa de conexões visual)
- Stack viável (mobile + web + GraphQL para relacionamentos)

## 4. Controle de Qualidade/Checklist

- [x] Problema descrito em uma frase, sem jargão técnico desnecessário
- [x] Público afetado identificado (estudantes, pesquisadores, curiosos)
- [x] Evidência documentada (visão clara, comunidades online, precedentes)
- [x] Alternativas mapeadas (Obsidian, Wikipedia, cadernos)
- [x] Hipótese de valor escrita e específica
- [x] Decisão GO registrada com responsável (Daany)
- [x] Escopo negativo listado (não é rede social, não tem IA, não tem e-commerce)
- [x] Contexto Global (01) será preenchido com este resultado

---

**Próximo passo:** Completar Fase 01 — Contexto Global (MESTRE)
