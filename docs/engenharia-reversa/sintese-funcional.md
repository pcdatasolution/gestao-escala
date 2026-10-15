# Síntese funcional transversal — Engenharia reversa

Projeto: Gestão Escala. Referência investigada: PontoCorp.

Fontes lidas integralmente: [Fluxo 1 — Colaboradores](fluxo-1-colaboradores.md), [Fluxo 2 — Escalas](fluxo-2-escalas.md) e [Fluxo 3 — Visão Diária](fluxo-3-visao-diaria.md).

Este documento conecta as evidências às decisões de produto anteriores à especificação. Não é a especificação final do MVP, um modelo de banco de dados ou uma confirmação de capacidades não testadas. Nenhuma nova investigação foi realizada e os três documentos de origem foram preservados.

Convenção: **OBSERVADO** = conteúdo ou comportamento documentado nas fontes; **INFERIDO** = interpretação dessas evidências; **NÃO VERIFICADO** = comportamento não demonstrado. Uma lacuna não significa inexistência no PontoCorp. As classificações de comparação e as perguntas de produto são avaliações, não descobertas sobre a aplicação.

## 1. Modelo funcional descoberto

A sequência solicitada é uma forma de organizar o domínio; as evidências não demonstram que todos os seus elos formem um fluxo automático.

| Relação | Classificação | Sustentação e limite |
|---|---|---|
| Empresa/operação → horário de funcionamento | **OBSERVADO** | O editor apresenta “Horário de Funcionamento da Empresa”, dias e abertura/fechamento. O estado era 07:00–22:00 de segunda a domingo. Escopo específico por unidade **NÃO VERIFICADO**. F2, seção 3 |
| Horário de funcionamento → necessidade/meta | **OBSERVADO** quanto à apresentação conjunta | A mesma área apresenta meta 3 por dia e controles diários. Sua interpretação como necessidade simultânea por faixa horária é **NÃO VERIFICADA**. F2, seção 3 |
| Necessidade/meta → escala/padrão recorrente | **NÃO VERIFICADO** | Não foi demonstrado que a meta gere, limite ou valide a configuração de jornadas. A existência dos dois controles não estabelece dependência automática. F2, seções 3 e 7 |
| Escala/padrão → colaborador | **OBSERVADO** | Campo de escala no cadastro; seleção e salvamento do vínculo do Teste 01. Vinculação pela ação da lista de escalas não foi executada. F1, seções 3–4; F3, seção 4 |
| Colaborador vinculado + padrão + data → jornada prevista | **INFERIDO**, sustentado por experimento | Após o vínculo, Teste 01 apareceu 08:00–18:00 em quarta/sexta e em folga no sábado; Teste 02 permaneceu sem escala. O resultado nas datas é **OBSERVADO**; a generalização para outros modelos não foi demonstrada. F3, seção 4 |
| Padrão + data → folga | **OBSERVADO** no cenário semanal | Sábado 17/10 apresentou “Folga da Escala” para Teste 01, coerente com o sábado de folga do padrão. Regra geral para exceções e outros ciclos **NÃO VERIFICADA**. F3, seções 3–4 |
| Ausência/indisponibilidade registrada → jornada da data | **NÃO VERIFICADO** | Férias/atestados apareceram como categoria/indicador, mas nenhum caso positivo foi testado. F3, seções 2–3 |
| Jornada/folga da data → visualização diária | **OBSERVADO** | Timeline para jornada; cartões para pessoas sem jornada. Categorias filtraram as seções. F3, seções 2–3 |
| Jornadas na visualização → oferta de pessoas por horário | **OBSERVADO** no cenário testado | Uma pessoa gerou contagem 1 entre 08:00 e 18:00 e 0 fora. Agregação de várias pessoas e pausas explícitas **NÃO VERIFICADA**. F3, seções 4–5 |
| Oferta horária + necessidade → cobertura suficiente/insuficiente | **NÃO VERIFICADO** | Não houve comparação com meta, função ou janela de operação. Faixa com zero pessoas não comprova déficit sem demanda definida. F3, seção 5 |

**INFERIDO:** há três camadas conceitualmente úteis: configuração da operação, definição recorrente de jornadas e consulta diária da oferta. A integração completa entre necessidade operacional e oferta permaneceu **NÃO VERIFICADA**.

