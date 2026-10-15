# Fluxo 2 — Escalas

Referência: PontoCorp. Projeto: Gestão Escala.

## Base e limites da consolidação

- **OBSERVADO — fonte consolidada pelo usuário:** este registro utiliza exclusivamente a consolidação fornecida para completar a documentação da Fase 1. Não houve nova investigação, uso do REA ou navegação para produzir o arquivo.
- **OBSERVADO:** a lista inicial tinha uma escala semanal e nenhum colaborador vinculado. O experimento posterior de vínculo no Fluxo 3 representa outro estado.
- **NÃO VERIFICADO:** descrições e alegações de conformidade não comprovam correção jurídica, bloqueios efetivos ou funcionamento em outros cenários.

Convenção: **OBSERVADO** = conteúdo ou comportamento documentado; **INFERIDO** = interpretação; **NÃO VERIFICADO** = comportamento não demonstrado. Configuração experimental no editor não é sinônimo de registro salvo.

## 1. Conceito de Escala

- **OBSERVADO:** URL `/rh/schedules`; título “Gestão, Turnos & Regras de Escala”. Há parâmetros semanais e de ciclo, horários, intervalos, dias/folgas e controles de vinculação a colaboradores.
- **INFERIDO:** Escala funciona principalmente como um padrão reutilizável de jornada, semanal ou em ciclo, associável a pessoas.
- **NÃO VERIFICADO:** grade nominal de planejamento por período nessa tela, múltiplas jornadas por pessoa, exceções por data e publicação de planejamento.
- **INFERIDO:** esse objeto não deve ser automaticamente equiparado ao calendário operacional semanal pretendido para o Gestão Escala.

## 2. Lista de Escalas

### Organização e indicadores

**OBSERVADO:** modos Tabela e Cards; busca indicada por nome, política ou modalidade. Estado inicial:

| Indicador | Valor |
|---|---:|
| Escalas | 1 |
| Semanais | 1 |
| Em ciclo | 0 |
| Colaboradores vinculados | 0 |

**OBSERVADO:** o registro “Comercial Padrão (Seg-Sex)” apresentou:

| Informação | Conteúdo |
|---|---|
| Modalidade | SEMANAL / 5X2 |
| Horário | 08:00–18:00 |
| Intervalo | 60 minutos |
| Política | CLT Padrão |
| Colaboradores | Inicialmente 0 |

- **OBSERVADO:** ações Assistente Guiado, Nova Escala de Trabalho, Vincular, Editar e Excluir; Ver Detalhes nos cards.
- **NÃO VERIFICADO:** execução de busca, assistente, criação, exclusão ou vinculação por essa lista; a existência de botões não comprova seus resultados.

### Modelos rápidos

**OBSERVADO:** Comercial 5x2, Varejo & Lojas 6x1, Padarias & Bares 6x1, Plantão 12x36 e Estágio 30h.

**INFERIDO:** são entradas para iniciar configurações a partir de modelos, não cinco registros adicionais. **NÃO VERIFICADO:** resultado de criar por cada entrada.

## 3. Estrutura do editor

**OBSERVADO:** quatro áreas identificadas:

1. Horário de Funcionamento.
2. Padrões & Ciclos.
3. Alertas CCT.
4. Limites & Tolerâncias.

### 1. Horário de Funcionamento

- **OBSERVADO:** título “Horário de Funcionamento da Empresa”, configuração de operação e meta de cobertura por dia, com controles individuais.
- **OBSERVADO:** segunda a domingo marcados, abertura 07:00, fechamento 22:00 e meta de cobertura 3 em cada dia; texto “Janela Operacional Ativa”.
- **OBSERVADO:** nenhum seletor de filial apareceu nessa área no estado investigado.
- **INFERIDO:** representa a janela de operação da empresa, distinta da jornada individual.
- **NÃO VERIFICADO:** escopo global ou por escala/unidade, desativação dos dias, funcionamento 24h e comparação real com pessoas escaladas. Meta diária 3 não comprova exigência simultânea de três pessoas durante toda a janela.

### 2. Padrões & Ciclos

**OBSERVADO:** nome, modelo, dias/ciclo, horários, intervalo, personalização por dia e projeção individual de 30 dias. Os estados e experimentos estão detalhados na seção 4.

### 3. Alertas CCT

**OBSERVADO:** painel no estado Plantão com avaliações dominical, interjornada, feriados e carga semanal. Resultados e limites de interpretação estão na seção 5.

### 4. Limites & Tolerâncias

**OBSERVADO:** tolerância de entrada, intervalo/almoço, janela de banco de horas e Salvar Escala. Valores e divergências estão na seção 5.

**NÃO VERIFICADO:** variações condicionais dessas áreas e comportamentos de validação/envio não descritos na fonte.

## 4. Padrões & Ciclos

### Modelos/tipos expostos

**OBSERVADO:** opções no editor:

