# Gestão Escala — contexto de produto

## Objetivo declarado

Apoiar o gestor no planejamento semanal de pessoas, dias e horários, com cenário inicial de farmácia 24h. Este documento organiza o escopo declarado; não é a especificação funcional final nem aprova regras abertas.

## Escopo declarado para discussão do MVP

- Calendário semanal de pessoas × dias × horários.
- Atribuição de turnos, folgas e indisponibilidades.
- Reorganização de pessoas e identificação de conflitos.
- Identificação de horários ou turnos descobertos.
- Continuidade entre datas na operação 24h.

Operações, semântica, validações e critérios específicos dependem das decisões abertas. Papéis de acesso, dados mínimos, stack e arquitetura ainda não foram definidos.

## Fontes e limites

A [síntese funcional](docs/engenharia-reversa/sintese-funcional.md) conecta os três fluxos da referência PontoCorp. As fontes distinguem observações, inferências e comportamentos não verificados. Capacidades observadas na referência não se tornam automaticamente requisitos do Gestão Escala.

## Decisões em aberto

**D01–D20 permanecem explicitamente em aberto**, conforme a seção 7 da síntese. Nenhuma resposta foi aprovada por este setup. Começar por D01, D02, D03, D04 e D07 é sugestão da síntese, não uma decisão funcional.

Escolhas futuras devem registrar aprovação, contexto e impacto em documento próprio. Não reescreva evidências históricas para fazê-las parecer compatíveis com escolhas novas.

## Limites atuais

Não há aplicação, banco, autenticação, API ou interface implementada. Não há stack definida. CPF, ponto, banco de horas, QR, licenças e compliance CCT avançado não devem ser importados da referência como requisitos do núcleo inicial.

## Próxima entrega e aceite

Primeiro validar os agentes em nova sessão. Depois pode ser proposto um índice de rastreabilidade de D01–D20, sem respondê-las nem alterar fontes. O aceite desse índice seria conter as 20 decisões, referências verificáveis e limites das evidências; sua criação não faz parte deste setup.

Critérios de aceite das funcionalidades ainda dependem das decisões aprovadas. Critérios técnicos deste setup estão em [quality](docs/quality.md).