## 2. Objetos do domínio identificados

Os termos abaixo são conceitos funcionais. Sua separação em entidades, atributos, cálculos ou estados derivados será uma decisão posterior de modelagem.

| Conceito | Evidência e significado delimitado |
|---|---|
| Empresa/operação | **OBSERVADO:** contexto organizacional e título do horário de funcionamento; delimitação exata de escopo **NÃO VERIFICADA** |
| Unidade/filial | **OBSERVADO:** campo no colaborador, opção Matriz e filtro no diretório; relação com demanda e escala **NÃO VERIFICADA** |
| Colaborador | **OBSERVADO:** cadastro, identidade e vínculo com escala; duas pessoas de teste permitiram comparar estados |
| Status cadastral | **OBSERVADO:** Ativo, Férias e Inativo no seletor; consequências completas **NÃO VERIFICADAS** |
| Cargo, departamento e supervisor | **OBSERVADO:** campos organizacionais; hierarquia e papel no dimensionamento **NÃO VERIFICADOS** |
| Escala/padrão recorrente | **OBSERVADO:** parâmetros semanais/cíclicos e vínculo com pessoa; **INFERIDO:** modelo reutilizável de jornada |
| Modelo rápido | **OBSERVADO:** opções de configuração e mudança automática de parâmetros no Plantão; não equivale a um registro salvo |
| Data consultada | **OBSERVADO:** recorte diário que alterou a situação apresentada do mesmo colaborador |
| Jornada prevista | **OBSERVADO:** barra 08:00–18:00 para pessoa/data; geração recorrente **INFERIDA** pelo experimento |
| Dia de trabalho | **OBSERVADO:** marcação no padrão e presença na timeline nos dias úteis testados |
| Folga | **OBSERVADO:** sábado de folga no padrão e “Folga da Escala” no resultado; rótulo “Folga DSR” também foi aplicado a pessoas sem escala |
| Ausência/indisponibilidade | **OBSERVADO** apenas como campos/categorias relacionados a férias e atestados; registro e aplicação por data **NÃO VERIFICADOS** |
| Intervalo | **OBSERVADO:** duração ou início/retorno no editor; desconto na oferta horária **NÃO VERIFICADO** para pausa explícita |
| Ciclo | **OBSERVADO:** Plantão experimental com D1 trabalho/D2 folga e projeção; aplicação nominal diária **NÃO VERIFICADA** |
| Horário de funcionamento | **OBSERVADO:** abertura/fechamento por dia, separado dos horários da pessoa |
| Meta de cobertura | **OBSERVADO:** valor diário na configuração; significado temporal e utilização no planejamento **NÃO VERIFICADOS** |
| Disponibilidade/oferta horária | **OBSERVADO:** contagem prevista por hora na timeline; não comprova presença real nem capacidade por função |
| Turno | **OBSERVADO:** termo usado pelo produto; **NÃO VERIFICADO:** objeto independente atribuído a uma pessoa. O termo não define por si só o turno do Gestão Escala |
| Política/CCT, tolerância e banco de horas | **OBSERVADO:** parâmetros, rótulos e avaliações; efeitos e validade dos cálculos **NÃO VERIFICADOS** |

**INFERIDO:** status cadastral, ausência de escala, folga prevista e indisponibilidade são conceitos que precisam ser distinguidos no raciocínio de produto. A referência agrupou motivos diferentes em “Folga DSR”; isso não torna os motivos equivalentes.

## 3. Fluxo funcional entre os três módulos

**OBSERVADO — configuração:** Colaboradores permite selecionar uma escala. Escalas apresenta padrões com dias, horários, intervalo e vínculos. A lista também oferece Vincular, mas o caminho efetivamente testado foi o campo no cadastro da pessoa.

**OBSERVADO — experimento documentado:**

1. Os dois colaboradores sem escala apareceram sem jornada em 14/10/2026, na seção de folgas/ausências.
2. Somente Teste 01 recebeu Comercial Padrão (Seg-Sex), por edição do cadastro e Salvar Alterações.
3. Visão Diária de 14/10 passou a mostrar Teste 01 em 08:00–18:00; Teste 02 continuou sem escala.
4. Em 16/10, Teste 01 continuou em jornada; em 17/10, apareceu como Folga da Escala.
5. Em Turno e Folgas & Ausências separaram as seções em 16/10, mantendo os indicadores gerais.

