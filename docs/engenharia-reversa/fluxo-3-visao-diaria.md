# Fluxo 3 — Visão Diária / Distribuição Operacional

Referência: PontoCorp. Projeto: Gestão Escala.

## Base e limites da consolidação

- **OBSERVADO:** este registro utiliza somente observações passivas do REA, imagens e relatos do usuário já coletados no fluxo. Não houve nova investigação para produzir o documento.
- **OBSERVADO:** a conta foi inicialmente observada sem colaboradores; depois, com dois colaboradores de teste sem escala; por fim, com somente o Teste 01 vinculado à escala Comercial Padrão (Seg-Sex).
- **OBSERVADO — relato do usuário:** a criação com CPF válido foi aceita; a reutilização do mesmo CPF foi rejeitada; outro CPF permitiu criar o segundo colaborador. A implementação dessa validação não foi investigada. Identificadores pessoais não são reproduzidos neste documento.
- **OBSERVADO — consolidação posterior fornecida pelo usuário:** apenas Nome habilitou o botão, mas a tentativa de envio sem CPF não permitiu concluir o cadastro. **NÃO VERIFICADO:** conjunto mínimo completo de campos; habilitação não equivale a aceitação do envio. O complemento consta no [Fluxo 1](fluxo-1-colaboradores.md).
- **OBSERVADO:** não foram encontrados arquivos dos Fluxos 1 e 2 no diretório local durante a preparação desta consolidação. A estrutura segue as seções solicitadas e a classificação epistemológica das consolidações do chat.

Convenção: **OBSERVADO** = evidência direta na interface ou relato explicitamente identificado; **INFERIDO** = interpretação; **NÃO VERIFICADO** = comportamento não demonstrado. Textos promocionais ou classificações do produto não comprovam sua execução.

## 1. Objetivo da tela

- **OBSERVADO:** a tela se chama “Disponibilidade Operacional & Escala”, em `/rh/daily-roster`, sob RH → Visão Diária. Apresenta pessoas e sua situação para uma data selecionada.
- **OBSERVADO:** quando há pessoa com jornada prevista, apresenta “Cobertura Operacional (Timeline)”, horários e contagem de pessoas por hora. Pessoas sem jornada aparecem em seção separada.
- **INFERIDO:** sua finalidade principal demonstrada é consultar a disponibilidade prevista derivada das escalas vinculadas, por dia.
- **OBSERVADO:** o cadastro de Escalas investigado anteriormente define padrões de dias, horários, intervalos e ciclos. Nesta tela, o experimento mostrou o resultado diário de um vínculo com o padrão semanal.
- **NÃO VERIFICADO:** uso da Visão Diária para construir, editar ou publicar planejamento. Também não foi demonstrado que represente presença real ou ponto registrado.

## 2. Estrutura da tela

### Data e navegação

- **OBSERVADO:** título da aba do navegador “PontoCorp”; consulta de um dia por vez, com data numérica e dia da semana por extenso.
- **OBSERVADO:** datas inspecionadas: quarta-feira 14/10/2026, sexta-feira 16/10/2026 e sábado 17/10/2026.
- **OBSERVADO:** controles Dia anterior, Próximo dia e Atualizar; botão Hoje apareceu nas datas posteriores à data inicial da consulta. A navegação manual entre datas foi utilizada.
- **NÃO VERIFICADO:** execução dos botões Hoje e Atualizar, seleção direta de data e visualização semanal/mensal.

### Indicadores

**OBSERVADO:** indicadores superiores e valores nos cenários documentados:

| Cenário | Escalados hoje | Em folga regular | Férias & atestados | Risco de interjornada |
|---|---:|---:|---:|---:|
| 14/10, sem colaboradores | 0 | 0 | 0 | 0 |
| 14/10, dois sem escala | 0 | 2 | 0 | 0 |
| 14/10, Teste 01 com escala e Teste 02 sem escala | 1 | 1 | 0 | 0 |
| 16/10, mesmo vínculo | 1 | 1 | 0 | 0 |
| 17/10, mesmo vínculo | 0 | 2 | 0 | 0 |

