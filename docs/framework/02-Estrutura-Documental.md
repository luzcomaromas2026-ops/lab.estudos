# Fase 02 — Estrutura Documental

## 1. Por que essa fase existe?

Documentação sem estrutura vira ruído: arquivos duplicados, decisões perdidas e ninguém sabe qual versão vale. Esta fase define onde cada tipo de informação mora, como nomear, o que é fonte da verdade e como o GPS se conecta ao repositório — para que produto, arquitetura e código falem a mesma língua.

## 2. Quais perguntas preciso responder?

- Quais documentos são obrigatórios neste projeto e quais são opcionais?
- Qual é a fonte da verdade para produto, arquitetura, decisões e runbooks?
- Como nomeamos pastas e arquivos (padrão, idioma, versionamento)?
- O que fica em `docs/framework/` versus docs de produto/técnicos específicos?
- Como registramos decisões (ADR, changelog, comentários no Contexto Global)?
- Quem pode editar o quê e quando um documento precisa de reaprovação?
- Como evitamos duplicar o mesmo conteúdo em dois lugares?

## 3. O GPS da Fase

1. Confirmar a árvore canônica do GPS em `docs/framework/`.
2. Definir pastas adicionais do projeto (ex.: `docs/produto/`, `docs/arquitetura/`, `docs/adr/`) se necessário.
3. Estabelecer nomenclatura e idioma padrão dos documentos.
4. Declarar a fonte da verdade por tema (produto, arquitetura, segurança, operações).
5. Definir o fluxo de atualização: mudança → documento da fase → Contexto Global.
6. Criar um índice curto no Contexto Global apontando para cada documento vivo.
7. Remover ou arquivar rascunhos órfãos que competem com a fonte da verdade.

### Árvore canônica do GPS

```text
docs/framework/
├── 00-Descoberta.md
├── 01-Contexto-Global.md      ← documento mestre
├── 02-Estrutura-Documental.md
├── 03-Descoberta-do-Produto.md
├── 04-Arquitetura.md
├── 05-Implementacao.md
└── 06-Evolucao.md
```text

## 4. Controle de Qualidade/Checklist

- [ ] Árvore documental definida e refletida no repositório
- [ ] Fonte da verdade por tema declarada
- [ ] Padrão de nomenclatura documentado
- [ ] Fluxo de atualização (fase → Contexto Global) explícito
- [ ] Índice de documentos linkado no Contexto Global
- [ ] Sem documentos duplicados conflitantes
- [ ] Regras de edição/aprovação claras para docs sensíveis (segurança, permissões, dados)