**INFERIDO:** o caminho funcional demonstrado é configuração recorrente → vínculo da pessoa → resultado previsto por data. Isso não demonstra uma alocação manual independente para cada dia.

| Configuração recorrente — OBSERVADO | Resultado diário — OBSERVADO | Limite |
|---|---|---|
| Comercial, seg–sex; 08:00–18:00; pausa 60 min | Jornada do Teste 01 em quarta/sexta | **NÃO VERIFICADO:** todas as datas e modelos |
| Sábado/domingo de folga no padrão | Sábado com Folga da Escala | Domingo não foi observado operacionalmente |
| Escala ausente no Teste 02 | Sem jornada; Sem escala vinculada / Folga DSR | Não comprova folga formal ou indisponibilidade |
| Plantão experimental no editor | Projeção individual de ciclo de 2 dias | Não houve aplicação nominal salva do ciclo |

**OBSERVADO:** a alteração experimental do padrão para Plantão não foi salva; o editor posterior voltou aos parâmetros originais. **INFERIDO:** consistente com descarte. Não deve ser confundida com o vínculo do Teste 01, que foi salvo e seguido de resultado diário observado.

**OBSERVADO:** nove horas líquidas foram apresentadas no editor Comercial, mas a oferta diária permaneceu contínua por dez faixas de uma hora. **NÃO VERIFICADO:** se a diferença decorre do modo de intervalo, da visualização ou de outra regra.

## 4. O que o PontoCorp demonstrou

| Capacidade | Evidência e alcance |
|---|---|
| Cadastro de pessoas de teste | **OBSERVADO — relatos documentados:** dois cadastros concluídos, CPF repetido rejeitado. Não determina requisitos do nosso produto |
| Estrutura organizacional no cadastro | **OBSERVADO:** campos filial, cargo, departamento e supervisor; não prova funcionamento integral de cada relação |
| Seleção de escala no colaborador | **OBSERVADO:** seleção sem novos campos e vínculo salvo no Teste 01 |
| Configuração operacional diária | **OBSERVADO:** sete dias com abertura, fechamento e meta; controles apresentados, sem teste de validação de cobertura |
| Parâmetros semanais e de ciclo | **OBSERVADO:** Comercial semanal e Plantão experimental de dois dias |
| Aplicação de modelo no editor | **OBSERVADO:** selecionar Plantão mudou nome, horários, modo e projeção |
| Dois modos de intervalo | **OBSERVADO:** por duração e por horário, incluindo 12:00–13:00 no experimento |
| Personalização por dia | **OBSERVADO:** ativação revelou cartões e controles; efeitos de horários diferentes não foram testados |
| Projeção individual de 30 dias | **OBSERVADO:** trabalho/folga e carga projetada para um colaborador modelo |
| Jornada e folga por data | **OBSERVADO:** resultados do Teste 01 em dias úteis e sábado; relação causal generalizada é **INFERIDA** no limite do experimento |
| Timeline nominal de um dia | **OBSERVADO:** pessoa × horas, barra 08:00–18:00 e eixo de 24 horas |
| Oferta por faixa horária | **OBSERVADO:** contagem 0/1 com uma pessoa em jornada |
| Filtros de situação diária | **OBSERVADO:** Em Turno e Folgas & Ausências filtraram resultados sem alterar indicadores gerais |
| Consulta por datas | **OBSERVADO:** navegação manual entre as datas investigadas |
| Rótulos e resultados de compliance | **OBSERVADO:** painel e valores; bloqueios e conformidade efetivos não demonstrados |

**OBSERVADO:** controles para convite, CSV, QR, licenças, busca e exclusão foram encontrados. **NÃO VERIFICADO:** sua execução. Não entram nesta síntese como funcionalidades operacionalmente comprovadas.

**OBSERVADO — divergências preservadas:** Comercial (40h) versus projeção 45h; modelo rápido 08:00–17:00 versus registro 08:00–18:00; tolerância configurada 10 versus ajuda mencionando 15. **NÃO VERIFICADO:** causas e correção. Não fundamentam regras próprias do Gestão Escala.

## 5. O que o PontoCorp não demonstrou

Todos os itens desta seção são **NÃO VERIFICADOS**. Isso não significa inexistência na referência.

