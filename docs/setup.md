# Setup e evidências — Gestão Escala

## Origem e escopo

Data: 15/10/2026. Adoção local autorizada do Vibe Coding Toolkit, revisão fixa `f13bb354363dafef8ce8d8f605856cc9e1cc52cc`. Estágio: documentação e engenharia reversa, sem stack de aplicação definida. Nenhuma decisão D01–D20 foi respondida.

Templates consultados anteriormente e disponíveis no contexto desta execução:

- [AGENTS.md.template](https://github.com/soumatheusgomes/vibe-coding-toolkit/blob/f13bb354363dafef8ce8d8f605856cc9e1cc52cc/templates/AGENTS.md.template).
- [README.md.template](https://github.com/soumatheusgomes/vibe-coding-toolkit/blob/f13bb354363dafef8ce8d8f605856cc9e1cc52cc/templates/project-docs/README.md.template).
- [product.md.template](https://github.com/soumatheusgomes/vibe-coding-toolkit/blob/f13bb354363dafef8ce8d8f605856cc9e1cc52cc/templates/product.md.template).
- [setup.md.template](https://github.com/soumatheusgomes/vibe-coding-toolkit/blob/f13bb354363dafef8ce8d8f605856cc9e1cc52cc/templates/project-docs/setup.md.template).
- [onboarding.md.template](https://github.com/soumatheusgomes/vibe-coding-toolkit/blob/f13bb354363dafef8ce8d8f605856cc9e1cc52cc/templates/project-docs/onboarding.md.template).
- [quality.md.template](https://github.com/soumatheusgomes/vibe-coding-toolkit/blob/f13bb354363dafef8ce8d8f605856cc9e1cc52cc/templates/project-docs/quality.md.template).

[Prompt de integração](https://github.com/soumatheusgomes/vibe-coding-toolkit/blob/f13bb354363dafef8ce8d8f605856cc9e1cc52cc/docs/prompts/12-existing-project-setup.md), [guia Codex](https://github.com/soumatheusgomes/vibe-coding-toolkit/blob/f13bb354363dafef8ce8d8f605856cc9e1cc52cc/docs/tools/15-codex-workflow.md) e [manifesto](https://github.com/soumatheusgomes/vibe-coding-toolkit/blob/f13bb354363dafef8ce8d8f605856cc9e1cc52cc/templates/project-docs/manifest.json) orientam a adaptação. Não houve download nem execução de script remoto nesta retomada.

Os TOMLs são definições próprias do projeto no formato nativo documentado do [Codex](https://learn.chatgpt.com/docs/agent-configuration/subagents); não são cópias de agentes Claude. Instruções de leitura não criam sandbox separado.

## Ambiente e Git na instalação

Raiz independente: `C:\Users\Pedro\repos\saas-factory\gestao-escala`. Branch `main`; origin fetch/push `https://github.com/pcdatasolution/gestao-escala`. Ainda sem commits. O diagnóstico anterior consultou o remoto e não encontrou referências; não foi repetida consulta de rede nesta retomada.

Executor observado no diagnóstico: `desktop-0mqsiai\codexsandboxoffline`, diferente do proprietário Pedro. Em todas as invocações Git desta execução foi usada a exceção transitória `-c safe.directory=C:/Users/Pedro/repos/saas-factory/gestao-escala`. Nenhuma configuração global ou permissão foi alterada e o repositório ancestral não foi reconfigurado.

Versões observadas no diagnóstico: Git 2.42.0.windows.2, Node 24.19.0, npm 11.17.0 e Codex CLI 0.162.0-alpha.17.2. Não são dependências de aplicação. Python 3.11.3 foi confirmado nesta execução em `C:/Users/Pedro/.pyenv/pyenv-win/versions/3.11.3/python.exe` para usar `tomllib` sem instalar pacotes. `py -3` não encontrou runtime e o shim python não tem versão selecionada; nenhuma configuração pyenv foi alterada.

## Adaptações e cobertura na instalação

| Componente | Decisão | Estado |
|---|---|---|
| Instruções compartilhadas e contexto | AGENTS curto e documentos referenciados | Configurado localmente |
| Planejamento, delegação e revisão | Workflow e dois agentes especializados | Configurado; execução pendente |
| Memória | Documentação versionável e handoff sob demanda | Configurado; sem memória externa |
| Superpowers, Ponytail e Caveman | Fora do escopo autorizado | Não instalados; apenas princípios de processo adaptados |
| Context7 | Adiado | Sem MCP novo |
| RTK | Adiado | Sem CLI ou hook novo |
| Graphify | Adiado, base documental pequena | Sem grafo ou dependência |
| Obsidian e memória Claude | Desnecessários neste estágio/cliente | Não configurados |
| ESLint/Biome e quality gates de aplicação | Sem código ou stack | Inaplicáveis agora |
| Skills Vercel e find-skills | Sem tarefa de framework/discovery | Não duplicadas nem instaladas |
| Navegador e Chrome DevTools | Sem interface local | Adiados |
| Skills de artefatos/criação e extras | Usar capacidades existentes sob demanda | Sem instalação |
| Plugins Claude/aia-harness/hooks | Fora do escopo | Não configurados |
| Scaffold e templates Next/banco | Sem autorização para aplicação ou stack | Não aplicados |

Não foram alterados modelo, provedor, autenticação ou permissões. Nenhum subagente foi executado nesta instalação. As regras futuras preservam herança e limitam delegação a trabalho pertinente, com um escritor por arquivo e revisão em leitura.

## Arquivos e mapa do manifesto

Criados: [README](../README.md), [AGENTS](../AGENTS.md), [PRODUCT](../PRODUCT.md), este setup, [onboarding](onboarding.md), [quality](quality.md), [workflow](workflow.md), [.gitignore](../.gitignore), [evidence-researcher](../.codex/agents/evidence-researcher.toml) e [planning-reviewer](../.codex/agents/planning-reviewer.toml).

Dos nove destinos do manifesto, CLAUDE.md foi adiado por não haver adoção Claude; architecture.md e design.md foram adiados por não haver aplicação, stack ou design aprovados. Estado técnico atual está descrito neste setup e no README; o contexto funcional permanece nas fontes originais. Workflow é um documento adicional para processo e retomada. Não foram criadas skills locais que duplicassem capacidades existentes.

## Linha de base SHA-256

Arquivos relativos a `docs/engenharia-reversa/`. Hashes conferidos antes da escrita contra o diagnóstico anterior:

| Arquivo | SHA-256 |
|---|---|
| fluxo-1-colaboradores.md | 27670990D8591C3B10BB77BEA0B103B9991DE0A06ACE6DBE6552C89993022C50 |
| fluxo-2-escalas.md | 75A808FC39FB24801522E30CFC2E8997306D220F4EE09E10B1E094B93F1DF9E0 |
| fluxo-3-visao-diaria.md | 58E323625FB2B2217F6771F8C590BD89F6A700F6E2A8B6348E93EF4E1E57FFD0 |
| sintese-funcional.md | F69ED5BB0A24DE2400CB114DC7C0894182B8EB5C6F59B1508AA615A2F1C793A4 |

## Verificações e limites

- Pré-escrita: raiz Git, branch e origin conferidos com sucesso; quatro hashes iguais ao diagnóstico.
- Teste de escrita: criado arquivo temporário exclusivo na raiz e removido imediatamente; sucesso.
- A ferramenta de patch recusou a gravação inicial do README. Nenhum arquivo foi criado por ela; a escrita local pelo PowerShell funcionou sem alterar ACLs.
- Validações finais: realizadas; resultados detalhados abaixo.
- Aplicação: lint, tipos, build e testes indisponíveis, sem execução ou instalação.
- Codex: arquivos configurados não comprovam descoberta, carregamento de AGENTS.md ou execução dos agentes na nova sessão.

## Próximo passo e manutenção

O teste de [onboarding](onboarding.md), pendente ao final da instalação, foi concluído e aprovado em 15/10/2026, conforme o registro abaixo. Não é necessário repeti-lo para concluir este setup. Em futuras retomadas, confira o estado persistente antes de considerar nova execução; não é necessário instalar plugins ou dependências.

Antes de repetir o setup, inspecione o estado e incorpore mudanças aos documentos existentes, sem duplicar seções/agentes. Atualize fontes e evidências quando necessário. Não reinstale componentes para provar repetibilidade. Os arquivos foram criados apenas quando ausentes nesta execução.

Sugestão de três ciclos posteriores, sem execução automática: fidelidade documental, configuração/Git e retomada/descoberta. Prompt de continuação:

```text
Execute três ciclos de revisão deste setup: (1) fidelidade às fontes e D01–D20
abertas; (2) TOMLs, links, hashes e escopo Git; (3) retomada e descoberta dos
agentes, somente quando possível em nova sessão. Não modifique as quatro fontes,
não instale ferramentas, não crie commits e não faça push. Use Git com a opção
safe.directory temporária definida em AGENTS.md. Registre achados com evidências
e limites; antes de editar novos documentos, apresente correções propostas.
```

## Resultado da validação local na instalação

- Quatro hashes SHA-256 iguais à linha de base; fontes preservadas byte a byte.
- Dez arquivos previstos presentes e UTF-8 legíveis.
- Dois TOMLs aceitos por `tomllib` do Python 3.11.3. Exatamente os três campos esperados, strings não vazias e nomes iguais aos arquivos; sem overrides de modelo/provedor/permissões.
- 48 referências Markdown locais resolvidas, incluindo as fontes originais. Não há links locais com âncora nesses documentos; links externos não foram retestados nesta retomada.
- Vinte IDs D01–D20 encontrados na ordem esperada na síntese, cujo hash é idêntico ao original.
- Whitespace dos dez arquivos novos inspecionado diretamente; nenhuma linha com espaço final e todos terminam com newline. `git diff --check` sem erros, lembrando que os arquivos ainda não são rastreados.
- `git check-ignore` confirmou que README, AGENTS, síntese, exemplo em `.agents/skills/` e agente em `.codex/agents/` não são ignorados.
- Estado Git: dez arquivos novos e quatro documentos originais não rastreados; nenhum commit ou push. Raiz e origin confirmados. Não houve staging.
- Arquivo de teste de escrita removido; nenhum recurso temporário mantido.
- Descoberta de AGENTS.md e dos agentes personalizados em nova sessão: pendente. Não foi iniciada outra sessão nem executado agente genérico como substituto.

## Conclusão do teste multiagente e retomada — 15/10/2026

**Resultado: APROVADO.** Registro baseado nas chamadas e respostas reais da sessão Codex, conferidas pelo coordenador e confirmadas pelo usuário ao autorizar a conclusão do setup. As seções de instalação acima preservam o estado histórico anterior; suas menções a execução pendente não representam o resultado atual.

- Ambos os papéis personalizados foram descobertos na interface de delegação do Codex e executados, sem substituição por agentes genéricos.
- `evidence-researcher`, tarefa `/root/pesquisa_d03_d04`: leu os quatro documentos de engenharia reversa e investigou bases, fontes, classificações, ambiguidades e lacunas de D03/D04.
- `planning-reviewer`, tarefa `/root/revisao_d03_d04`: revisou independentemente o resultado resumido encaminhado contra os documentos locais, buscando referências incorretas, extrapolações e requisitos inventados.
- Ambos concluíram em leitura, sem subdelegação, alterações, instalações, Git ou consultas à aplicação/serviços externos. Não foram solicitados overrides de modelo, provedor, autenticação ou permissões.
- O coordenador conferiu as fontes e os quatro hashes antes/depois: todos iguais à linha de base. D03 e D04 permanecem abertas, assim como D01–D20; nenhum comportamento ou número do PontoCorp foi aprovado como regra do Gestão Escala.

### Resultado documental e revisão

D03: o eixo de 24 horas é **OBSERVADO**; continuidade entre datas e contagem sem duplicação são **NÃO VERIFICADAS**. D04: meta diária 3 e contagem de oferta são **OBSERVADAS**; confronto entre demanda e oferta é **NÃO VERIFICADO**. As relações com outras decisões são interpretações, não requisitos ou sequência obrigatória.

O revisor não encontrou achados materiais. Apontou uma melhoria de rastreabilidade de severidade baixa: para meta gerar/limitar/validar jornadas e suficiência da cobertura, citar respectivamente as linhas 19 e 26 da síntese, em vez da referência ampla iniciada na linha 17. A consolidação na conversa incorporou a precisão; nenhuma fonte original foi editada.

### Limitações conhecidas

- A investigação e a revisão foram documentais; não revalidaram a aplicação nem os artefatos históricos REA.
- O revisor recebeu um resumo do resultado do pesquisador e conferiu as fontes locais.
- Codificação incorreta na leitura inicial e truncamento de saídas extensas foram resolvidos com UTF-8 explícito e leituras menores.
- Somente leitura é uma instrução de comportamento, não comprovação de sandbox independente.
- O teste comprova descoberta e execução na sessão utilizada; não garante disponibilidade em todo cliente ou sessão futura.

### Integridade após o desligamento

A verificação posterior confirmou os dez arquivos do toolkit presentes e legíveis, os dois TOMLs válidos e os quatro SHA-256 iguais à linha de base e aos registros do teste. O inventário continha apenas os 14 arquivos esperados fora de Git, sem temporários ou locks encontrados. Branch `main` e origin `https://github.com/pcdatasolution/gestao-escala` foram confirmados; naquele momento os 14 arquivos ainda não eram rastreados e não havia commits.

O procedimento permanece em [onboarding](onboarding.md). A conclusão atual autoriza o primeiro commit e sua publicação; o hash do commit e o resultado efetivo do push serão informados no relatório de execução, sem antecipar sucesso neste registro.
