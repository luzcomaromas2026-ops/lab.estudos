# Fase 04 — Arquitetura

## 1. Por que essa fase existe?

Arquitetura transforma o produto em limites técnicos claros: componentes, dados, segurança, integrações e riscos. Implementar sem arquitetura aprovada gera retrabalho, dívida oculta e decisões irreversíveis tomadas “no calor do código”. No GPS, a Fase 05 (Implementação) só começa depois desta fase estar documentada e aprovada pela usuária.

## 2. Quais perguntas preciso responder?

- Quais componentes / serviços existem e qual a responsabilidade de cada um?
- Quais tecnologias e restrições de stack já estão definidas no Contexto Global?
- Como os dados são modelados, onde vivem e quem pode acessá-los?
- Quais fluxos de autenticação, autorização e permissões se aplicam?
- Quais integrações externas existem e quais são os contratos?
- O que precisa escalar, o que precisa ser simples, e onde está o trade-off?
- Quais riscos técnicos, de segurança e de operação estão abertos?
- O que é decisão permanente (ADR) versus experimento reversível?

## 3. O GPS da Fase

1. Partir dos fluxos e critérios de aceite da Descoberta do Produto (03).
2. Desenhar o diagrama de contexto e os limites de responsabilidade.
3. Definir modelo de dados em alto nível e ownership dos dados.
4. Documentar autenticação, autorização, permissões e impacto de segurança.
5. Listar integrações, contratos e falhas esperadas.
6. Registrar decisões arquiteturais relevantes (ADR ou seção dedicada).
7. Explicitar riscos e mitigações.
8. Submeter à aprovação da usuária antes de qualquer código de implementação.
9. Atualizar o Contexto Global: Fase 04 aprovada (ou bloqueada com pendências).

### Aviso de gate

**Não avance para a Fase 05 nem sugira código de implementação enquanto este documento não estiver completo e aprovado pela usuária.**

## 4. Controle de Qualidade/Checklist

- [ ] Diagrama / descrição de componentes e responsabilidades
- [ ] Modelo de dados e ownership documentados
- [ ] Autenticação, autorização e permissões descritos
- [ ] Integrações e contratos listados
- [ ] Decisões relevantes registradas (com racional)
- [ ] Riscos e mitigações explícitos
- [ ] Alinhamento com restrições do Contexto Global verificado
- [ ] Arquitetura aprovada pela usuária
- [ ] Status da Fase 04 atualizado no Contexto Global