| Lacuna relevante ao MVP | Limite da evidência disponível |
|---|---|
| Calendário semanal pessoas × dias × horários | Foi observada uma data por vez, não vários dias editáveis em uma grade |
| Atribuição manual de turnos | Vincular padrão não demonstrou alocar um turno específico por pessoa/data |
| Edição pontual | Nenhuma exceção individual foi criada; barra sem ação de clique conforme relato |
| Drag-and-drop/reorganização | Nenhum arraste ou movimentação foi testado |
| Indisponibilidade específica | Nenhum período parcial/integral de indisponibilidade foi aplicado |
| Substituições e trocas | Não houve transferência de jornada ou troca entre pessoas |
| Conflitos | Nenhum caso de sobreposição, indisponibilidade ou descanso insuficiente demonstrou detecção/resolução |
| Demanda mínima por horário | Meta por dia apareceu; sua decomposição por faixa não foi demonstrada |
| Déficit/excesso | Contagem de oferta não foi confrontada com demanda |
| Turnos/horários descobertos | Zero pessoas fora de 08:00–18:00 não foi identificado como déficit operacional |
| Cobertura por função/unidade | Campos organizacionais não demonstraram exigência ou contagem por qualificação |
| Operação 24h atravessando meia-noite | Eixo de 24 horas não demonstra continuidade, divisão ou contagem entre datas |
| Múltiplos turnos | Não houve jornadas independentes na mesma data nem múltiplas pessoas sobrepostas na timeline |
| Aplicação operacional de ciclos | Plantão 12x36 ficou no editor/projeção; vínculo nominal, início e defasagem não foram testados |
| Pausas na cobertura | A duração de 60 min não abriu lacuna na barra observada; pausa com horários explícitos não foi confrontada com oferta |
| Granularidade de minutos | Somente faixas horárias inteiras foram observadas operacionalmente |
| Vigência e propagação de mudanças | Não houve teste de impacto de alterar um padrão sobre jornadas já planejadas |
| Rascunho/publicação/cópia | Não foram demonstrados planejamento provisório, publicação ou cópia de dias/semanas |

## 6. PontoCorp × Gestão Escala

Escopo definido pelo usuário: calendário semanal, pessoas × dias × horários, atribuição de turnos, folgas/indisponibilidades, reorganização, conflitos, identificação de horários/turnos descobertos e operação 24h no cenário inicial de farmácia.

**INFERIDO — avaliação de produto:** a classificação abaixo indica como tratar a referência na discussão de produto. Não aprova funcionalidades adicionais nem encerra as decisões da seção 7.

| Conceito/capacidade | Classificação | Aplicação da referência e limite |
|---|---|---|
| Identidade e situação básica da pessoa | APROVEITAR COMO REFERÊNCIA | Identificar quem pode ser planejado; dados mínimos próprios ainda a decidir |
| Padrão separado do resultado por data | APROVEITAR COMO REFERÊNCIA | Distinção útil, sem impor recorrência obrigatória |
| Configuração de entrada, saída e intervalo | APROVEITAR COMO REFERÊNCIA | Vocabulário e separação dos parâmetros; regras próprias ainda abertas |
| Horário de funcionamento | ADAPTAR | Separar operação de jornada e contemplar continuidade 24h e escopo da farmácia |
| Meta diária de cobertura | ADAPTAR | O MVP precisa identificar descobertos; semântica temporal e por função requer decisão |
| Timeline e contagem de oferta | ADAPTAR | Usar como referência visual para calendário semanal e confronto com necessidade |
| Pessoa sem escala / Folga DSR | ADAPTAR | Decidir distinção entre sem alocação, folga e indisponibilidade, sem herdar equivalência |
| Personalização e ciclos | ADAPTAR | Decidir uso de recorrência, exceções e 12x36 sem presumir comportamento operacional validado |
| Filial/cargo/departamento/supervisor | ADAPTAR | Definir somente dimensões necessárias ao cenário inicial; não adotar hierarquia administrativa completa |
| Calendário semanal e unidade turno | PRECISAMOS DEFINIR POR CONTA PRÓPRIA | A referência não demonstrou a experiência de planejamento exigida |
| Atribuição, reorganização e substituição | PRECISAMOS DEFINIR POR CONTA PRÓPRIA | Definir operações e efeitos sobre pessoas/datas |
| Indisponibilidade e exceção pontual | PRECISAMOS DEFINIR POR CONTA PRÓPRIA | Definir estados e precedência sobre padrões |
| Conflitos, déficit e turnos descobertos | PRECISAMOS DEFINIR POR CONTA PRÓPRIA | Definir regras, severidade e correção |
| Virada de dia, múltiplos turnos e pausas na oferta | PRECISAMOS DEFINIR POR CONTA PRÓPRIA | Necessários à clareza da operação contínua; sem comportamento suficiente da referência |
| Rascunho/publicação | PRECISAMOS DEFINIR POR CONTA PRÓPRIA | Decidir se faz parte do MVP; não incluir por presunção |
| CPF, QR de ponto e licenças extras | NÃO NECESSÁRIO NO MVP | Não demonstraram necessidade para o núcleo operacional definido |
| Apuração de ponto, banco de horas e compliance CCT avançado | NÃO NECESSÁRIO NO MVP | Não ampliar o núcleo de planejamento por associação com a referência; conflitos operacionais permanecem no escopo |

