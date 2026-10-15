# Fluxo 1 — Colaboradores

Referência: PontoCorp. Projeto: Gestão Escala.

## Base e limites da consolidação

- **OBSERVADO — fonte consolidada pelo usuário:** este documento registra exclusivamente a consolidação fornecida para completar a documentação da Fase 1, incluindo os experimentos posteriores de cadastro realizados durante o Fluxo 3.
- **NÃO VERIFICADO:** comportamentos não descritos nessa fonte não são recuperados por suposição. Não houve nova investigação, uso do REA ou navegação para produzir este arquivo.
- **OBSERVADO:** os indicadores iniciais correspondem à base vazia; a criação posterior de dois colaboradores de teste é outro estado da investigação. Não são contagens simultâneas.

Convenção: **OBSERVADO** = conteúdo ou comportamento documentado na fonte, com relatos identificados; **INFERIDO** = interpretação; **NÃO VERIFICADO** = comportamento não demonstrado. Rótulos e descrições de ações não comprovam sua execução. Nenhum CPF ou dado pessoal é reproduzido.

## 1. Objetivo e identificação da tela

- **OBSERVADO:** URL `/rh/employees`, título “Diretório de Colaboradores”.
- **OBSERVADO:** há indicadores, busca, categorias, filtros organizacionais e entradas de cadastro, convite e importação.
- **INFERIDO:** a tela centraliza a consulta e a entrada de colaboradores e seus vínculos organizacionais e de jornada.
- **NÃO VERIFICADO:** ciclo completo de administração dos registros, permissões e regras de acesso.

## 2. Diretório de Colaboradores

### Indicadores e consulta

**OBSERVADO:** no estado inicial:

| Indicador | Valor |
|---|---:|
| Total | 0 |
| Ativos | 0 |
| Em atividade hoje | 0 |
| Admissões recentes | 0 |
| Licenças em uso / capacidade | 0 / 50 |

- **OBSERVADO:** a busca indica nome, e-mail e matrícula.
- **OBSERVADO:** categorias Todos, Ativos, Em Férias e Inativos; filtros por departamento e filial.
- **INFERIDO:** departamento e filial são dimensões de organização do diretório.
- **NÃO VERIFICADO:** resultado de buscas, combinação dos filtros, origem das opções de departamento e regras de cálculo dos indicadores. A consolidação fornecida não detalha tabela/colunas nem apresentação do estado vazio além dos contadores iniciais.

### Ações e formas de entrada

| Entrada — OBSERVADO | O que foi documentado | Limite |
|---|---|---|
| Novo Colaborador / +Adicionar | Entradas para cadastro individual | Cadastro explorado; regras mínimas completas não demonstradas |
| Convidar | WhatsApp ou link | **NÃO VERIFICADO:** envio, aceite e resultado do convite |
| Importar | CSV | **NÃO VERIFICADO:** formato, processamento e validações |
| Cartaz QR | Relacionado a ponto | **NÃO VERIFICADO:** geração e utilização |
| Licenças extras | Ação disponível | **NÃO VERIFICADO:** contratação e efeito sobre capacidade |

**NÃO VERIFICADO:** a presença dessas entradas não comprova que convite ou importação produzam o mesmo cadastro e os mesmos vínculos do formulário individual.

## 3. Cadastro individual

**OBSERVADO:** os campos e opções abaixo constam na fonte. Os tipos indicados como aparentes são **INFERIDOS** a partir de sua função e dos controles descritos; não representam uma auditoria de atributos HTML.