- **OBSERVADO:** descrições dos indicadores: “Em atividade operacional”, “DSR e folgas de escala”, “Ausências programadas/médicas” e “Conformidade integral”. O título “Escalados hoje” permaneceu mesmo ao consultar outras datas.
- **NÃO VERIFICADO:** cálculo de risco de interjornada e situações positivas de férias/atestados.

### Categorias, busca e organização

- **OBSERVADO:** categorias Visão Completa, Em Turno e Folgas & Ausências, com contadores nas duas últimas.
- **OBSERVADO:** em 16/10, Em Turno (1) mostrou somente a timeline do Teste 01; Folgas & Ausências (1) mostrou somente o cartão do Teste 02. Os indicadores gerais permaneceram 1/1/0/0 em ambas.
- **INFERIDO:** as categorias filtram seções do resultado diário e preservam o resumo geral da data.
- **OBSERVADO:** busca com placeholder “Buscar por colaborador, cargo ou setor...”.
- **NÃO VERIFICADO:** funcionamento da busca, filtros por filial/escala e agrupamentos por cargo ou setor.
- **OBSERVADO:** nos estados capturados, o conteúdo relevante coube no viewport; a acessibilidade não revelou seções adicionais pertinentes. A timeline apresentou uma barra de rolagem horizontal, sem teste de sua utilização.

## 3. Colaborador na Visão Diária

### Sem jornada na data

- **OBSERVADO:** seção “De Folga, Férias ou Ausências”, descrita como “Colaboradores que não possuem jornada escalada para esta data”.
- **OBSERVADO:** cartões apresentam avatar/iniciais, nome, cargo ou “Sem cargo”, classificação e explicação da ausência de jornada.
- **OBSERVADO:** Teste 01 e Teste 02, inicialmente sem escala, apareceram como “Folga DSR” e “Sem escala vinculada”, sem horários.
- **OBSERVADO:** em 17/10, Teste 01 apareceu como “Folga DSR” e “Folga da Escala”; Teste 02 permaneceu como “Folga DSR” e “Sem escala vinculada”.
- **INFERIDO:** o produto agrega sob uma mesma classificação visual motivos diferentes para ausência de jornada; a explicação do cartão distingue os dois casos testados.
- **NÃO VERIFICADO:** ausência real, direito a DSR ou folga cadastrada para quem está sem escala. O rótulo do produto não comprova essas condições.

### Com jornada na data

- **OBSERVADO:** Teste 01 passou a aparecer em uma linha nominal da timeline, com avatar, identificação e barra 08:00–18:00 nos dias úteis observados.
- **OBSERVADO:** a identificação visual na linha foi truncada; a acessibilidade confirmou o nome completo. A linha apresentou o texto genérico “COLABORADOR”.
- **OBSERVADO:** não foram exibidos nessa linha nome da escala, filial, departamento ou intervalo separado nos estados capturados.
- **NÃO VERIFICADO:** apresentação de cargos/departamentos preenchidos, férias, atestados, ausências e riscos individuais.

## 4. Escala → jornada diária

**OBSERVADO:** sequência do experimento manual documentado:

1. Em 14/10, ambos os colaboradores estavam sem escala e fora da área de trabalho; os dois contavam como folga regular.
2. O formulário de edição do Teste 01 confirmou “Sem escala”.
3. O usuário selecionou somente “Comercial Padrão (Seg-Sex)” e acionou Salvar Alterações; relatou retorno ao diretório.
4. Em 14/10, Teste 01 apareceu na timeline 08:00–18:00; Teste 02 permaneceu sem escala e em folga. O indicador de escalados passou de 0 para 1.
5. Em 16/10, sexta-feira, Teste 01 também apresentou 08:00–18:00.
6. Em 17/10, sábado, Teste 01 saiu da timeline e apresentou “Folga da Escala”.