## 7. Questões de produto que precisamos decidir

São **20 decisões abertas**, identificadas de D01 a D20. Nenhuma resposta está aprovada por esta síntese. As bases são evidências ou lacunas; as alternativas são possibilidades para deliberação, não capacidades atribuídas ao PontoCorp.

### D01 — Como o gestor começa a montar a semana?

**Base:** **INFERIDO:** a referência deriva jornadas de padrões vinculados; **NÃO VERIFICADO:** montagem semanal direta.

**Decisão:** o gestor atribui turnos diretamente no calendário, parte de padrões recorrentes ou combina os dois caminhos? Pessoas sem padrão podem ser planejadas? A resposta define o fluxo principal e a dependência da recorrência.

### D02 — O que é um turno e como ele se distingue de jornada e padrão?

**Base:** **OBSERVADO:** barra de jornada e padrões; **NÃO VERIFICADO:** turno independente atribuível.

**Decisão:** turno é uma faixa reutilizável, uma necessidade a preencher ou a atribuição de uma pessoa em uma data? Uma jornada pode conter vários turnos/segmentos? Definir o vocabulário e a unidade que o gestor cria, move e substitui.

### D03 — Como representar jornadas atravessando meia-noite?

**Base:** **OBSERVADO:** eixo 24h; **NÃO VERIFICADO:** virada de dia.

**Decisão:** como informar data/hora inicial e final, em qual dia a atribuição começa e como sua continuidade aparece no dia/semana seguinte? Como evitar duplicação na oferta e tratar sobreposição nos limites entre datas? A decisão deve cobrir o cenário de farmácia 24h.

### D04 — Como cadastrar demanda mínima e o que significa descoberto?

**Base:** **OBSERVADO:** meta diária 3 e contagem de oferta; **NÃO VERIFICADO:** confronto entre elas.

**Decisão:** demanda é cadastrada por faixa horária, turno, dia ou padrão semanal? Como representar operação contínua, mudanças em datas específicas e faixas sem necessidade? Descoberto significa turno sem responsável, quantidade abaixo da demanda, ou ambos? Definir também o significado de demanda ainda não cadastrada.

### D05 — Cobertura considera apenas quantidade ou também função?

**Base:** **OBSERVADO:** campo Cargo; **NÃO VERIFICADO:** exigência de função na cobertura.

**Decisão:** a farmácia exige somente número total de pessoas ou mínimos por função/qualificação? Uma mesma pessoa pode satisfazer mais de uma necessidade ao mesmo tempo? Que vínculos são necessários para calcular elegibilidade sem contar a mesma oferta indevidamente?

### D06 — Como intervalos e minutos parciais afetam a oferta?

**Base:** **OBSERVADO:** pausa 60 min no padrão sem desconto visível na timeline; **NÃO VERIFICADO:** pausa explícita na cobertura.

**Decisão:** é necessário informar o horário da pausa ou somente duração? Quando uma pessoa deixa de contar para cobertura? Qual granularidade usar para horários parciais, pausas e contagem, inclusive à meia-noite? A resposta separa duração líquida de disponibilidade operacional.

### D07 — Qual é o efeito de alterar somente uma data?