| Campo — OBSERVADO | Tipo aparente — INFERIDO | Obrigatoriedade evidenciada | Valores, opções e comportamento documentados |
|---|---|---|---|
| Nome | Texto | **NÃO VERIFICADO:** exigência no envio isoladamente | Preencher somente Nome habilitou Criar Colaborador no teste posterior |
| E-mail | Entrada de e-mail | **NÃO VERIFICADO** | Sem valores ou validações documentados na fonte |
| Departamento | Texto | **NÃO VERIFICADO** | Opções e regras de padronização não documentadas |
| CPF* | Identificador textual | **OBSERVADO:** asterisco e tentativa sem CPF não concluída | CPF válido aceito; reutilização rejeitada nos casos testados |
| Matrícula | Texto | **NÃO VERIFICADO** | Sem valores ou validações documentados na fonte |
| Data de Admissão | Data | **NÃO VERIFICADO** | Sem valor inicial documentado na fonte |
| Início da Apuração (Ponto) | Data | **OBSERVADO:** indicado como opcional | Sem valor inicial documentado nesta fonte |
| Data de Desligamento | Data | **OBSERVADO:** indicada como opcional | Sem valor inicial documentado na fonte |
| Cargo | Texto | **NÃO VERIFICADO** | Opções e regras não documentadas |
| Supervisor | Busca/seleção | **NÃO VERIFICADO** | Opção “Sem supervisor” observada |
| Horário de trabalho (Escala) | Seletor | **NÃO VERIFICADO** | “Sem escala” e “Comercial Padrão (Seg-Sex)”; reabertura após cancelamento voltou a Sem escala |
| Filial | Seletor | **NÃO VERIFICADO** | “Matriz (Sede Principal)” no estado investigado; não comprova obrigatoriedade nem disponibilidade em outras contas |
| Status | Seletor | **NÃO VERIFICADO** | Ativo, Férias e Inativo; o valor padrão não é explicitado na fonte fornecida |

- **OBSERVADO:** selecionar Comercial Padrão mudou o seletor sem abrir campos adicionais.
- **OBSERVADO:** Cancelar retornou ao diretório; reabrir sem salvar restaurou “Sem escala”.
- **INFERIDO:** ao menos a escolha experimental da escala não foi preservada nesse cancelamento/reabertura.
- **NÃO VERIFICADO:** descarte geral de outros campos, salvamento automático, mensagens condicionais e estrutura de etapas/seções não detalhada pela fonte.

## 4. Relacionamentos

| Relação | Classificação e limite |
|---|---|
| Colaborador ↔ escala | **OBSERVADO:** seletor com escala disponível e opção Sem escala. A aplicação diária foi posteriormente sustentada no [Fluxo 3](fluxo-3-visao-diaria.md) |
| Colaborador ↔ filial | **OBSERVADO:** campo Filial com Matriz. **NÃO VERIFICADO:** cardinalidade, transferências e outras unidades |
| Colaborador ↔ supervisor | **OBSERVADO:** campo e opção Sem supervisor. **NÃO VERIFICADO:** elegibilidade e hierarquia |
| Colaborador ↔ departamento | **OBSERVADO:** campo de cadastro e filtro do diretório. **INFERIDO:** dimensão de classificação |
| Colaborador ↔ cargo | **OBSERVADO:** campo de cadastro. **NÃO VERIFICADO:** vínculo com funções necessárias à cobertura |
| Colaborador ↔ status | **OBSERVADO:** Ativo, Férias e Inativo. **NÃO VERIFICADO:** consequências e transições de cada estado |

**INFERIDO:** departamento, cargo, supervisor e horário de trabalho parecem atributos ou relacionamentos paralelos do colaborador, não uma cadeia hierárquica sequencial entre si.

## 5. Regras e experimentos posteriores

**OBSERVADO — experimento posterior relatado pelo usuário, durante o Fluxo 3:**

| Teste | Resultado documentado |
|---|---|
| Preencher somente Nome | Botão Criar Colaborador habilitado |
| Tentar enviar sem CPF | Cadastro não concluído |
| Usar CPF válido | Primeiro colaborador criado |
| Reutilizar o mesmo CPF para outra pessoa | Rejeitado |
| Usar outro CPF | Segundo colaborador criado |

