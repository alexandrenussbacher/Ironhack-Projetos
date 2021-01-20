<a name="topo"></a>
<h1 align="center"> 🔎 PROJETO 03 | Mineração e visualização de dados - Campeonato Brasileiro 2020 (Série A) <br></br>
  <img src="https://github.com/alexandrenussbacher/Ironhack-Projetos/blob/main/Projeto%2003%20-%20Campeonato%20Brasileiro%202020%20(S%C3%A9rie%20A)/imagens/Brasileiro_2020.png" alt="Brasileiro"/>
</h>

## TABELA DE CONTEÚDO

- [PROPOSTA](#proposta)
- [ETAPAS IMPORTANTES](#etapas)
- [PROCESSO DE APRENDIZADO](#processo)
- [AUTOR](#autor)

<a name="proposta"></a>
## PROPOSTA

* [**Parte 1:**](https://ironhack.school/asset-v1:IRONHACK+DAFT+202007_SAO+type@asset+block@web-scraping-project.pdf) Criar uma base de dados a partir de Web Scraping e/ou API.

* [**Parte 2:**](https://ironhack.school/asset-v1:IRONHACK+DAFT+202007_SAO+type@asset+block@data-visualization-project.pdf) Criar um dashboard e/ou uma história no Tableau com os insights através da visualização dos dados obtidos.

### Objetivo específico:

> **Analisar a performance dos jogadores que atuam na Série A do Campeonato Brasileiro de 2020.**

<a name="etapas"></a>
## ETAPAS IMPORTANTES

<ol type="1">
<li> Criar duas funções, uma para os scouts defensivos e outra para os scouts ofensivos. </li> <p></p>

<li> Usar o selenium dentro das funções:
  
   - Iniciar a navegação da [url](https://1xbet.whoscored.com/Regions/31/Tournaments/95/Seasons/8158/Stages/18472/PlayerStatistics/Brazil-Brasileir%C3%A3o-2020);
   
   - Criar um Dataframe vázio;
   
   - Criar um loop para clicar nos botões necessários, aguardar o tempo mínimo para mudar de página, realizar o Web Scraping da página momentânea e adicionar o conteúdo ao Dataframe criado. </li> <p></p>

<li> Unir os dois Dataframe criados. </li> <p></p>

<li> Limpar e manipular os dados:
  
  - Criar 3 funções com expressões regulares para separar a coluna que contém informações do nome, time e idade do jogador;
  
  - Criar novas colunas, aplicando as funções criadas;
  
  - Mudar o nome e ordem das colunas;
  
  - Substituir os valores "-" por 0. </li> <p></p>
  
<li> Exportar o Dataframe final para o SQL (conectando com o Python) e arquivo csv. </li> <p></p>
  
</ol>

## RESULTADO

[TABLEAU PUBLIC]()

<a name="processo"></a>
## PROCESSO DE APRENDIZADO

### Habilidades aplicadas:

- [x] Web Scraping (Selenium)
- [x] Pandas
- [x] Numpy
- [x] Limpeza de Dados
- [x] Manipulação de Dados
- [x] Expressões Regulares
- [x] Conexão do Python com PostgreSQL
- [x] Tableau

### Melhorias:

* Otimizar o código através de classes/funções.

* Além do Tableau, usar as bibliotecas Matplotlib e Seaborn do Python para a visualização dos dados.

<a name="autor"></a>
## AUTOR:

Alexandre Nussbacher

- [SUBIR AO TOPO](#topo)