**Base:** **OBSERVADO:** parâmetros recorrentes; **NÃO VERIFICADO:** exceção diária e propagação.

**Decisão:** uma alteração na semana afeta apenas a atribuição selecionada, esta e futuras ocorrências ou o padrão? Como o gestor escolhe o alcance e como uma exceção é preservada se o padrão mudar? Definir a fronteira entre padrão e planejamento efetivo.

### D08 — Como representar folga, indisponibilidade e ausência de alocação?

**Base:** **OBSERVADO:** a referência usou Folga DSR tanto para sem escala quanto para folga do padrão.

**Decisão:** quais estados o MVP diferencia? Indisponibilidade pode ocupar parte do dia e atravessar datas? Qual prioridade tem sobre a recorrência e o que acontece com atribuições existentes? Decidir sem incorporar automaticamente categorias administrativas de RH.

### D09 — Como atribuir e reorganizar pessoas?

**Base:** **NÃO VERIFICADO:** atribuição direta, movimentação e arraste na referência.

**Decisão:** quais operações estarão disponíveis no calendário — selecionar e atribuir, mover, redimensionar, arrastar ou editar horários? Como transferir uma atribuição entre pessoas/dias e qual retorno apresentar se o destino for inválido? A existência de drag-and-drop é uma escolha de interação, não uma conclusão da referência.

### D10 — Como funcionam substituições e trocas?

**Base:** **NÃO VERIFICADO:** substituição e troca de turno.

**Decisão:** substituição transfere integralmente a jornada, permite cobertura parcial ou cria nova atribuição? Troca entre duas pessoas precisa manter ambas as jornadas válidas em conjunto? O que acontece com a oferta original e como evitar duplicação ou perda de cobertura?

### D11 — Quais situações são conflitos e qual sua severidade?

**Base:** **OBSERVADO:** rótulos de risco/CCT; **NÃO VERIFICADO:** detecção e bloqueio efetivos.

**Decisão:** quais regras o MVP verificará para sobreposição, indisponibilidade, função, descanso e outros limites escolhidos? Quais impedem a ação, quais alertam e quais admitem confirmação? Déficit de cobertura é tratado como conflito ou como pendência operacional separada? Não adotar números legais da interface como regra aprovada.

### D12 — Qual é a composição visual do calendário semanal?

**Base:** **OBSERVADO:** pessoas × horas para uma data; **NÃO VERIFICADO:** semana em uma grade.

**Decisão:** como distribuir pessoas, dias, horários e múltiplos segmentos sem ocultar a continuidade noturna? Como mostrar, na mesma leitura, folgas, indisponibilidades e descobertos? Definir início da semana e leitura de jornadas que começam fora da semana visível.

### D13 — O que constitui a operação planejada no MVP?

**Base:** **OBSERVADO:** empresa, filial no cadastro e funcionamento da empresa; **NÃO VERIFICADO:** escopo por unidade.

**Decisão:** a semana pertence a uma farmácia/unidade ou pode reunir várias? Funcionamento, demanda e pessoas são vinculados a qual escopo? Uma pessoa pode cobrir unidades diferentes e que colisões devem ser consideradas? Não presumir gestão multifilial completa.

### D14 — Como ciclos são ancorados e aplicados às pessoas?

**Base:** **OBSERVADO:** Plantão experimental com ciclo de 2 dias; **NÃO VERIFICADO:** aplicação nominal/defasagem.

**Decisão:** quais ciclos são necessários no cenário inicial e o que é sua data de início? O início é do padrão ou de cada pessoa? Como tratar equipes em fases diferentes, exceções e continuidade entre semanas? Definir necessidade de 12x36 no MVP sem inferir sua operação pelo rótulo da referência.

### D15 — Qual é a relação entre padrão e planejamento vigente/publicado?

**Base:** **OBSERVADO:** padrão e consulta diária; **NÃO VERIFICADO:** versão publicada independente.

**Decisão:** a semana é uma projeção sempre atualizada do padrão ou um planejamento que preserva suas atribuições após gerar? Alterar o padrão deve modificar semanas já vigentes? Qual referência determina o que a equipe deve cumprir em uma data?

### D16 — Precisamos de rascunho e publicação no MVP?

**Base:** **NÃO VERIFICADO:** estados de planejamento/publicação na referência.