| Modelo | Informação fornecida na consolidação |
|---|---|
| Comercial 5x2 (40h) | Seg–Sex, 40h/semana |
| Comercial 44h compensado | Modelo apresentado |
| Estágio 30h | Modelo apresentado |
| Estágio/Aprendiz 20h | Modelo apresentado |
| Varejo & Loja 6x1 | Modelo apresentado |
| Alimentação 6x1 turno partido | Modelo apresentado |
| Alimentação & Produção 6x1 | 04:00–12:20 |
| Plantão 12x36 | Selecionado no experimento |
| Indústria 6x2 | Modelo apresentado |
| Jornada Flexível | Modelo apresentado |

**NÃO VERIFICADO:** seleção e parâmetros resultantes dos demais modelos além dos estados Comercial e Plantão documentados.

### Comercial original versus experimento Plantão

| Parâmetro — OBSERVADO | Comercial original | Plantão experimental |
|---|---|---|
| Nome | Comercial Padrão (Seg-Sex) | Escala Plantão 12x36, alterado automaticamente |
| Modo | SEMANAL 5X2 | CICLO |
| Trabalho/folga | Segunda a sexta trabalho; sábado/domingo folga | Ciclo de 2 dias: D1 trabalho, D2 folga |
| Entrada/saída | 08:00–18:00 | 07:00–19:00 |
| Intervalo | 60 minutos, por duração | 60 minutos |
| Jornada líquida apresentada | 9h/dia | 11h/dia |
| Carga semanal projetada | 45h | 38,5h |

- **OBSERVADO:** a grade do ciclo apresentava alternância trabalho/folga. A fonte não documenta um teste de modificação desses dias.
- **OBSERVADO:** a projeção de 30 dias é para um “colaborador modelo”.
- **INFERIDO:** os parâmetros geram uma previsão individual de recorrência, sem comprovar distribuição nominal da equipe.
- **NÃO VERIFICADO:** início/defasagem individual de ciclos e aplicação diária efetiva do Plantão. A projeção no editor não é comprovação de atribuição operacional salva.

### Intervalos

- **OBSERVADO:** modos por duração e por horário. No experimento Plantão, o modo por horário apresentou entrada 07:00, início de intervalo 12:00, retorno 13:00 e saída 19:00.
- **INFERIDO:** esse modo permite representar a posição da pausa dentro da jornada, além da duração.
- **NÃO VERIFICADO:** validações da sequência, múltiplas pausas, intervalos noturnos e efeitos sobre cobertura. O tratamento observado posteriormente na timeline é restrito ao cenário descrito no Fluxo 3.

### Personalização diária

- **OBSERVADO:** inicialmente desligada no Comercial; ao ativá-la no experimento, apareceram cartões de segunda a domingo com horários e intervalos próprios, modelos rápidos e ações de sincronizar a base e copiar a base para todos.
- **OBSERVADO:** trabalho/folga do ciclo permanecia separado da personalização dos horários.
- **NÃO VERIFICADO:** domingo com personalização desligada não foi demonstrado como folga; desligar a personalização não pode ser interpretado como fechamento ou indisponibilidade.
- **INFERIDO:** personalização diária e sequência do ciclo são dimensões distintas.
- **NÃO VERIFICADO:** precedência entre elas, efeito de horários divergentes, execução das ações de sincronizar/copiar e persistência das personalizações.

## 5. Regras, limites e alertas

### Alertas CCT

**OBSERVADO — textos/resultados do produto no estado Plantão:**

| Tema | Apresentação documentada |
|---|---|
| Dominical | Não aplicável |
| Interjornada | Mínimo 11h; 100% em conformidade no estado apresentado |
| Feriados | Mapeados |
| Limite semanal | Referência a média de 44h; 38,5h mapeadas |

**NÃO VERIFICADO:** correção jurídica, convenção aplicável, feriados considerados, execução de travas e validade dos cálculos. A classificação exibida não prova cumprimento legal.

### Limites & Tolerâncias

**OBSERVADO:**

| Campo | Valor apresentado |
|---|---:|
| Tolerância de entrada | 10 minutos |
| Intervalo/almoço | 60 minutos |
| Janela de banco de horas | 180 dias |

- **OBSERVADO:** a ajuda da tolerância mencionava padrão legal de 15 minutos; havia ação Salvar Escala.
- **NÃO VERIFICADO:** limites aceitos, sincronização do intervalo entre abas e efeitos desses parâmetros sobre ponto e planejamento.

### Divergências preservadas

| Evidência — OBSERVADO | Limite |
|---|---|
| Rótulo Comercial 5x2 (40h) versus projeção atual de 45h | **NÃO VERIFICADO:** causa e tratamento da diferença |
| Modelo rápido descrevia 08:00–17:00; registro original tinha 08:00–18:00 | **NÃO VERIFICADO:** razão da diferença; não são automaticamente a mesma configuração |
| Tolerância configurada 10; ajuda mencionava 15 | **NÃO VERIFICADO:** causa, validação e correção jurídica |

**NÃO VERIFICADO:** essas diferenças não autorizam corrigir valores, presumir erro de implementação ou afirmar que o produto bloqueia o salvamento.

