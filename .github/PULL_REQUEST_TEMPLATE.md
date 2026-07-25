<!-- Título curto e objetivo da PR --> 
**Resumo rápido:** Descreva em 1-2 linhas o objetivo desta PR.

<!-- O que foi alterado e por quê -->
## Mudanças
- Lista curta das mudanças implementadas (arquivos principais e trechos relevantes).

## Documentação relacionada
- Link para `docs/framework/01-Contexto-Global.md` e outras fases relevantes.
- Se aplicável, link para ADRs ou decisões arquiteturais.

## Checklist mínimo (obrigatório)
- [ ] Li o `docs/framework/01-Contexto-Global.md` e confirmei alinhamento com restrições e objetivos.
- [ ] Para alterações que tocam arquitetura: a Fase 04 (`docs/framework/04-Arquitetura.md`) está atualizada e aprovada.
- [ ] Expliquei claramente qualquer mudança em segurança, banco de dados ou permissões e solicitei confirmação da usuária (se aplicável).
- [ ] Não existem senhas, tokens ou chaves no código ou nos arquivos modificados.
- [ ] Indiquei arquivo(s) e trecho(s) exatos na PR (linhas/arquivos) quando relevante.
- [ ] Testes automatizados adicionados/atualizados quando aplicável.
- [ ] Passes locais de build/test foram executados com sucesso.
- [ ] Expliquei riscos potenciais de produção (se houver) e marquei-os em **negrito** na descrição.
- [ ] Esta PR está pronta para revisão (assign reviewer / label).

## Checklist de revisão do revisor
- [ ] As mudanças estão alinhadas com o Contexto Global?
- [ ] Há evidência de que a Arquitetura foi considerada (quando aplicável)?
- [ ] Mudanças de segurança/banco/permissões foram justificadas e aprovadas?
- [ ] Código claro, teste(s) suficientes e documentação atualizada?
- [ ] Não há segredos nos diffs?
- [ ] Comentários do revisor tratados antes da aprovação final?

<!-- Instruções de deploy ou notas importantes -->
## Notas de deploy / rollback
- Indique passos de deploy e rollback se relevantes.