- **OBSERVADO — referência previamente documentada:** o padrão Comercial tinha segunda a sexta como trabalho, sábado/domingo como folga, entrada 08:00, saída 18:00 e intervalo de 60 minutos.
- **INFERIDO:** a comparação antes/depois, mantendo Teste 02 como controle, sustenta a relação funcional: escala semanal vinculada → jornada prevista da pessoa na data, respeitando o dia de trabalho/folga nos exemplos testados.
- **OBSERVADO:** a barra diária foi contínua entre 08:00 e 18:00. A contagem mostrou 1 em cada faixa de 08:00–09:00 até 17:00–18:00 e 0 nas demais faixas.
- **OBSERVADO:** o resumo cobre dez faixas de uma hora, embora o padrão tivesse uma hora de intervalo e nove horas líquidas no editor. A timeline não apresentou esse desconto visualmente.
- **NÃO VERIFICADO:** não se pode generalizar esse tratamento para intervalos com início/retorno explícitos, minutos fracionados, outros modelos, ciclos ou jornada noturna. Não é evidência de dez horas de trabalho líquido ou presença efetiva.
- **OBSERVADO:** o início de apuração do ponto exibido no cadastro era 15/10/2026, mas a jornada prevista apareceu em 14/10. **NÃO VERIFICADO:** efeitos dessa data sobre outras funcionalidades; não foi alterada no experimento.

## 5. Cobertura operacional

| Capacidade | Classificação | Evidência/limite |
|---|---|---|
| Pessoas por faixa horária | **OBSERVADO** | Linha Total Disponível — Pessoas por hora, com 0/1 por faixa de uma hora no cenário testado |
| Distribuição nominal por horário | **OBSERVADO** | Uma linha de pessoa com barra 08:00–18:00 |
| Meta de cobertura nesta tela | **NÃO VERIFICADO** | Nenhuma meta apresentada; a meta diária 3 encontrada no editor não foi demonstrada aqui |
| Déficit/excesso versus demanda | **NÃO VERIFICADO** | Nenhuma comparação ou alerta demonstrado |
| Cobertura por cargo/função | **NÃO VERIFICADO** | Busca menciona cargo/setor, mas não houve demanda ou contagem por função |
| Faixas com zero pessoas | **OBSERVADO** | Contagem zero fora de 08:00–18:00 |
| Identificação de horários operacionalmente descobertos | **NÃO VERIFICADO** | Zero pessoas não prova déficit sem confrontar funcionamento e demanda |
| Visualização das 24 horas | **OBSERVADO** | Eixo 00h–23h, com faixas até 24:00 na acessibilidade |
| Cobertura contínua/virada de dia | **NÃO VERIFICADO** | Eixo de 24 horas não comprova tratamento de plantões atravessando datas |

- **OBSERVADO:** textos “Operação & Cobertura Diária” e “Distribuição contínua de turnos ao longo das 24 horas do dia”.
- **INFERIDO:** a interface ajuda a consultar oferta prevista de pessoas por horário.
- **NÃO VERIFICADO:** gestão de cobertura baseada em necessidade, descontando pausas e considerando qualificações. Os textos não comprovam essas capacidades.

## 6. Planejamento e edição

- **OBSERVADO — relato do usuário:** a barra da jornada não era clicável no teste solicitado.
- **OBSERVADO:** nenhuma ação individual de edição ou publicação apareceu nas capturas e na acessibilidade dos estados investigados.
- **INFERIDO:** a função demonstrada da timeline é consulta.

| Capacidade | Resultado |
|---|---|
| Edição exclusiva de uma data | **NÃO VERIFICADO** |
| Troca de turno | **NÃO VERIFICADO** |
| Substituição de colaborador | **NÃO VERIFICADO** |
| Drag-and-drop/reorganização | **NÃO VERIFICADO**; não foi realizado arraste |
| Alocação manual na Visão Diária | **NÃO VERIFICADO** |
| Copiar dia/semana | **NÃO VERIFICADO** |
| Publicar/salvar planejamento | **NÃO VERIFICADO** |
| Registrar folga/indisponibilidade pontual | **NÃO VERIFICADO** |