## 6. Edição e persistência

- **OBSERVADO:** foram modificados manualmente modelo Plantão, modo de intervalo e personalização no editor. O usuário retornou sem Salvar; posteriormente o editor mostrou novamente os valores originais.
- **INFERIDO:** o resultado é consistente com descarte das alterações experimentais.
- **NÃO VERIFICADO:** mecanismo geral de persistência, abrangência do descarte sobre todos os campos, salvamento automático, comportamento com colaboradores vinculados e confirmação direta de todo o estado armazenado.
- **NÃO VERIFICADO:** a ausência das mudanças no editor posterior não comprova por si só como o backend realiza persistência. Nenhuma investigação de implementação é parte desta consolidação.

## 7. Modelo funcional observado/inferido

| Relação | Evidência e classificação |
|---|---|
| Empresa → horário operacional | **OBSERVADO:** título e parâmetros da primeira aba |
| Empresa/unidade → escala | **INFERIDO:** organização do domínio; vínculo específico com unidade **NÃO VERIFICADO** |
| Escala → dias/horários/intervalos/folgas/ciclo | **OBSERVADO:** campos e estados do editor |
| Escala ↔ colaborador | **OBSERVADO:** relação apresentada pela interface; vínculo e resultado diário posteriormente documentados no Fluxo 3 |
| Regras recorrentes → datas | **OBSERVADO:** projeção no editor; **INFERIDO**, sustentado pelo experimento semanal posterior, quanto à geração da jornada prevista na consulta |
| Horário operacional + pessoas → cobertura | **NÃO VERIFICADO:** integração da demanda com a oferta; o Fluxo 3 demonstrou contagem horária, não comparação com meta |

**INFERIDO:** a referência separa configuração operacional, padrão de jornada e consulta diária das pessoas. A integração completa entre as camadas não foi demonstrada.

## 8. Principais descobertas

- **OBSERVADO:** há padrões semanais e ciclos; o experimento Plantão produziu dois dias alternando trabalho/folga e parâmetros próprios.
- **OBSERVADO:** janela operacional e meta diária aparecem em área separada da jornada do colaborador modelo.
- **OBSERVADO:** o editor apresenta intervalos por duração/horário, personalização diária, projeção e parâmetros de CCT/ponto.
- **INFERIDO:** Escala é principalmente um padrão reutilizável de jornada; a tela não demonstrou planejamento nominal semanal editável.
- **OBSERVADO:** rótulos e valores projetados divergem nos casos preservados acima; suas causas permanecem **NÃO VERIFICADAS**.

## 9. Relevância para o MVP Gestão Escala

**INFERIDO — avaliação de produto, não especificação funcional:**

| Conceito | Relevância |
|---|---|
| Padrões de jornada, horários e intervalos | Relevantes à formação de jornadas e atribuições |
| Trabalho/folga e ciclos | Relevantes; ciclos podem ser necessários a 12x36 e operações contínuas |
| Pessoa ↔ escala | Relevante como base recorrente, sem substituir alterações pontuais |
| Funcionamento e meta operacional | Conceitos úteis para confrontar demanda e oferta; integração da referência não comprovada |
| Personalização por dia e modelos rápidos | Podem facilitar configuração; prioridade depende do cenário |
| CCT, banco de horas e regras trabalhistas avançadas | Não se tornam requisitos automáticos do MVP |

**INFERIDO:** o Gestão Escala permanece orientado a calendário semanal, pessoas × dias × horários, atribuição, folgas/indisponibilidades, reorganização, conflitos e horários descobertos, incluindo farmácia 24h. O modelo administrativo do PontoCorp não redefine esse escopo.

## 10. Lacunas ainda existentes

**NÃO VERIFICADO:**

- Alocação nominal pela tela de Escalas, múltiplos vínculos e vigência/histórico.
- Aplicação operacional de ciclos, início/defasagem por pessoa e modelos alternativos não selecionados.
- Jornada atravessando meia-noite, operação 24h e continuidade entre datas.
- Múltiplos turnos, pausas e cálculo de cobertura por função/unidade.
- Comparação entre janela/meta operacional e oferta; déficit/excesso e horários descobertos.
- Folgas extraordinárias, indisponibilidades e exceções por data versus padrão recorrente.
- Conflitos, substituições e reorganização de pessoas.
- Precedência de personalização diária/ciclo e efeito das ações de cópia/sincronização.
- Validações reais, execução dos alertas e persistência geral.

## 11. Conclusão do fluxo

**Fluxo 2 — Escalas suficientemente compreendido para avançar: SIM.**

**INFERIDO — parecer:** parâmetros, padrões semanais/cíclicos, janela operacional e projeções estão suficientemente delimitados para avançar à distribuição diária, sem declarar validados os comportamentos pendentes. O objeto seguinte é RH → Visão Diária, documentado no [Fluxo 3](fluxo-3-visao-diaria.md). O cadastro que apresenta o vínculo pessoa ↔ escala consta no [Fluxo 1](fluxo-1-colaboradores.md).
