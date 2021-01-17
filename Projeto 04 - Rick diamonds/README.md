<a name="topo"></a>
<h1 align="center"> 📈 PROJETO 04 | Regressão Linear - Rick diamonds <br></br>
  <img width="300" src="https://github.com/alexandrenussbacher/Ironhack-Projetos/blob/main/Projeto%2004%20-%20Rick%20diamonds/imagens/diamante.jpg" alt="Shark"/>
</h>

## TABELA DE CONTEÚDO

- [PROPOSTA](#proposta)
- [ETAPAS IMPORTANTES](#etapas)
- [PROCESSO DE APRENDIZADO](#processo_de_aprendizado)
- [AUTOR](#autor)

<a name="proposta"></a>
## PROPOSTA

Criar um modelo de regressão linear para prever o preço dos [diamantes do Rick](https://github.com/alexandrenussbacher/Ironhack-Projetos/blob/main/Projeto%2004%20-%20Rick%20diamonds/data/Rick's%20diamonds.csv), com base em um [Dataset histórico](https://github.com/alexandrenussbacher/Ironhack-Projetos/blob/main/Projeto%2004%20-%20Rick%20diamonds/data/Histoical%20Dataset.csv).

### OBJETIVO

**Os preços previstos devem ter um RMSE (raiz quadrada média do erro) menor que 900.**

> clique [aqui](https://ironhack.school/asset-v1:IRONHACK+DAFT+202007_SAO+type@asset+block@linear-regression-challenge.pdf) para saber mais.

<a name="etapas"></a>
## ETAPAS IMPORTANTES

<ol type="1">

<li> Importar os Datasets e criar um backup. </li> <p></p>

<li> Criar uma baseline para prever o preço dos diamantes do Rick através da média dos preços dos diamantes na base de dados histórica. </li> <p></p>

<li> Explorar e limpar o Dataset histórico:
 
 - checar valores nulos.
 
 - converter variáveis categóricas em numéricas.
 
 - analisar valores zerados das colunas x, y e z e estimar valores zerados de z, dropando as linhas em que o cálculo nao fosse possivel. </li> <p></p>
 
 <li> Criar o primeiro modelo com base em todas as colunas. <p></p>
  
>**RMSE**=1287.6253018160428

>**R²**=90.81% </li> <p></p>

<li> Criar o segundo modelo com base no logaritmo das colunas (sem considerar x, y e z, pois possuem valores zerados no Dataset do Rick). <p></p>
  
>**RMSE**=890.9525826770072

>**R²**=98.21% </li> <p></p>

</ol>

* [link](https://daft-oct2020-rick-diamonds.herokuapp.com/) para anexar arquivo csv e verificar o RMSE.

<a name="processo_de_aprendizado"></a>
## PROCESSO DE APRENDIZADO

### Habilidades aplicadas:

- [x] Pandas
- [x] Numpy
- [x] Matplotlib
- [x] Seaborn
- [x] Regressão Linear

### Melhorias:

* Explorar mais o Dataset histórico com as bibliotecas Matplotlib e Seaborn.

* Diminuir o RMSE.

<a name="autor"></a>
## AUTOR:

Alexandre Nussbacher

- [SUBIR AO TOPO](#topo)
