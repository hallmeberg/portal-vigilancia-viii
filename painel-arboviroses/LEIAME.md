# Painel de Arboviroses · VIII GERES

Painel de dengue, chikungunya e zika dos 7 municípios da VIII Região de Saúde de Pernambuco, de apoio ao Grupo Técnico Regional de Enfrentamento às Arboviroses.

- **Endereço público (link oficial):** https://hallmeberg.github.io/portal-vigilancia-viii/painel-arboviroses/
- **Endereço para atualizar:** https://hallmeberg.github.io/portal-vigilancia-viii/painel-arboviroses/?atualizar
- **Arquivo:** `index.html` (página única, com os dados agregados embutidos, cerca de 2 MB)
- **Publicado no GitHub em:** 26/11/2026, a partir da versão do Claude (https://claude.ai/artifact/RrwD9312gCyukVExDtoCwh), que deixa de ser o link oficial

## O que o painel mostra

| Página | Conteúdo |
|---|---|
| Visão geral | Indicadores do ano, curva epidêmica por semana de início dos sintomas (ano escolhido e dois anteriores), mapa de incidência e tabela por município |
| Situação atual | Sinalização das 4 semanas consolidadas mais recentes, diagrama de controle (10 anos anteriores, com e sem anos epidêmicos) e mapa de calor semanal |
| Perfil dos casos | Pirâmide de faixa etária e sexo, raça/cor e gestantes |
| Gravidade e laboratório | Sinais de alarme, dengue grave, hospitalização, óbitos, critério de confirmação, classificação e sorotipos |
| Qualidade dos dados | Encerramento oportuno, fichas em aberto, inconsistências, duplicidades e residentes de fora notificados na região |
| Notas e método | Definições, regras de tratamento das bases e rotina de atualização |

Filtros: agravo, ano (início dos sintomas) e município de residência. As tabelas têm botão **Baixar CSV**.

## Como atualizar (quinzenal ou mensal)

1. Exporte o **ano corrente** de dengue e chikungunya (Sinan Online, arquivos DENGON e CHIKON) e de zika (Sinan Net, DBF ou planilha Excel convertida), por **residência**, **Regional VIII**, com chave fonética e data de nascimento.
2. Abra o endereço para atualizar (com `?atualizar`) e clique em **Atualizar base de dados**.
3. Escolha os arquivos e clique em **Ler arquivos**. Confira os totais da VIII GERES (antes → depois).
4. Clique em **Baixar index.html atualizado**.
5. No GitHub, abra a pasta `painel-arboviroses` deste repositório, clique em **Add file → Upload files**, envie o `index.html` baixado e confirme em **Commit changes**. O site se atualiza em cerca de 1 minuto.

Os arquivos do Sinan são lidos só no computador de quem atualiza. O `index.html` gerado traz apenas contagens agregadas: nenhum nome, endereço, telefone ou Cartão SUS.

## Regras importantes

- **Anos fechados:** 2016 a 2025 estão congelados. Arquivos desses anos são ignorados, com aviso.
- **Virada do ano:** enquanto 2026 não for encerrado, envie os arquivos de 2026 junto com os de 2027. Quando 2026 for encerrado, o limite de anos fechados precisa passar para 2026 (ajuste feito no código, campo `fechado_ate`).
- **População:** se faltar a população de um ano, o painel pede os 7 valores antes de continuar e os grava no arquivo gerado.
- **Caso provável:** todo notificado, exceto descartado. Incidência por 100 mil habitantes, com a população da tabela da VIII GERES.

## Cuidados

- O GitHub Pages é **público**: qualquer pessoa com o link vê o painel. Os dados são agregados, mas em municípios pequenos alguns recortes têm 1 ou 2 casos.
- Quem abre o endereço com `?atualizar` consegue gerar um arquivo, mas só quem tem acesso ao repositório consegue publicá-lo.
- A versão no Claude não é mais atualizada; use sempre este endereço.

## Histórico

### 26/11/2026
- Publicação no GitHub Pages, com os dados da versão do Claude (notificações até 10/11/2026).
- Adaptações para fora do Claude: botão de atualização por `?atualizar` gerando o `index.html`, CSV pelo download do navegador e link "← Portal da Vigilância".
