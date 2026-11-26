# Portal da Vigilância em Saúde · VIII GERES

Página inicial da Coordenação de Vigilância em Saúde da VIII GERES (SES-PE, Petrolina – PE), com painéis de monitoramento, alertas, normas, calendário e contatos para os sete municípios da VIII Região de Saúde.

- **Endereço público:** https://hallmeberg.github.io/portal-vigilancia-viii/
- **Repositório:** https://github.com/hallmeberg/portal-vigilancia-viii
- **Arquivo principal:** `index.html` (página única; logos e fotos embutidos no próprio arquivo)
- **Cópia local:** `Desktop\Pagina de Apresentação V.S\Portal_Vigilancia_VIII_GERES.html`
- **Última atualização:** 26/11/2026

---

## 1. Seções da página

| Seção | Conteúdo | Onde editar no `index.html` |
|---|---|---|
| Topo | Logos SES-PE / Governo de PE e VIII GERES, faixa arco-íris, título, números-resumo e **Alerta em destaque** | Destaque = alerta com `destaque:true` em `ALERTAS` |
| Painéis | Cartões com botão **Acesse aqui** (abre na mesma aba), filtro por coordenação e busca | `PAINEIS` |
| Alertas e orientações | Faixa "Notifique aqui" (CIEVS-PE), lista de alertas/notas e atalhos para informes do CIEVS por agravo | `ALERTAS`, `INFORMES` |
| Portarias e normas | Normas de referência com link oficial | `NORMAS` |
| Calendário | Semana epidemiológica atual (calculada automaticamente) e próximos compromissos | `EVENTOS` |
| Meu município | Seletor dos 7 municípios: alertas, painéis e compromissos de cada um | `MUNICIPIOS` (usa `ALERTAS`, `PAINEIS`, `EVENTOS`) |
| Nossa equipe | Gerente, coordenadora de VS e as 5 coordenações com fotos | `COORD` (fotos em `FOTOS`) |
| Links úteis | CIEVS-PE, SINAN, DATASUS, SES-PE, Ministério da Saúde | `LINKS` |
| Rodapé / Contato | Endereço, e-mail e telefone | HTML do `<footer>` |

Todos os blocos editáveis estão marcados no código com `EDITE AQUI`.

## 2. Como atualizar

### Adicionar um alerta
No bloco `ALERTAS`, acrescente uma linha:

```js
{dt:"2026-12-05", tipo:"Alerta", c:"epi", fonte:"CIEVS-PE",
 t:"Título do alerta", mun:"Todos", url:"https://link-do-documento.pdf"},
```

- `dt`: data no formato AAAA-MM-DD (a lista é ordenada automaticamente)
- `tipo`: Alerta, Nota técnica, Nota informativa, Informe ou Orientação
- `c`: coordenação → `info`, `epi`, `pni`, `amb` ou `lab` (define a cor)
- `mun`: `"Todos"` ou uma lista, ex.: `["Petrolina","Afrânio"]`
- `destaque:true` coloca o alerta no quadro amarelo do topo
- `d:"..."`: resumo curto (aparece só no destaque)

### Adicionar ou liberar um painel
No bloco `PAINEIS`: para liberar um painel "Em construção", troque `st:"soon"` por `st:"on"` e preencha `url` e `at` (periodicidade).

### Adicionar compromisso no calendário
No bloco `EVENTOS`: `{dt:"2026-12-09", t:"Reunião da CIR", c:"info", mun:"Todos", ex:true}` — `ex:true` mostra a etiqueta "Data a confirmar". Compromissos com data passada somem sozinhos.

### Adicionar norma
No bloco `NORMAS`: `{t:"Descrição", m:"Portaria nº ..., de ...", url:"link oficial"}`.

### Publicar
Depois de editar, envie o `index.html` para a branch `main` do repositório. O GitHub Pages atualiza o site em cerca de 1 minuto.

## 3. Identidade visual

- **Base:** azul-marinho do Governo de Pernambuco `#122657`, fundo branco e faixa arco-íris
- **Cores das coordenações (iguais ao organograma):**
  - Informações Epidemiológicas `#e5323b` (vermelho)
  - Vigilância Epidemiológica `#2f6bff` (azul)
  - Imunização (PNI) `#6b3fd0` (roxo)
  - Vigilância Ambiental e Saúde do Trabalhador `#2fa84f` (verde)
  - Laboratório Regional `#e8701a` (laranja)
- **Destaque de alerta:** amarelo `#f5c400`
- **Fontes:** Archivo (títulos) e Inter (texto), via Google Fonts
- **Contornos:** `#b4bfd6`, 1,5 px, com sombra leve
- Funciona em computador e celular, nos temas claro e escuro.

## 4. Fontes do conteúdo

- **Alertas e notas:** portal CIEVS-PE — https://portalcievs.saude.pe.gov.br/ (consultado em 20/11/2026)
- **Notificação:** https://portalcievs.saude.pe.gov.br/notifique/formulario-dinamico
- **Painéis de vacinação:** https://www.gov.br/saude/pt-br/vacinacao/paineis-de-vacinacao
- **Normas:** Diário Oficial da União (in.gov.br), Biblioteca Virtual em Saúde (bvsms.saude.gov.br) e NormasBrasil (Portaria SES-PE nº 660/2022)
- **Equipe e fotos:** organograma da Vigilância em Saúde da VIII GERES (2026)

## 5. Pendências

- [ ] Confirmar datas da reunião do GT Regional de Arboviroses (25/11) e da CIR (09/12)
- [ ] Trocar o link da Portaria SES-PE nº 660/2022 pelo link oficial do Diário Oficial de PE
- [ ] Liberar o painel de Sazonalidade dos Vírus Respiratórios quando estiver pronto
- [x] Painel de Violência (VIVA) liberado em 26/11/2026
- [ ] Manter público o link do painel no Claude (ATT)

