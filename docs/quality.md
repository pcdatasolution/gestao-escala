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

## Aceite deste setup

Dez arquivos previstos presentes, links locais resolvidos e TOMLs aceitos por parser, sem overrides de modelo/provedor/permissões. Quatro hashes originais idênticos. Git na raiz/origin corretos com exceção temporária. Sem configuração global, dependência, commit ou push. Descoberta e execução dos agentes ficam pendentes até evidência de nova sessão.
