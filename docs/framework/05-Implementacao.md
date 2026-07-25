# Fase 05 — Implementação

## 1. Por que essa fase existe?

Com produto e arquitetura aprovados, a implementação entrega valor em incrementos rastreáveis: cada mudança de código deve mapear para um fluxo, um critério de aceite e uma decisão arquitetural. Esta fase existe para construir com disciplina — não para redesenhar o sistema no meio do caminho.

## 2. Quais perguntas preciso responder?

- A Arquitetura (04) está documentada e aprovada pela usuária?
- Qual é o próximo incremento entregável (menor fatia útil)?
- Quais critérios de aceite desta fatia serão atendidos?
- Quais arquivos / módulos serão tocados e por quê?
- Como validamos (testes, checagem manual, observabilidade)?
- O que pode quebrar em produção nesta mudança?
- Há alteração de segurança, banco ou permissões? (exige explicação de impacto + confirmação)
- A definição de pronto desta entrega está clara?

## 3. O GPS da Fase

1. Confirmar gate: Fase 04 aprovada no Contexto Global.
2. Escolher o próximo incremento alinhado ao MVP e à arquitetura.
3. Implementar de ponta a ponta na fatia escolhida (sem meias soluções).
4. Indicar arquivo e trecho exatos em cada entrega relevante.
5. Cobrir critérios de aceite e registrar como foram verificados.
6. Se tocar segurança, banco ou permissões: explicar impacto, pedir confirmação, só então aplicar.
7. Alertar em **negrito** qualquer risco de quebra em produção.
8. Atualizar docs se a implementação revelar ajuste necessário (e revalidar com a usuária se for mudança arquitetural).
9. Marcar o incremento como pronto e escolher o próximo.

### Definição de pronto (mínima)

- Código alinhado à arquitetura aprovada
- Critérios de aceite da fatia atendidos
- Sem segredos (senhas, tokens, chaves) em arquivos
- Riscos de produção comunicados quando existirem
- Contexto Global / docs atualizados se houver decisão material

## 4. Controle de Qualidade/Checklist

- [ ] Gate da Fase 04 confirmado (aprovação da usuária)
- [ ] Incremento escolhido e critérios de aceite listados
- [ ] Solução completa entregue (arquivo + trecho indicados)
- [ ] Testes / verificação descritos ou executados
- [ ] Sem credenciais ou segredos nos arquivos
- [ ] Mudanças de segurança/banco/permissões confirmadas pela usuária (se houver)
- [ ] Riscos de produção avisados em **negrito** quando aplicável
- [ ] Docs e status do GPS atualizados após a entrega
