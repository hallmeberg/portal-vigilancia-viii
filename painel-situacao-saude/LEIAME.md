# Painel de Situação de Saúde · VIII GERES

Mortalidade e natalidade da VIII Região de Saúde de Pernambuco e de seus 7 municípios (Afrânio, Cabrobó, Dormentes, Lagoa Grande, Orocó, Petrolina e Santa Maria da Boa Vista), de 2006 a 2026, no modelo do Card de Indicadores SEPLAG/NGR da SES-PE.

- **Endereço público (link oficial):** https://hallmeberg.github.io/portal-vigilancia-viii/painel-situacao-saude/
- **Arquivo:** `index.html` (página única, com os dados agregados embutidos, cerca de 1,1 MB)
- **Publicado no GitHub em:** 26/11/2026, a partir da versão do Claude (https://claude.ai/artifact/V2TtZXG5HCFiHPV4uT1WgL), que deixa de ser o link oficial

## O que o painel mostra

| Seção | Conteúdo |
|---|---|
| Indicadores | 7 indicadores de mortalidade (causas evitáveis, DCNT prematura, infância, infantil, materna, acidente de transporte terrestre, a esclarecer) e 1 de natalidade (mães com 7+ consultas de pré-natal), com meta do Card de Metas da Saúde de PE para 2026 |
| Série histórica | Evolução de cada indicador de 2006 a 2026, com a meta e o traço do território em relação à VIII GERES |
| Comparação entre municípios | Mapa e barras por município no ano escolhido |
| Tabela | Todos os anos (2006–2026) de uma vez, por indicador |
| Perfil dos nascidos vivos | Anomalia congênita, tipo de parto, sexo, idade da mãe, semanas de gestação e peso ao nascer, com tipos de anomalia por grupo prioritário do Ministério da Saúde |
| Campo 37 | Investigação de óbitos maternos: classificação do período de ocorrência do óbito (Campo 37 da DO) para mulheres de 10 a 49 anos, com lista dos casos a investigar |

Filtros: território (VIII GERES ou um dos 7 municípios) e ano.

## Como atualizar

Diferente do Painel de Arboviroses, este painel **não tem botão de atualização no navegador**: por pedido de quem o criou, as bases do SIM (óbitos) e do SINASC (nascidos vivos) continuam sendo enviadas ao Claude, que recalcula os indicadores, valida a qualidade dos dados e gera um novo `index.html`.

1. Envie ao Claude os arquivos atualizados do SIM (`DO*.DBF`) e do SINASC (`DN*.DBF`) do ano corrente (e do ano anterior, se ainda não fechado).
2. O Claude recalcula os indicadores, a série histórica e as demais seções, e gera um novo `index.html` autônomo (mesmo formato deste arquivo).
3. No GitHub, abra a pasta `painel-situacao-saude` deste repositório, clique em **Add file → Upload files**, envie o `index.html` novo e confirme em **Commit changes**. O site se atualiza em cerca de 1 minuto.

Os arquivos do SIM/SINASC são lidos só pelo Claude, em sessão isolada. O `index.html` gerado traz apenas contagens agregadas: nenhum nome, endereço, telefone, Cartão SUS ou outro dado identificável.

## Regras importantes

- **Anos fechados:** 2006 a 2024 estão congelados e não recebem atualização. Só o ano corrente (parcial) e o ano anterior (preliminar) são atualizados.
- **Mortalidade materna:** usa a causa básica registrada no SIM, independentemente do resultado da investigação.
- **Metas:** as metas mostradas são as do Card de Metas da Saúde de Pernambuco para 2026 (SEPLAG/NGR SES), por enquanto únicas para todos os territórios. Quando houver metas próprias da VIII GERES ou de cada município, elas substituem a estadual.
- **Campo 37:** considera óbitos não fetais de mulheres de 10 a 49 anos residentes. Campo 37 = 8 → descartado para materno; em branco ou = 9 → possível óbito materno a investigar; de 1 a 5 com causa básica fora do capítulo O → também a investigar.

## Cuidados

- O GitHub Pages é **público**: qualquer pessoa com o link vê o painel. Os dados são agregados, mas em municípios pequenos alguns recortes têm poucos casos.
- A versão no Claude não é mais atualizada; use sempre este endereço.
- O painel original no Claude é do tipo "Dashboard" (dados em banco próprio da plataforma) e não pode ser exportado automaticamente: esta cópia estática foi reconstruída à mão (HTML, CSS e JavaScript próprios, com os mesmos cálculos e o mesmo desenho dos gráficos), com os dados agregados do dia da publicação embutidos no arquivo.

## Histórico

### 26/11/2026
- Publicação no GitHub Pages, com os dados da versão do Claude (óbitos e nascimentos até 09/11/2026).
- Reconstrução fora do Claude: HTML/CSS/JS próprios (sem depender da plataforma do Claude), d3.js via CDN, link "← Portal da Vigilância em Saúde".
