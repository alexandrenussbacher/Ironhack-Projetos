<a name="topo"></a>
<h1 align="center"> 🧹 PROJETO 02 | Data Manipulation & Data Cleaning - Shark Attacks <br></br>
  <img src="https://ogimg.infoglobo.com.br/in/24555312-444-83e/FT631A/tubarao.jpg" alt="Shark"/>
</h>

## TABELA DE CONTEÚDO

- [PROPOSTA](#proposta)
- [PERGUNTAS](#perguntas)
- [ETAPAS IMPORTANTES](#etapas)
- [RESULTADOS](#EUA)
- [PROCESSO DE APRENDIZADO](#processo_de_aprendizado)
- [AUTOR](#autor)

<a name="proposta"></a>
## PROPOSTA

Fazer uma leitura e análise de um [Dataset do kaggle](https://www.kaggle.com/teajay/global-shark-attacks%20) sobre ataque de tubarões e formular pergunta(s) que possa(m) ser respondida(s) através da limpeza e manipulação dos dados (clique [aqui](https://ironhack.school/asset-v1:IRONHACK+DAFT+202007_SAO+type@asset+block@shark-attacks-project-v1.pdf) para saber mais).

<a name="perguntas"></a>
## PERGUNTAS

Antes de formular a(s) pergunta(s), foi preciso fazer uma análise dos dados para tentar entendê-los um pouco melhor. Após verificar que os Estados Unidos foi o país que mais teve casos de ataque (e que o índice de mortes é relativamente baixo), foi realizado uma análise específica em cima do mesmo com o foco nas seguintes questões:

* **Relação entre a ocorrência de casos e mortes ao longo dos anos nos Estados Unidos entre 1900 e 2018.**

* **Ocorrência de casos e mortes nos Estados Unidos para cada atividade que a vítima estava realizando, comparando os seguintes períodos: 1900 a 1999 e 2000 a 2018.**


<a name="etapas"></a>
## ETAPAS IMPORTANTES

1. Importar o Dataset e criar um backup.

2. Renomear as colunas e redefinir o DataFrame, utilizando apenas colunas que supostamente poderão ser utilizadas.

4. Verificar a quantidade de casos e mortes por país:

<table>
<tr><th>CASOS</th><th>MORTES</th></tr>
<tr><td>

|país                                   |casos      |
|:--------------------------------------|----------:|
| USA                                   |      2229 |
| AUSTRALIA                             |      1338 |
| SOUTH AFRICA                          |       579 |
| PAPUA NEW GUINEA                      |       134 |
| NEW ZEALAND                           |       128 |
| BRAZIL                                |       112 |

</td><td>

|país                          |mortes     |
|:-----------------------------|----------:|
| AUSTRALIA                    |       283 |
| USA                          |       186 |
| SOUTH AFRICA                 |       106 |
| PAPUA NEW GUINEA             |        56 |
| MEXICO                       |        43 |
| BRAZIL                       |        38 |

</td></tr> </table>

5. Criar um DataFrame para daods entre 2000 e 2018 e outro para dados entre 1900 e 1999.

6. Para ambos os DataFrame criados, verificar a quantidade de valores NaN (not a number) em cada coluna e removê-los das colunas "fatal" e "country" para que as colunas em interesse ("fatal", "country" e "year") tivessem apenas valores significantes.

Exemplo das informações do DataFrame de 2000 a 2018 após a remoção dos valores nulos das 2 colunas citadas (as 3 colunas em interesse passaram a ter a mesma quantidade de valores não-nulos):

<pre>&lt;class 'pandas.core.frame.DataFrame'&gt;
Int64Index: 1912 entries, 0 to 2078
Data columns (total 11 columns):
 #   Column       Non-Null Count  Dtype 
---  ------       --------------  ----- 
 0   case number  1912 non-null   object
 1   year         1912 non-null   int64 
 2   country      1912 non-null   object
 3   area         1836 non-null   object
 4   location     1839 non-null   object
 5   activity     1847 non-null   object
 6   sex          1823 non-null   object
 7   age          1444 non-null   object
 8   fatal        1912 non-null   object
 9   time         1408 non-null   object
 10  morte        1912 non-null   int64 
dtypes: int64(2), object(9)
memory usage: 259.2+ KB
</pre>

7. Comparar informações de casos e mortes em determinados países:

|    | country                     |   num_casos_2000a2018 |   num_mortes_2000a2018 |   prop_mortes_2000a2018 |   num_casos_1900a1999 |   num_mortes_1900a1999 |   prop_mortes_1900a1999 |
|---:|:----------------------------|----------------------:|-----------------------:|------------------------:|----------------------:|-----------------------:|------------------------:|
|  0 | USA                         |                   951 |                     20 |               0.0210305 |                   944 |                    112 |                0.118644 |
|  1 | AUSTRALIA                   |                   362 |                     33 |               0.0911602 |                   701 |                    186 |                0.265335 |
|  2 | SOUTH AFRICA                |                   124 |                     22 |               0.177419  |                   363 |                     65 |                0.179063 |
|  4 | BRAZIL                      |                    49 |                     18 |               0.367347  |                    49 |                     17 |                0.346939 |
| 15 | PAPUA NEW GUINEA            |                     9 |                      3 |               0.333333  |                   116 |                     51 |                0.439655 |

> Apesar do número de casos nos Estados Unidos ser muito alto se comparado com os outros países, o índice de mortes se destaca por ser relativamente baixo.

<a name="EUA"></a>
## FOCO NOS ESTADOS UNIDOS (RESPONDENDO AS PERGUNTAS)

* **Relação entre a ocorrência de casos e mortes ao longo dos anos nos Estados Unidos entre 1900 e 2018.**

DataFrame com a relação de casos e mortes por ano nos Estados Unidos:

|     |   year |   casos |   mortes |   prop_mortes |
|----:|-------:|--------:|---------:|--------------:|
|   0 |   1900 |       4 |        0 |     0         |
|   1 |   1901 |       1 |        0 |     0         |
|   2 |   1902 |       3 |        1 |     0.333333  |
|   3 |   1903 |       2 |        1 |     0.5       |
|   4 |   1904 |       3 |        2 |     0.666667  |
|     |        |         |          |               |
| 112 |   2015 |      66 |        1 |     0.0151515 |
| 113 |   2016 |      59 |        0 |     0         |
| 114 |   2017 |      58 |        0 |     0         |
| 115 |   2018 |      10 |        0 |     0         |

Correlação entre as variáveis do DataFrame acima:

|             |       year |      casos |     mortes |   prop_mortes |
|:------------|-----------:|-----------:|-----------:|--------------:|
| year        |  1         |  0.792549  | -0.0656931 |     -0.527312 |
| casos       |  0.792549  |  1         |  0.0534203 |     -0.380861 |
| mortes      | -0.0656931 |  0.0534203 |  1         |      0.511903 |
| prop_mortes | -0.527312  | -0.380861  |  0.511903  |      1        |

> **Conclusão:**

> Com base nos dados acima, podemos ver que há uma tendência no aumento do número de casos com o passar dos anos. Os números do primeiro DataFrame e a alta correlação positiva entre anos e casos nos perimite chegar a essa conclusão. Isso mostra que cada vez mais casos são registrados, muito provavelmente pelo avanço das ferramentas tecnológicas.

> Podemos ver também que mesmo com aumento do número de casos, o número de mortes se mantém baixo ao longo dos anos.

* **Ocorrência de casos e mortes nos Estados Unidos para cada atividade que a vítima estava realizando, comparando os seguintes períodos: 1900-1999 e 2000-2018.**

|    | atividade     |   casos_2000-2018 |   mortes_2000-2018 |   prop_mortes_2000-2018 |   casos_1900-1999 |   mortes_1900-1999 |   prop_mortes_1900-1999 |
|---:|:--------------|------------------:|-------------------:|------------------------:|------------------:|-------------------:|------------------------:|
|  0 | Surfing       |               347 |                  3 |              0.00864553 |               185 |                  3 |               0.0162162 |
|  1 | Swimming      |               153 |                  7 |              0.0457516  |               165 |                 38 |               0.230303  |
|  2 | Snorkeling    |                20 |                  2 |              0.1        |                 7 |                  2 |               0.285714  |
|  3 | Body boarding |                16 |                  1 |              0.0625     |                 7 |                  2 |               0.285714  |
|  4 | Diving        |                 6 |                  1 |              0.166667   |                11 |                  2 |               0.181818  |

> **Conclusão:**

> Com base nos dados do DataFrame acima, podemos ver que apesar do número de casos em que a vítima estava surfando é maior do que nadando (principalmente entre 2000 e 2018), o índice de mortes das vítimas nadando é muito maior do que surfando. Por exemplo, entre 1900 e 1999, o índice de mortes de vítimas surfando é de 1,6%, enquanto o de vítimas nadando é de 23% (esta comparação é relevante porque o número de casos nessa época é significativo e parecido em ambas as atividades).

> Além disso, se compararmos os casos de vítimas nadando nos dois períodos, podemos ver que o índice de mortes entre 1900 e 1999 é de 23%, enquanto entre 2000 e 2018 é de apenas 4,5% (novamente a comparação é relevante porque o número de casos nas duas épocas é significativo e parecido).

> Por fim, podemos ver também que em apenas 19 anos (entre 2000 e 2018) o número de casos de vítimas surfando é quase o dobro do que em 100 anos (entre 1900 e 1999), comprovando a conclusão da primeira pergunta de que com o passar dos anos houve cada vez mais casos registrados. 

<a name="processo_de_aprendizado"></a>
## PROCESSO DE APRENDIZADO

### Habilidades aplicadas:

- [x] Pandas
- [x] Numpy
- [x] Manipulação de dados
- [x] Limpeza de dados

### Desafios:

* Necessidade de utilizar ferramentas como estatística e visualização de dados.

* Tempo curto para a realização do projeto.

<a name="autor"></a>
## AUTOR:

Alexandre Nussbacher

- [SUBIR AO TOPO](#topo)