**Decisão:** mudanças valem imediatamente ou existe revisão antes de tornar a semana vigente? Se houver rascunho, o que o gestor vê como cobertura e o que pode ser publicado com pendências? Se não houver, como tornar claro que a alteração já vale? Não incluir publicação como requisito decidido.

### D17 — Como mudanças são salvas, descartadas e desfeitas?

**Base:** **OBSERVADO:** retorno do editor sem Salvar seguido de valores originais; **INFERIDO:** descarte, sem prova geral.

**Decisão:** cada mudança no calendário é persistida imediatamente ou há salvamento por conjunto? Como indicar alterações pendentes, cancelar e recuperar um movimento? Como tratar falhas e evitar que o gestor acredite ter salvo algo que não foi confirmado?

### D18 — Como vigência e histórico afetam semanas existentes?

**Base:** **NÃO VERIFICADO:** histórico de vínculo e alterações retroativas.

**Decisão:** quando uma troca de padrão ou inativação começa a valer? O que acontece com jornadas passadas e futuras? Qual registro mínimo de mudanças é necessário para distinguir o plano anterior do atual, sem pressupor um módulo amplo de auditoria?

### D19 — Quais dados e ações de cadastro são mínimos para planejar?

**Base:** **OBSERVADO:** cadastro amplo, status e CPF exigido no cenário; **NÃO VERIFICADO:** necessidade desses dados para nosso planejamento.

**Decisão:** além do nome, quais dados de função, unidade, situação e disponibilidade são indispensáveis à farmácia? Como inatividade afeta atribuições existentes? Quem pode cadastrar pessoas, atribuir turnos e alterar a semana? Delimitar as responsabilidades necessárias sem importar o RH completo da referência.

### D20 — Precisamos copiar semanas e como tratar colisões na cópia?

**Base:** **OBSERVADO:** modelos e recorrência; **NÃO VERIFICADO:** cópia de planejamento diário/semanal.

**Decisão:** recorrência atende à preparação semanal ou é necessário copiar uma semana/dia? Se incluído, copia-se atribuição, demanda, exceções ou quais partes? O que acontece com indisponibilidades e atribuições já existentes no destino? Decidir inclusão e comportamento antes de implementar a operação.

## 8. Conclusão

### A. O que aprendemos de estruturalmente útil?

**OBSERVADO:** existem parâmetros de funcionamento, padrões de jornada, vínculo com colaborador e uma visualização diária nominal com contagem horária. O experimento semanal apresentou jornada em dias úteis e folga no sábado.

**INFERIDO:** separar operação, padrão, pessoa, ocorrência por data e oferta é uma base conceitual útil. Também é necessário distinguir presença prevista de presença real, duração líquida de disponibilidade e ausência de escala de folga.

**NÃO VERIFICADO:** a referência não demonstrou uma ligação completa entre demanda e oferta nem o fluxo de planejamento semanal exigido pelo MVP.

### B. Onde começa a diferenciação funcional do Gestão Escala?

**INFERIDO — avaliação de produto:** na transformação dessa consulta em planejamento semanal manipulável: atribuir e reorganizar pessoas, aplicar exceções/indisponibilidades, detectar conflitos e mostrar descobertos contra demanda, com continuidade entre datas na operação 24h da farmácia. Essas capacidades pertencem ao escopo declarado; não são alegações de ausência no PontoCorp.

### C. Quais decisões precedem a especificação funcional do MVP?

**INFERIDO — ordem de discussão sugerida:** começar por D01 (origem da semana), D02 (unidade turno), D03 (virada de dia), D04 (demanda/descobertos) e D07 (alcance das alterações). Elas condicionam como atribuir, calcular e modificar o planejamento.

As demais decisões D05–D06, D08–D20 precisam de resposta ou adiamento explícito com impacto delimitado antes de fechar as respectivas regras da especificação. Cobertura por função, pausas, indisponibilidades, conflitos e planejamento vigente são especialmente dependentes dessas primeiras definições.

**INFERIDO — parecer:** os três fluxos fornecem base suficiente para a discussão de produto; não fornecem respostas prontas às 20 decisões. O próximo resultado esperado é um registro das escolhas e dos limites do MVP, anterior à especificação final e à implementação. Nenhuma dessas escolhas foi tomada por este documento.
