# Fase 06 — Evolução

## 1. Por que essa fase existe?

Produto em produção não “termina”: feedback, débito técnico, mudanças de negócio e incidentes exigem um ciclo consciente de evolução. Esta fase garante que o GPS continue girando — voltando ao contexto, ao produto ou à arquitetura quando a mudança for estrutural, em vez de acumular patches sem norte.

## 2. Quais perguntas preciso responder?

- O que aprendemos com usuários, métricas e incidentes desde a última entrega?
- O MVP ainda é o alvo certo ou o escopo precisa mudar?
- Quais débitos técnicos ou de documentação estão bloqueando velocidade/qualidade?
- A mudança pedida é feature, correção, ou quebra de arquitetura/contexto?
- Precisamos voltar para a Fase 03 (produto), 04 (arquitetura) ou só iterar na 05?
- Quais métricas de sucesso do Contexto Global melhoraram ou pioraram?
- O que deve ser arquivado, descontinuado ou simplificado?

## 3. O GPS da Fase

1. Coletar feedback e evidências (uso, suporte, métricas, pós-mortem).
2. Classificar cada pedido: evolução incremental vs. mudança de produto vs. mudança de arquitetura.
3. Atualizar o Contexto Global com aprendizados e novos riscos.
4. Se mudar escopo/jornadas → reabrir Descoberta do Produto (03) e reaprovar.
5. Se mudar limites técnicos/dados/segurança → reabrir Arquitetura (04) e reaprovar.
6. Se for incremento alinhado → voltar à Implementação (05) com critérios claros.
7. Priorizar e pagar débito técnico que ameace estabilidade ou velocidade.
8. Revisar a estrutura documental (02) se a fonte da verdade tiver divergido do código.

### Ciclo de retorno

```text
Evidência → Classificar → Atualizar Contexto Global
                │
                ├─ produto    → Fase 03 → (04 se necessário) → 05
                ├─ arquitetura → Fase 04 → 05
                └─ incremento  → Fase 05
```text

## 4. Controle de Qualidade/Checklist

- [ ] Feedback e evidências da rodada registrados
- [ ] Pedidos classificados (produto / arquitetura / incremento)
- [ ] Contexto Global atualizado
- [ ] Reaberturas de fase (03/04) feitas quando necessário e reaprovadas
- [ ] Débitos críticos priorizados ou explicitamente adiados com motivo
- [ ] Métricas de sucesso revisadas
- [ ] Documentação alinhada ao estado real do sistema
- [ ] Próximo ciclo do GPS definido (fase e dono)
