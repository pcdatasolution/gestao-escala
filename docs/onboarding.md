# Preparação local

## Estado atual

O projeto contém documentação e configuração de agentes. Não instale dependências para abrir os arquivos. Não existem servidor de desenvolvimento, banco, variáveis de ambiente ou testes de aplicação.

Use editor Markdown, Git e cliente Codex com suporte a agentes personalizados. Python 3.11+ com `tomllib` é opção de validação TOML, não dependência do produto.

## Abrir e conferir

Abra o Codex na raiz `C:\Users\Pedro\repos\saas-factory\gestao-escala`. Leia [AGENTS.md](../AGENTS.md), [PRODUCT.md](../PRODUCT.md) e a [síntese](engenharia-reversa/sintese-funcional.md).

No executor com identidade diferente do proprietário:

```powershell
git -c safe.directory=C:/Users/Pedro/repos/saas-factory/gestao-escala rev-parse --show-toplevel
git -c safe.directory=C:/Users/Pedro/repos/saas-factory/gestao-escala status --short
git -c safe.directory=C:/Users/Pedro/repos/saas-factory/gestao-escala remote -v
```

Não persista a exceção. Espere a raiz acima e origin `https://github.com/pcdatasolution/gestao-escala`.

## Testar os agentes em nova sessão

Abra uma nova conversa do Codex na raiz. Solicite confirmação das instruções carregadas e descoberta dos agentes personalizados. Se não forem descobertos, registre cliente/versão e diagnóstico; não substitua silenciosamente por agentes genéricos.

```text
Leia AGENTS.md e confirme as instruções carregadas.
Use o agente personalizado evidence-researcher para localizar as bases e
limites de D03 e D04 nos quatro documentos de docs/engenharia-reversa/.
Retorne caminhos, seções e classificações sem responder às decisões.
Depois use planning-reviewer para revisar o resultado contra as fontes,
buscando requisitos inventados, referências incorretas e extrapolações.
Ambos trabalham somente em leitura, sem subdelegação, preservando modelo,
provedor e permissões. Aguarde ambos e confira as evidências.
Não crie arquivos ou commits, nem faça chamadas a serviços externos.
Informe os agentes efetivamente executados e limitações observadas.
```

Aceite: ambos realmente acionados, D03/D04 abertas, fontes conferidas pelo coordenador e hashes originais iguais antes/depois. Arquivos TOML válidos não comprovam descoberta ou execução.

## Retomada e dificuldades conhecidas

Consulte [setup](setup.md), [workflow](workflow.md) e [quality](quality.md). Não instale plugins ou MCPs. A descoberta pode depender da confiança do cliente no projeto; preserve políticas e reporte bloqueios.

O launcher `py -3` não encontrou Python no executor e o shim `python` não tem versão selecionada. Há Python 3.11.3 instalado via pyenv; use seu executável existente diretamente para validar, sem alterar configuração global/local. O caminho de máquina está registrado em setup. `npm.ps1` é bloqueado por política; `npm.cmd` funciona, mas não é necessário neste estágio.