- **OBSERVADO:** habilitação do botão e aceitação do envio são comportamentos distintos no experimento.
- **INFERIDO:** há uma exigência de CPF no cenário testado e uma restrição contra sua reutilização entre os dois colaboradores.
- **NÃO VERIFICADO:** conjunto mínimo completo de campos no envio; se a validação é apenas estrutural ou externa; alcance da unicidade fora desses registros/empresa; tratamento de registros inativos e concorrência. A implementação não foi investigada.
- **NÃO VERIFICADO:** unicidade de e-mail/matrícula, validações de datas, nomes ou vínculos. Nenhum dado identificador dos testes é necessário a esta consolidação.

## 6. Modelo funcional inferido

```text
Empresa
  └─ [INFERIDO] organiza colaboradores por filial
       └─ Colaborador
            ├─ [OBSERVADO] campo Filial
            ├─ [OBSERVADO] campos Departamento / Cargo / Supervisor
            ├─ [OBSERVADO] seletor Status
            └─ [OBSERVADO] seletor Horário de trabalho (Escala)
                 └─ [INFERIDO, sustentado no Fluxo 3] jornada prevista por data
```

**NÃO VERIFICADO:** hierarquia real de equipes, permissões, múltiplos vínculos e vigência/histórico das alterações.

## 7. Principais descobertas

- **OBSERVADO:** o diretório reúne consulta por identidade, situação e dimensões organizacionais, além de várias entradas de colaboradores.
- **OBSERVADO:** o cadastro oferece vínculo com escala, filial e supervisor, além de departamento, cargo e dados administrativos.
- **OBSERVADO:** selecionar uma escala não revelou horários próprios adicionais no formulário; cancelar e reabrir restaurou Sem escala.
- **OBSERVADO — relato posterior:** CPF interferiu na conclusão do cadastro e sua repetição foi rejeitada; somente Nome habilitar o botão não bastou para comprovar criação.

## 8. Relevância para o MVP Gestão Escala

**INFERIDO — avaliação de produto, não especificação funcional:**

| Conceito | Relevância |
|---|---|
| Identidade básica e ativo/inativo | Relevantes para identificar pessoas elegíveis ao planejamento |
| Pessoa ↔ escala/padrão | Relevante à geração de jornadas, sem substituir atribuições pontuais |
| Unidade/filial | Pode delimitar a operação planejada |
| Departamento, cargo e supervisor | Podem apoiar organização e responsabilidade; prioridade depende da operação |
| CPF, apuração de ponto, licenças e QR | Não são requisitos automáticos do MVP por existirem na referência |

**INFERIDO:** o escopo do MVP permanece calendário semanal, pessoas × dias × horários, atribuição de turnos, folgas/indisponibilidades, reorganização, conflitos, horários descobertos e operação 24h para farmácia. Esta comparação não altera esse escopo nem propõe reproduzir o cadastro administrativo do PontoCorp.

## 9. Lacunas ainda existentes

**NÃO VERIFICADO:**

- Conjunto mínimo completo de cadastro e validações além dos casos relatados.
- Funcionamento real de busca, filtros e transições de status.
- Relações de supervisor/equipe e significado operacional de cargo/departamento.
- Vínculos por unidade, múltiplas escalas e histórico/vigência.
- Efeito de inatividade, férias e indisponibilidades sobre atribuições.
- Importação, convite e demais entradas administrativas.
- Descarte/persistência de todos os campos ao cancelar, além da escala testada.

## 10. Conclusão do fluxo

**Fluxo 1 — Colaboradores suficientemente compreendido para avançar: SIM.**

**INFERIDO — parecer:** identidade, situação e vínculos do cadastro estão suficientemente delimitados para avançar ao estudo das jornadas, preservando as lacunas. Isso não equivale à validação completa do cadastro. O objeto seguinte é [RH → Escalas, Fluxo 2](fluxo-2-escalas.md); o experimento diário posterior consta no [Fluxo 3](fluxo-3-visao-diaria.md).
