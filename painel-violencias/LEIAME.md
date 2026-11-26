# Painel de Violência Interpessoal e Autoprovocada · VIII GERES

Notificações de violência interpessoal e autoprovocada do Sinan (VIVA Contínuo) de residentes dos 7 municípios da VIII Região de Saúde de Pernambuco (Afrânio, Cabrobó, Dormentes, Lagoa Grande, Orocó, Petrolina e Santa Maria da Boa Vista), de 2015 a 12/10/2026.

- **Endereço público (link oficial):** https://hallmeberg.github.io/portal-vigilancia-viii/painel-violencias/
- **Arquivo:** `index.html` (página única, com os dados agregados e os logos embutidos, cerca de 1,2 MB)
- **Fonte:** base do Sinan Net local da VIII GERES (`VIOLENET.DBF`), ficha de notificação versão 15/06/2015 e dicionário de dados v5.0/Patch 5.1
- **Publicado em:** 26/11/2026

## O que o painel mostra

| Aba | Conteúdo |
|---|---|
| Visão geral | Cartões-resumo, linha do tempo (por ano ou por mês), tipos de violência, **mapa da VIII GERES** (taxa por 100 mil hab. ou nº de casos) e casos por município |
| Quem sofre | Pirâmide por sexo e idade, raça/cor, escolaridade, situação conjugal, orientação sexual, identidade de gênero, deficiência, gestantes e zona |
| A violência | Tipo, meio de agressão, local, período do dia, dia da semana, repetição, motivação, mês e violência sexual (tipos e procedimentos) |
| Quem agride e a rede | Vínculo, sexo, ciclo de vida e uso de álcool do provável autor, número de envolvidos e encaminhamentos |
| Autoprovocada | Série, pirâmide, meio, repetição, local, raça/cor, período do dia e encaminhamentos das lesões autoprovocadas |
| **Alerta de reincidência** | Pessoas com **mais de uma tentativa de suicídio** notificada, por município de residência: total, últimos 90 dias, últimos 12 meses, mapa, tabela com nível de prioridade e série anual |
| Território | Residência × ocorrência × notificação |
| Quedas e acidentes | Fichas de quedas e outros acidentes registrados apenas como negligência, separadas das violências |
| Como lemos os dados | Etapas de limpeza do banco e critérios usados |

Filtros: município de residência, ano da notificação e recorte (todas, interpessoal ou autoprovocada). Tocar em um município no mapa ou na tabela também filtra o painel. Quando há pessoas em alerta no município escolhido, aparece uma faixa vermelha no topo com atalho para a aba de alerta.

## Alerta de reincidência de tentativa de suicídio

- **Critério:** mesma pessoa (nome e data de nascimento) com duas ou mais notificações de lesão autoprovocada em datas de ocorrência diferentes. Fichas da mesma pessoa com a mesma data de ocorrência contam uma vez só.
- **Município:** o de residência na notificação mais recente da pessoa.
- **Prioridade:** alta (última tentativa até 90 dias antes de 12/10/2026, a data mais recente da base), média (até 12 meses) e acompanhar (mais de 12 meses).
- **Situação na base atual:** 420 pessoas com 2 ou mais tentativas, 37 delas com a última nos 90 dias finais da base.

### Lista com o número da notificação no Sinan (restrita)

O painel é um site aberto, então mostra **somente contagens**. A relação de cada pessoa em alerta, com o **número da notificação no Sinan**, o município e o CNES da unidade notificadora, as datas de cada tentativa, o meio utilizado e a prioridade, está na planilha restrita `RESTRITO_alerta_reincidencia_autoprovocada_VIII_GERES.xlsx`, com uma aba por município.

Essa planilha **não deve ser enviada a este repositório** nem circular fora dos canais oficiais da vigilância, por conter dados sensíveis de saúde (LGPD, art. 11). Para localizar o caso no Sinan, use o número da notificação junto com o município de notificação.

## Tratamento dos dados

| Etapa | Registros |
|---|---|
| Notificações no banco (2015 a 12/10/2026) | 47.871 |
| Residentes da VIII GERES | 40.159 |
| Duplicidades prováveis excluídas | 83 |
| Não-casos excluídos (violência comunitária contra homens de 20 a 59 anos, NT nº 5/2024-CGVIVA) | 290 |
| Quedas e outros acidentes registrados como negligência (aba própria) | 19.204 |
| **Casos de violência analisados** | **20.582** |
| Reclassificados como violência sexual (estupro de vulnerável) | 361 |

- **Taxas por 100 mil habitantes:** população dos municípios usada nos painéis da VIII GERES (estimativas do IBGE de 2016 a 2026; para 2015 usa-se a de 2016). Em "todos os anos", a taxa é a média anual do período, com 2026 contado até 12/10. As taxas medem notificação e dependem também da capacidade de cada município de identificar e notificar.
- **Mapa:** malha municipal de Pernambuco do projeto geodata-br (IBGE), recortada para os 7 municípios.
- **Limitações:** residentes atendidos fora da região (sobretudo em Juazeiro/BA) só aparecem quando vieram pelo fluxo de retorno, que parece incompleto. Uma ficha pode marcar mais de um tipo, meio, autor ou encaminhamento.

## Como atualizar

1. Exporte do Sinan Net a base de violência interpessoal/autoprovocada (`VIOLENET.DBF`) e envie ao Claude.
2. O Claude refaz a limpeza, os agregados, o alerta de reincidência e a planilha restrita, e gera um novo `index.html`.
3. No GitHub, abra a pasta `painel-violencias`, clique em **Add file → Upload files**, envie o `index.html` novo e confirme em **Commit changes**. O site se atualiza em cerca de 1 minuto.
4. Envie a nova planilha restrita às coordenações municipais pelos canais oficiais.

## Cuidados

- O `index.html` traz apenas contagens agregadas: nenhum nome, endereço, telefone, Cartão SUS ou número de notificação.
- Para retirar o painel do ar, apague a pasta `painel-violencias` do repositório e volte o cartão do portal para `st:"soon"`.

Contato: vigilanciasaude8geres@gmail.com · (87) 3866-6557
