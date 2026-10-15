# Qualidade e verificações

## Checks disponíveis

Não há lint, typecheck, build ou testes de aplicação. Os checks atuais verificam documentação e configuração, sem comprovar comportamento de produto implementado.

| Check | O que comprova |
|---|---|
| SHA-256 dos quatro originais | Preservação byte a byte contra setup |
| Parser TOML | Sintaxe, não descoberta pelo Codex |
| Campos dos agentes | name, description e developer_instructions, sem overrides de modelo/provedor/permissões |
| Links Markdown locais | Existência de arquivos e âncoras, quando verificadas |
| Git status/diff/check-ignore | Escopo, whitespace e ausência de ignores indevidos |
| Nova sessão e uso dos agentes | Descoberta e execução no cliente testado |

## Comandos de leitura

```powershell
Get-FileHash docs/engenharia-reversa/*.md -Algorithm SHA256
git -c safe.directory=C:/Users/Pedro/repos/saas-factory/gestao-escala status --short
git -c safe.directory=C:/Users/Pedro/repos/saas-factory/gestao-escala diff --check
git -c safe.directory=C:/Users/Pedro/repos/saas-factory/gestao-escala ls-files --others --exclude-standard
```

Antes do primeiro commit, diff não cobre arquivos não rastreados. Inspecione-os diretamente; não adicione ao índice apenas para validar.

Com Python 3.11+ disponível:

```powershell
py -3 -c "import pathlib,tomllib; paths=list(pathlib.Path('.codex/agents').glob('*.toml')); assert len(paths)==2; [tomllib.loads(p.read_text(encoding='utf-8')) for p in paths]; print('TOML_OK')"
```

Neste executor o launcher não localiza runtime; o executável 3.11.3 existente pode substituir `py -3`, conforme setup. Não instale runtime nem pacotes automaticamente. Se não houver parser, registre a validação bloqueada.

## Revisão documental

Confira OBSERVADO/INFERIDO/NÃO VERIFICADO, referências e D01–D20 abertas. Não transforme números da referência em regras aprovadas nem lacunas em ausência de capacidade no PontoCorp.

O [workflow](workflow.md) define revisão separada e ciclos sugeridos; [onboarding](onboarding.md) contém o teste real. Instrução de leitura não é isolamento técnico de permissões.

## Qualidade operacional V1

Defina verificações a partir do aceite e do comportamento alterado. Para documentação, confira links afetados, classificação das fontes, escopo Git, UTF-8, formatação e whitespace. Arquivos novos exigem leitura direta, pois `git diff --check` não cobre não rastreados; após staging autorizado, confira também `git diff --cached --check`. Integridade dos quatro originais é aferida contra os hashes do setup.

Quando houver aplicação e stack aprovadas, selecione testes proporcionais: unidade para lógica isolada, integração para fronteiras e fluxo de interface quando necessário ao comportamento. Uma correção deve demonstrar a regressão quando pertinente. Não crie testes que apenas reproduzam a implementação ou comprovem alterações textuais triviais. Registre comandos, resultados, versão examinada e verificações indisponíveis; nenhum check documental comprova comportamento de aplicação.

A revisão independente segue o workflow: artefato identificável, achados fundamentados e limites explícitos. Correções recebem nova verificação e revisão direcionadas ao impacto, sem repetir suites sem motivo. Resultado verde anterior não comprova conteúdo posterior. Pendência essencial não pode ser declarada aprovada; o limite de correções encerra tentativas, não substitui aceite.

## Aceite deste setup

O Vibe Coding Toolkit foi instalado e validado: dez arquivos previstos presentes, links locais resolvidos, TOMLs aceitos por parser sem overrides de modelo/provedor/permissões e quatro hashes originais idênticos. Git na raiz/origin corretos com exceção temporária, sem alteração de configuração global nem instalação de dependências de aplicação. O versionamento posterior está registrado em [setup](setup.md).

Os agentes `evidence-researcher` e `planning-reviewer` foram testados com delegação real no teste D03/D04, aprovado. A auditoria de fundação R01/R02/R03 foi concluída com parecer de aprovação com ressalvas; resultados e limites estão em setup.

A governança operacional V1 está consolidada no workflow, com evidências do P01 e T7. D01–D20 permanecem abertas; criar um índice de rastreabilidade ou iniciar implementação não está autorizado. Registros anteriores em PRODUCT e setup descrevem a etapa histórica anterior; não constituem impedimento à consolidação documental explicitamente autorizada.