**NÃO VERIFICADO:** ausência de controles e clique sem ação não permitem concluir que essas funcionalidades inexistam em outros caminhos ou estados.

## 7. Modelo funcional descoberto

```text
Horário de funcionamento da empresa + meta diária
    └─ [NÃO VERIFICADO] comparação com a oferta na Visão Diária

Escala semanal com dias/horários/folgas
    └─ [OBSERVADO] seleção e salvamento no cadastro do Teste 01
         Colaborador vinculado + Data consultada
             └─ [INFERIDO, sustentado pelo experimento] determinação diária
                  ├─ Dia útil testado → jornada 08:00–18:00
                  │    └─ [OBSERVADO] linha da timeline + contagem horária
                  └─ Sábado testado → Folga da Escala
                       └─ [OBSERVADO] cartão de folga

Colaborador sem escala + Data consultada
    └─ [OBSERVADO, nos casos testados] Sem escala vinculada / Folga DSR
         └─ cartão na seção de folgas/ausências

Jornadas e situações da data
    └─ [OBSERVADO] Visão Completa / Em Turno / Folgas & Ausências
```

- **NÃO VERIFICADO:** integração com ausências registradas, prioridade de exceções, ciclos, data de vigência e alterações retroativas.

## 8. Comparação com o MVP Gestão Escala

**INFERIDO — avaliação de produto:** as prioridades abaixo preservam o escopo definido pelo usuário. O PontoCorp é referência observacional, não especificação do Gestão Escala.

| Capacidade encontrada | Prioridade proposta | Relação com o MVP |
|---|---|---|
| Pessoa × horário com jornada visível | ESSENCIAL PARA O MVP | Componente da grade semanal pessoas × dias × horários; somente consulta diária foi observada |
| Dias de trabalho/folga derivados do padrão | ESSENCIAL PARA O MVP | Base para jornadas e folgas; não substitui atribuição e exceções |
| Distinção de pessoas sem jornada | ESSENCIAL PARA O MVP | No MVP, diferenciar sem alocação, folga e indisponibilidade; PontoCorp agregou casos distintos |
| Contagem de pessoas por faixa horária | ESSENCIAL PARA O MVP | Insumo para identificar cobertura; demanda e déficit ainda precisam de solução própria |
| Eixo cobrindo 24 horas | ESSENCIAL PARA O MVP | Necessário à farmácia; virada de dia não foi demonstrada |
| Categorias de consulta e busca nominal | ESSENCIAL PARA O MVP | Apoio à leitura/reorganização da equipe; busca não foi testada |
| Navegação diária complementar | ÚTIL DEPOIS | O calendário semanal continua sendo a visão principal do MVP |
| Avatar e apresentação visual de cartões | ÚTIL DEPOIS | Conveniência visual, sem alterar o núcleo operacional |
| Agrupamento específico de férias e atestados | ÚTIL DEPOIS | Motivos especializados; indisponibilidade básica continua essencial |
| Indicador específico de risco trabalhista/interjornada | FORA DO ESCOPO INICIAL | Não demonstrou cálculo; não substitui os conflitos operacionais essenciais do MVP |
| CPF e sua unicidade no cadastro de referência | FORA DO ESCOPO INICIAL | Foi requisito/validação do produto de referência, sem necessidade demonstrada para o planejamento do MVP |

- **NÃO VERIFICADO no PontoCorp:** calendário semanal, atribuição de turnos, reorganização, conflitos, exceções pontuais e déficit contra demanda. **INFERIDO — avaliação:** continuam essenciais ao MVP mesmo sem demonstração no produto de referência.

## 9. Lacunas restantes relevantes ao MVP

**NÃO VERIFICADO:**

