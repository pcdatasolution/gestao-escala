# Fluxo de trabalho com agentes

Governança operacional V1, consolidada a partir do [P01 e da validação T7](pilotos/P01-fluxo-operacional.md). Codex nativo coordena; Superpowers permanece adiado. Este processo não define stack nem aprova regras de produto.

## Planejamento proporcional

Leia [produto](../PRODUCT.md), [instruções](../AGENTS.md) e [fontes funcionais](engenharia-reversa/sintese-funcional.md) antes de propor implementação. D01–D20 estão abertas. Levante dependências de produto sem responder por conta própria.

Cada tarefa indica objetivo, autorização, fontes, arquivos permitidos, dependências, aceite, verificações e formato de retorno. Tarefas pequenas podem ser planejadas na conversa; planos duradouros ficam em documento próprio, identificado como plano, com estado e próxima ação.

Esse é o contrato mínimo de entrada da demanda. Registre a fonte e o alcance da autorização, o estado inicial do Git e as decisões de produto necessárias ainda pendentes. Antes de produzir, decomponha tarefas com responsável, dependências, arquivos e critérios de aceite verificáveis. Não invente defaults para completar o contrato.

O fluxo é demanda → investigação → especificação proposta → aprovação das decisões de produto necessárias → planejamento técnico → produção → verificações direcionadas → revisão independente → correções → entrega e documentação. Dimensione as etapas ao escopo; ausência de aplicação torna as etapas de código inaplicáveis, sem exigir stack ou instalação.

O coordenador executa escolhas técnicas locais dentro da autorização explícita e continua etapas autorizadas sem confirmações repetidas. Quando faltar decisão de produto indispensável, registre a pergunta e bloqueie somente a atividade dependente. Ampliação de escopo, custos, produção ou ações fora da autorização exigem aprovação pertinente.

Estados de tarefa: **não iniciado** (sem execução), **em andamento** (execução iniciada sem aceite comprovado), **concluído** (saída e aceite verificados) e **bloqueado** (dependência impeditiva identificada). Cada bloqueio registra motivo, impacto e próxima ação; o rótulo de conclusão não substitui evidências.

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

O briefing nomeia o proprietário de cada arquivo e informa que os demais trabalhos locais devem ser preservados. Antes de transferir ownership, confirme a parada do trabalhador anterior e inspecione suas alterações reais. Somente o coordenador integra e executa operações Git.

Cada agente retorna estado, caminhos/seções, evidências, achados com severidade quando pertinentes, dúvidas e limitações. Ausência de achados deve delimitar o exame.

Registre papel e identidade efetivamente acionados, versão do artefato e resultado recebido. Arquivo de configuração, autorrevisão ou relato sem execução não comprovam revisão independente. Se o papel necessário estiver indisponível, registre a revisão pendente em vez de simulá-la. `planning-reviewer` cobre planejamento e rastreabilidade; não se presume capacidade de revisão técnica de uma futura aplicação.

## Verificação e revisão

Defina checks antes de editar; execute os pertinentes. Neste estágio: hashes, referências, TOML e Git conforme [quality](quality.md). Não gere testes de aplicação inexistente.

Após produção, use revisor independente em leitura com requisitos, autorização, alterações reais e resultados. Identifique a versão examinada por SHA-256 ou revisão Git acompanhada do diff exato, incluindo arquivos novos. Registre achados, severidade, evidência e limites. Acréscimos posteriores não herdam o parecer anterior.

O escritor corrige achados pertinentes dentro do escopo; reexecute checks afetados e solicite nova revisão direcionada quando a correção alterar o conteúdo examinado. Uma rodada é correção seguida de verificação/revisão pertinente. Registre achados abertos e progresso verificável. Após duas rodadas sem progresso verificável, interrompa a atividade afetada e reporte; não aumente o limite nem aprove pendências silenciosamente.

Aceite cumprido, checks pertinentes aprovados e revisão requerida concluída permitem preparar entrega. Defeitos que comprometem aceite bloqueiam a entrega dependente. Pendências que não comprometem aceite devem ter responsável, justificativa e impacto; reduzir aceite exige aprovação humana, independentemente da severidade.

Após implementação ou correção, sugira 3 a 8 ciclos posteriores de revisão, proporcionais ao risco, sem iniciá-los automaticamente. Para este setup: três ciclos, com focos em fidelidade às fontes, configuração Codex/Git e retomada/descoberta. Cada ciclo examina o estado atual; correções internas não reiniciam a contagem.

## Decisões e passagem de contexto

Registre decisões futuras aprovadas em documento próprio com ID, data, aprovação explícita, motivação e impacto; atualize documentos afetados. Preserve fontes históricas.

Ao encerrar tarefa longa, registre objetivo, estado real, arquivos afetados, checks/resultados, decisões aprovadas, pendências e próxima ação, sem credenciais. Na retomada, confira Git, arquivos e processos reais. Uma nota anterior não prova execução ativa. Respeite pausa explícita e conclua apenas partes independentes de bloqueios.

Mantenha checkpoints persistentes após planejamento, produção, revisão e entrega, no documento autorizado da demanda: autorização, referência Git, estados, ownership, identidades dos agentes, comandos/resultados, versões revisadas, limitações e próxima ação. Registro documental sem commit não é checkpoint recuperável no histórico Git.

Na nova sessão, leia instruções e registro, reconcilie raiz, branch, HEAD, índice, alterações rastreadas e não rastreadas, integridade pertinente e processos/agentes reais. Separe evidência histórica de checks atuais; não repita tarefas concluídas sem divergência que justifique. Mudança legítima de HEAD exige reconciliação, nunca restauração ou descarte automático. Escrita depende da autorização vigente; não inicie outra sessão automaticamente.

## Checkpoints Git e entrega

Commits locais exigem autorização explícita aplicável à tarefa, inclusive quando já concedida no pedido. Após aceite, revisão e checks, inspecione o conjunto a versionar e inclua somente arquivos autorizados em unidades coerentes. Confira o índice antes do commit e o hash, conteúdo e status depois. Preserve trabalho local alheio; falha relevante impede o commit até resolução.

Autorização de commit não autoriza push. Push, integração externa e publicação dependem de autorização própria; não são consequência automática de concluir a tarefa. Relate o commit real e pendências, sem antecipar sucesso. A entrega inclui alterações, motivo, validações, alcance da revisão, limitações e próxima ação.
