# PR Review Checklist (GPS)

Use este checklist como referência para revisar mudanças dentro do Framework de Projetos (GPS).

1. Contexto & Alinhamento
   - [ ] O autor leu e referenciou `docs/framework/01-Contexto-Global.md`.
   - [ ] As mudanças respeitam restrições e objetivos definidos no Contexto Global.

2. Arquitetura
   - [ ] Se a mudança toca arquitetura, `docs/framework/04-Arquitetura.md` foi consultada e atualizada.
   - [ ] Decisões arquiteturais relevantes estão registradas (ADR ou seção no documento).

3. Segurança, Dados e Permissões
   - [ ] Mudanças em segurança, banco de dados ou permissões contêm explicação de impacto.
   - [ ] A usuária responsável foi consultada e confirmou a mudança quando necessário.
   - [ ] Não há credenciais, tokens ou chaves nos diffs.

4. Qualidade do Código & Testes
   - [ ] Código legível e modular.
   - [ ] Testes automatizados cobrem casos novos/alterados sempre que aplicável.
   - [ ] Passes de CI local/automático verificados.

5. Documentação
   - [ ] Arquivos e trechos modificados foram indicados na PR.
   - [ ] Documentação pertinente (docs/framework/XX ou README) atualizada conforme necessário.

6. Riscos e Deploy
   - [ ] Riscos de produção identificados e comunicados (marcados em **negrito** na PR).
   - [ ] Plano de rollback simples documentado se aplicável.

7. Aprovação
   - [ ] Comentários do revisor foram respondidos e tratados.
   - [ ] Aprovador(es) indicado(s) e data da aprovação registrada em `docs/framework/01-Contexto-Global.md` se for mudança material.

