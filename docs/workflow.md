# Fluxo de trabalho com agentes

## Planejamento proporcional

Leia [produto](../PRODUCT.md), [instruções](../AGENTS.md) e [fontes funcionais](engenharia-reversa/sintese-funcional.md) antes de propor implementação. D01–D20 estão abertas. Levante dependências de produto sem responder por conta própria.

Cada tarefa indica objetivo, autorização, fontes, arquivos permitidos, dependências, aceite, verificações e formato de retorno. Tarefas pequenas podem ser planejadas na conversa; planos duradouros ficam em documento próprio, identificado como plano, com estado e próxima ação.

## Responsabilidades

| Papel | Quando usar | Limite |
|---|---|---|
| Coordenador | Planejar, integrar e conferir entrega | Responsável por configuração compartilhada e Git |
| evidence-researcher | Localizar evidências e limites nos fluxos e síntese | Somente leitura; não decide requisitos |
| planning-reviewer | Revisar planos e rastreabilidade contra fontes e autorização | Somente leitura; não implementa nem aprova produto |

Os agentes são definidos em `.codex/agents/`. Precisam ser descobertos e executados pelo cliente; veja [teste](onboarding.md). Leitura é instrução de comportamento, não um sandbox independente.

## Delegação

Delegue quando especialização, isolamento de contexto ou paralelismo compensarem o custo. Comece com no máximo dois trabalhadores, sem delegação recursiva, respeitando limites menores do host. Preserve modelo, provedor, autenticação e permissões vigentes.

Um arquivo tem um escritor. Revisores retornam achados ao responsável, sem editar. Tarefas paralelas precisam ser independentes e ter conjuntos de escrita disjuntos. Etapas dependentes são sequenciais. O coordenador aguarda e verifica fontes e alterações reais.

Cada agente retorna estado, caminhos/seções, evidências, achados com severidade quando pertinentes, dúvidas e limitações. Ausência de achados deve delimitar o exame.

## Verificação e revisão

Defina checks antes de editar; execute os pertinentes. Neste estágio: hashes, referências, TOML e Git conforme [quality](quality.md). Não gere testes de aplicação inexistente.

Após implementação ou correção, sugira 3 a 8 ciclos posteriores de revisão, proporcionais ao risco, sem iniciá-los automaticamente. Para este setup: três ciclos, com focos em fidelidade às fontes, configuração Codex/Git e retomada/descoberta. Cada ciclo examina o estado atual; correções internas não reiniciam a contagem.

## Decisões e passagem de contexto

Registre decisões futuras aprovadas em documento próprio com ID, data, aprovação explícita, motivação e impacto; atualize documentos afetados. Preserve fontes históricas.

Ao encerrar tarefa longa, registre objetivo, estado real, arquivos afetados, checks/resultados, decisões aprovadas, pendências e próxima ação, sem credenciais. Na retomada, confira Git, arquivos e processos reais. Uma nota anterior não prova execução ativa. Respeite pausa explícita e conclua apenas partes independentes de bloqueios.
