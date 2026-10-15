# Gestão Escala — instruções para agentes

## Contexto obrigatório

O projeto está em documentação e engenharia reversa, sem código ou stack de aplicação definida. Leia [PRODUCT.md](PRODUCT.md) e a [síntese funcional](docs/engenharia-reversa/sintese-funcional.md) antes de propor implementação. Consulte os três fluxos vinculados na síntese para confirmar evidências.

- Preserve integralmente os quatro documentos de `docs/engenharia-reversa/` neste setup. Alterações futuras nessas fontes exigem pedido explícito e preservação da proveniência.
- Preserve **OBSERVADO**, **INFERIDO** e **NÃO VERIFICADO**. Uma lacuna de teste não significa inexistência de capacidade no PontoCorp.
- D01–D20 permanecem abertas. Não preencha defaults nem transforme hipóteses em requisitos aprovados. Registre decisões futuras somente com aprovação explícita, fonte e impacto.
- Comportamentos e números do PontoCorp não são automaticamente regras do Gestão Escala.

## Execução e escopo

Leia instruções e arquivos pertinentes antes de editar. Planeje objetivo, arquivos permitidos, dependências, aceite e verificações conforme [workflow](docs/workflow.md). Faça a menor mudança completa, preserve trabalho local e atualize a documentação responsável.

A governança operacional V1 está no workflow, baseada no P01 e na retomada T7. O coordenador conduz as etapas autorizadas sem pedir confirmação a cada delegação. Decisões técnicas locais são autônomas dentro da autorização explícita; decisões de produto pendentes bloqueiam apenas atividades dependentes. Superpowers permanece adiado.

Verificações devem ser proporcionais; veja [quality](docs/quality.md). Instalação, desenvolvimento, lint, tipos, build e testes de aplicação estão indisponíveis porque não há aplicação. Não escolha stack para reproduzir defaults do toolkit.

Não altere permissões, propriedade ou configuração global. Não acesse produção, execute operações destrutivas ou introduza custos sem autorização pertinente. Não crie commits nem faça push sem autorização posterior. Plugins, hooks, MCPs e dependências estão fora deste setup.

## Delegação e revisão

Delegue tarefas independentes quando isolamento de contexto ou especialização trouxer benefício real. Para tarefas simples, prefira execução direta ou ferramentas determinísticas. Use revisores separados quando pertinente.

- Use `evidence-researcher` e `planning-reviewer` apenas quando descobertos pelo cliente; arquivo presente não prova funcionamento.
- Cada briefing inclui objetivo, contexto mínimo, arquivos permitidos, dependências, aceite, checks e retorno esperado. Pesquisadores e revisores trabalham em leitura.
- Um escritor por arquivo; o coordenador cuida da integração e operações Git. Paralelize apenas tarefas independentes com arquivos de escrita disjuntos.
- Preserve modelo, provedor, autenticação e permissões da sessão. Não configure outra cobrança para delegar.
- O coordenador confere evidências e alterações reais. Limite tentativas e confirme a parada de agentes antes de assumir seus arquivos.
- Após duas rodadas de correção sem progresso verificável, interrompa a atividade afetada e reporte achados, tentativas e próxima ação, conforme workflow. Não declare conclusão por atingir o limite.

## Git neste executor

Enquanto o executor tiver identidade distinta do proprietário, use em toda invocação Git neste repositório:

```powershell
git -c safe.directory=C:/Users/Pedro/repos/saas-factory/gestao-escala status --short
```

A exceção vale por comando. Nunca persista `safe.directory` globalmente nem altere o Git ancestral. Esse caminho é a exceção local autorizada, não um default portátil.

## Continuidade

Na retomada, confira arquivos, Git e resultados reais. Registre estado, evidências, pendências e próxima ação conforme workflow. Responda a pedidos de status e continue trabalho autorizado; respeite pausas e limites. Bloqueios parciais afetam apenas suas dependências. Não prometa execução após o turno sem processo verificável.

Após implementação ou correção, recomende de 3 a 8 ciclos posteriores de revisão com focos e checks pertinentes, sem iniciá-los automaticamente. É convenção do toolkit, não garantia de qualidade.