- Grade semanal de pessoas × dias × horários e navegação entre semanas.
- Atribuição manual de turnos e edição pontual sem modificar o padrão recorrente.
- Trocas, substituições, movimentação entre dias/pessoas e eventual drag-and-drop.
- Folgas/indisponibilidades específicas por data e prioridade sobre a escala recorrente.
- Conflitos de sobreposição, indisponibilidade e descanso entre jornadas, incluindo apresentação/resolução.
- Demanda mínima, déficit/excesso, turnos descobertos e relação com funcionamento e meta operacional.
- Cobertura por cargo/função, equipe ou unidade, e permissões de alocação entre unidades.
- Desconto de pausas com horários explícitos na contagem de cobertura.
- Granularidade de minutos, horas parciais e somatório com várias pessoas sobrepostas.
- Múltiplos turnos e múltiplas jornadas da mesma pessoa na mesma data.
- Operação 24h: início em uma data e término na seguinte, continuidade no dia seguinte e contagem sem duplicação.
- Aplicação diária de ciclos 12x36/6x2 e defasagem individual de início do ciclo.
- Vigência/histórico e impacto de mudar padrões sobre planejamento existente.
- Cópia de dias/semanas, salvamento/publicação e distinção entre rascunho e planejamento vigente, caso adotados no MVP.

## 10. Conclusão do fluxo

### A. Consulta, planejamento ou ambos?

**INFERIDO:** principalmente consulta, com base nos comportamentos demonstrados. **OBSERVADO:** navegação diária, filtros, timeline e contadores; barra sem ação de clique conforme relato. **NÃO VERIFICADO:** planejamento editável por outros caminhos.

### B. Escala recorrente gera jornada diária?

**INFERIDO — SIM, no cenário semanal testado:** vínculo salvo no Teste 01 foi seguido de jornada 08:00–18:00 em quarta/sexta e Folga da Escala no sábado, enquanto o Teste 02 permaneceu sem escala. **NÃO VERIFICADO:** generalização para todos os modelos e condições.

### C. Grade operacional pessoas × dias × horários?

**OBSERVADO:** pessoas × horas para uma data, com navegação diária. **NÃO VERIFICADO:** pessoas × vários dias × horários em uma grade semanal.

### D. Gestão efetiva de cobertura?

**OBSERVADO:** contagem horária de oferta prevista, além dos indicadores agregados. **NÃO VERIFICADO:** gestão contra demanda, déficits, excesso, função ou necessidade de abertura. Há mais que contadores superiores, mas não foi demonstrada gestão completa de cobertura.

### E. Suficientemente compreendido para avançar?

**Fluxo 3 — Visão Diária suficientemente compreendido para avançar: SIM.**

**INFERIDO — parecer:** foram demonstrados estrutura diária, distinção com/sem jornada, vínculo com padrão semanal, folga derivada, timeline nominal, contagem horária e filtros complementares. Isso basta para avançar na definição funcional, preservando as lacunas de planejamento semanal, cobertura contra demanda e operação 24h. Não equivale à validação completa dessas capacidades no PontoCorp.

## Referências de evidência já coletada

| Evidência REA | Observação |
|---|---|
| `ev_59617204b8f99a454ef2f1d833dd37082fcfc135659e8cb3bf1aeb2110f6fc3b` | Visão Diária vazia, 14/10 |
| `ev_f5bb756a0695f397278331bcff9a65ab6eedc5456bff00b7a3efa51825e0ef37` | Dois colaboradores sem escala |
| `ev_f4d53fd82cf21b4b7605b39710bf03752e7c39ffcbae9a2a53ddd5184606397c` | Teste 01 na timeline após vínculo, 14/10 |
| `ev_821a6666700e843f9b811adfeab979361a3a64a99a91a44815def32841810861` | Sábado, 17/10: Folga da Escala |
| `ev_08c1edcd79a190ca1ebe4e6eb3d3386faa18143f1af22ac4b5566777468943a6` | Sexta, 16/10: filtro Em Turno |

**OBSERVADO:** a comparação também utiliza a captura de Folgas & Ausências de 16/10, imagens do formulário e relatos manuais presentes no chat. As referências acima identificam observações já realizadas; o documento não incorpora novas consultas à aplicação.