## 6. Histórico de alterações

### 26/11/2026
- **Painel de Violência Interpessoal e Autoprovocada publicado no GitHub Pages**, na pasta `painel-violencias/` (https://hallmeberg.github.io/portal-vigilancia-viii/painel-violencias/). O cartão "Violência Interpessoal e Autoprovocada" deixou de estar "Em construção" e passou a apontar para esse endereço. Detalhes em [painel-violencias/LEIAME.md](painel-violencias/LEIAME.md).
- O painel ganhou a identidade visual do Governo de Pernambuco (logos da SES-PE e da VIII GERES, faixa arco-íris, azul-marinho), o **mapa da VIII GERES** (taxa por 100 mil habitantes ou número de casos, clicável) e a aba **Alerta de reincidência**, que aponta por município de residência as pessoas com mais de uma tentativa de suicídio notificada.
- A lista com o **número da notificação no Sinan** de cada pessoa em alerta **não foi publicada** no site, que é aberto: por ser dado sensível de saúde (LGPD, art. 11), ela fica em uma planilha restrita, enviada pela VIII GERES às coordenações municipais. O painel mostra só as contagens.
- **Painel de Situação de Saúde publicado no GitHub Pages**, na pasta `painel-situacao-saude/` (https://hallmeberg.github.io/portal-vigilancia-viii/painel-situacao-saude/). O cartão do portal passou a apontar para esse endereço, que é agora o **link oficial** do painel. Detalhes e rotina de atualização em [painel-situacao-saude/LEIAME.md](painel-situacao-saude/LEIAME.md).
- Diferente do Painel de Arboviroses, este painel é do tipo "Dashboard" do Claude (dados em banco próprio da plataforma, não um arquivo exportável), então a cópia estática foi **reconstruída à mão**: mesmo HTML, mesmos cálculos e mesmos gráficos, porém com CSS e JavaScript próprios (sem os tokens de estilo e a API de dados exclusivos da plataforma do Claude) e com os dados agregados do dia embutidos no arquivo. A atualização continua sendo feita enviando as bases do SIM/SINASC ao Claude, que gera um novo `index.html` para subir ao GitHub — sem botão de atualização no navegador, por ser essa a rotina já combinada para este painel.
- **Painel de Arboviroses publicado no GitHub Pages**, na pasta `painel-arboviroses/` (https://hallmeberg.github.io/portal-vigilancia-viii/painel-arboviroses/). O cartão do portal passou a apontar para esse endereço, que é agora o **link oficial** do painel. Detalhes e rotina de atualização em [painel-arboviroses/LEIAME.md](painel-arboviroses/LEIAME.md).
- No GitHub, o botão **Atualizar base de dados** aparece só com `?atualizar` no fim do endereço. A publicação é **automática**: com a chave de acesso (token) de quem tem permissão de escrita, o painel grava o `index.html` e o `versao.json` direto no repositório. Como criar a chave está em [painel-arboviroses/LEIAME.md](painel-arboviroses/LEIAME.md).
- O painel ganhou o link **← Portal da Vigilância**, que só aparece quando aberto pelo GitHub Pages.

### 24/11/2026
- Incluído o **Painel de Alerta Climático** (https://hallmeberg.github.io/painel-clima-viii.io/): calor, umidade do ar, chuva e ventos nos 7 municípios, avisos do INMET, previsão de 3 dias e mensagem para o grupo regional no WhatsApp. Classificado em Vigilância Ambiental e Saúde do Trabalhador · CIEVS Regional, atualização a cada 15 min, com dados por município.
- Todos os botões **Acesse aqui** (painéis, alertas, normas e links) passam a abrir **na mesma aba**, em vez de abrir uma aba nova. Para voltar ao portal, usa-se a seta ← do navegador; o texto da seção Painéis explica isso.
- Avaliado e descartado: abrir os painéis dentro do próprio portal. Os painéis do Claude bloqueiam ser exibidos dentro de outro site (regra de segurança `frame-ancestors`). Copiar os painéis para o GitHub também foi descartado: o Painel de Arboviroses tem cerca de 1 MB com os dados embutidos, e o de Situação de Saúde é um painel do tipo "Data" do Claude, que não pode ser exportado como página.
- Decidido manter assim: os painéis no Claude não recebem botão "← Voltar ao portal".

### 20/11/2026
- Criação do portal com identidade visual do Governo de PE, a partir do organograma da Vigilância em Saúde.
- Painéis: Situação de Saúde, ATT e Arboviroses (disponíveis); Painéis de Vacinação do Ministério da Saúde (externo); Sazonalidade respiratória e Violência (em construção).
- Alertas reais do CIEVS-PE: calor e baixa umidade (alerta e nota técnica), hantavirose, NT nº 49/2026 e febre maculosa × dengue.
- Portarias e normas: LNC (GM/MS nº 11.211/2026 e nº 10.175/2026), lista estadual (SES-PE nº 660/2022), PQA-VS (GM/MS nº 6.878/2025), vigilância do óbito (nº 72/2010 e nº 1.119/2008), SIM/SINASC (SVS nº 116/2009) e Guia de Vigilância em Saúde.
- Novas seções: calendário com semana epidemiológica automática, "Meu município", fotos da equipe e contato no rodapé.
- Publicação no GitHub Pages (repositório `hallmeberg/portal-vigilancia-viii`).
- Aumento do contraste dos contornos de cartões, quadros, botões e etiquetas.
