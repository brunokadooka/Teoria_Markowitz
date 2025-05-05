# 📘 Teoria de Markowitz

## 📂 1. Introdução

Este trabalho integra o portfólio de análise de dados e apresenta um projeto de análise descritiva e explanatória com base em uma teoria do mercado de investimentos. **Não se trata de recomendação de investimento** nos ativos mencionados, mas sim de um estudo de caso com fins exclusivamente acadêmicos e de portfólio.

A motivação partiu de um vídeo da [T2 Educação](https://www.youtube.com/watch?v=i5WCpU07_yo&) que aborda a Fronteira Eficiente, explicando como calculá-la e como é utilizada. A partir disso, surgiu o interesse em aplicar a teoria à carteira do IBOV, uma vez que ela possui ponderações sobre os ativos, o que levanta algumas questões relevantes, como:

- Qual é o risco do IBOV?  
- Qual é a rentabilidade do IBOV?  
- Onde a carteira do IBOV se posiciona na Fronteira Eficiente?  
- Existe uma configuração "melhor" para o IBOV?

Essas perguntas orientam o estudo e contribuem para a compreensão da aplicação prática da teoria em carteiras de ativos. O estudo pode ser replicado futuramente para outros índices ou fundos de investimento, auxiliando na avaliação de alternativas de alocação. Reforçando: **este projeto não tem caráter de recomendação de investimentos.**

Antes de iniciar a análise, serão resumidos os principais tópicos abordados, como: o que é a Teoria de Markowitz, uma explicação sobre o IBOV e uma visão geral do projeto.

### 📌 1.1. Teoria de Markowitz

A Teoria de Markowitz, também conhecida como Teoria Moderna do Portfólio, é um modelo de análise de risco e retorno de uma carteira de ativos. Com base nessa teoria, é possível ponderar os ativos de forma a encontrar a menor combinação de risco com a maior rentabilidade. Cada ponderação, ao ser testada, gera um ponto no gráfico de retorno x risco. A disposição desses pontos forma a chamada Fronteira Eficiente. Assim, é possível identificar carteiras com menor risco e melhor rentabilidade.

Essa teoria pode beneficiar tanto investidores equilibrados quanto arrojados. O investidor equilibrado busca boa rentabilidade com menor risco. Por exemplo: entre uma Carteira A com 10% de risco e 12% de retorno, e uma Carteira B com o mesmo risco e 15% de retorno, a Carteira B é preferível. Já entre uma Carteira A com 10% de risco e 12% de retorno e uma Carteira B com 6% de risco e 8% de retorno, é possível usar o cálculo de retorno por unidade de risco. Nesse caso, a Carteira A oferece 1,2% de retorno por 1% de risco, enquanto a B oferece 1,33%, sendo uma escolha mais equilibrada.

Por outro lado, o investidor arrojado prioriza a rentabilidade. Mesmo diante de maior risco, o retorno esperado é o fator decisivo. No exemplo anterior, com 12% de retorno contra 8%, a Carteira A seria a escolhida.

Entre os princípios da teoria, destaca-se a importância da correlação ou covariância entre os ativos. Há divergências quanto ao uso de uma ou outra: a correlação é mais fácil de explicar e é uma forma padronizada da covariância, enquanto esta última é a medida utilizada nos cálculos originais de Markowitz. Neste estudo, será analisado se há diferença significativa entre as abordagens. O vídeo de referência utiliza a covariância; portanto, se não houver diferença, será utilizada a correlação, por ser mais acessível conceitualmente.

Esse princípio é importante porque, caso uma carteira esteja altamente correlacionada ou covariada, o risco **pode** ser maior. No entanto, é necessário diferenciar: uma correlação **positiva** forte entre ativos aumenta o risco, pois os ativos se comportam de maneira semelhante. Já uma correlação **negativa** pode ajudar a reduzir o risco, sendo desejável. Assim, o problema está na correlação positiva elevada. A aplicação desse princípio busca evitar uma ponderação excessiva em ativos com comportamentos muito semelhantes, promovendo melhor diversificação.

A fronteira eficiente e a relação entre risco e retorno também são pilares da teoria. Embora existam diferentes formas de calcular essa relação, a ideia central é que a escolha de uma carteira deve ser racional, com base na fronteira e na relação risco-retorno.

### 📌 1.2. Carteira do IBOV

A carteira do IBOV serve como um índice geral das ações brasileiras. É o principal índice da B3 e referência para o mercado de ações.

Os ativos deste índice devem atender a alguns critérios:

- Não podem ter ações com cotação em centavos (abaixo de R$ 1,00). Caso o ativo atinja esse valor, é estabelecido um prazo para recuperação.  
- Apenas ações do tipo preferenciais (PN) e ordinárias (ON) são incluídas — ou seja, são excluídos FIIs, BDRs, Units, ETFs, entre outros.  
- Os ativos não podem ter baixa liquidez.  
- Não podem estar em recuperação judicial ou apresentar graves problemas financeiros.  
- Devem ter boa presença no mercado (frequência mínima de negociação) e alto volume financeiro.

O índice é rebalanceado a cada quatro meses, ou seja, quatro vezes ao ano (janeiro, maio, setembro e janeiro do ano seguinte). Mais à frente no estudo, essa característica será considerada um desafio. No entanto, esse rebalanceamento é positivo, pois garante a inclusão contínua de empresas relevantes como referência de mercado.

Antes de iniciar o estudo, será realizada uma análise específica sobre a composição do IBOV. O objetivo é examinar a composição atualizada do índice e entender como cada ativo se comporta dentro dele. Esta análise será apresentada na seção 2.

### 📌 1.3. Sobre o Projeto

A carteira do IBOV se alinha bem com a Teoria de Markowitz, por ser composta por diversos ativos com ponderações definidas. Isso permite avaliar qual seria a melhor composição da carteira para gerar maior rentabilidade, buscar o equilíbrio entre retorno e risco e identificar filtros adicionais que podem ser aplicados. Por exemplo, é possível calcular a correlação entre os ativos e filtrar aqueles altamente correlacionados, promovendo maior diversificação.

O projeto propõe estudar a Fronteira Eficiente do IBOV, sugerir melhorias nos critérios de composição da carteira e comparar indicadores de retorno e risco entre diferentes configurações. Além disso, alguns desafios relevantes devem ser considerados. Um dos principais é o fato de que a composição do IBOV é rebalanceada a cada quatro meses, o que dificulta a análise de longos períodos. Isso ocorre porque os ativos podem variar em peso ou mesmo serem substituídos — com a entrada de novos ativos ou a exclusão de outros. 

Um exemplo claro é o período entre 2000 e 2010, no qual o índice incluía empresas do grupo EBX, de Eike Batista, com forte influência no mercado. Um destaque foi a OGXP3 (mineradora), que chegou a representar cerca de 5% do índice [(Fonte: InfoMoney)](https://www.infomoney.com.br/mercados/como-o-investidor-deve-interpretar-as-mudancas-na-composicao-do-ibovespa). Atualmente, esse percentual corresponderia à 4ª maior participação, conforme será analisado na seção 2. Portanto, realizar uma análise contínua da carteira ao longo dos anos é uma tarefa complexa, mas serão utilizadas hipóteses e métodos estatísticos alternativos para tentar estimar e compreender as variações da composição histórica.

Este trabalho consiste em um estudo de caso e, por isso, é fundamental reforçar que **não se trata de recomendação de investimento**. Qualquer estudo envolvendo finanças deve deixar isso claro. O objetivo é exclusivamente demonstrar habilidades analíticas e o uso de ferramentas como Excel, Power BI e bibliotecas do Python.

Este projeto está estruturado em três etapas principais:

**1ª Etapa — Coleta e Preparação dos Dados**  
A primeira fase consiste na obtenção de dados brutos, por meio de *web scraping* e do download de informações financeiras utilizando bibliotecas Python, como o *yfinance*. Essa etapa está documentada no arquivo **"1.Criando_Dados.ipynb"**, desenvolvido em Python.  

**2ª Etapa — Análises Exploratórias e Descritivas**  
Após a coleta, foram realizadas análises exploratórias e descritivas da composição do índice Ibovespa, com aplicação de técnicas de *feature engineering*, comparações entre carteiras e outras análises relevantes. Essa etapa é abordada em dois formatos:  
- O arquivo **"2.Analises.ipynb"** demonstra as análises feitas em Python.  
- O arquivo **"Analises.xlsx"** ilustra a mesma etapa com o uso de Excel. Nele, as guias em **azul** representam consultas ou dados brutos, enquanto as guias em **verde** contêm gráficos e análises. Destaca-se a guia **"Carteiras_IBOV"**, que utiliza tabelas dinâmicas e está associada à análise da terceira etapa.  
- Adicionalmente, o arquivo **"Relatorio.pbix"** (Power BI) apresenta um dashboard com a composição atual da carteira do Ibovespa, com foco na visualização informativa dos dados.

**3ª Etapa — Aplicação da Teoria de Markowitz**  
Nesta fase final, foi aplicada a Teoria de Markowitz para otimizar a carteira do Ibovespa, com foco em maximizar o retorno ajustado ao risco. Foram realizados os cálculos de rentabilidade e risco dos ativos e da carteira como um todo, geração de gráficos visuais das carteiras testadas e utilização de busca bayesiana para encontrar composições mais eficientes. Todas essas análises estão documentadas no arquivo **"3.Teoria.ipynb"**, com comentários detalhados sobre as decisões e observações feitas ao longo do processo.

**Metodologia**

A metodologia de pesquisa adotada neste projeto foi o **CRISP-DM (Cross Industry Standard Process for Data Mining)**. Como mencionado anteriormente, o projeto foi estruturado em três grandes etapas, enquanto o CRISP-DM é composto por seis fases. Acontece que nem todas as etapas do CRISP-DM foram aplicadas integralmente — por exemplo, a fase de *Deployment* não foi utilizada. Por outro lado, algumas fases foram agrupadas; como é o caso de **Entendimento do Negócio** e **Entendimento dos Dados**, que foram consolidadas em uma única etapa inicial.

Na seção de **Desenvolvimento**, explicaremos detalhadamente como cada fase do CRISP-DM foi abordada e a qual arquivo da estrutura do projeto cada uma corresponde.


## 📂 2. Desenvolvimento

Nesta seção, vamos discutir como o projeto foi desenvolvido. Como mencionado anteriormente, a pesquisa seguiu a metodologia **CRISP-DM**, portanto, cada subtítulo desta seção descreve uma das etapas dessa metodologia, explicando como ela se relaciona com os arquivos e a estrutura do projeto apresentados na Introdução. Antes de detalhar as etapas do CRISP-DM, é importante explicar como os **dados brutos** foram adquiridos para o estudo.

### 📌 2.1. Dados Brutos

Para coletar os dados, não basta apenas obter a cotação do IBOV. Afinal, o índice é composto por diversos ativos, cada um com um peso específico em sua formação. Este estudo visa encontrar uma melhor composição desses pesos e ativos, com o objetivo de tornar o índice mais rentável ou com uma distribuição risco-retorno mais eficiente. No site da B3, é possível encontrar, de forma atualizada, a composição da carteira do Ibovespa — **válida até 01/04/2025**. Este é o primeiro passo: identificar quais ativos fazem parte do IBOV. No entanto, esse documento fornece apenas o nome do ativo e seu respectivo peso de participação, o que é relevante para a análise, mas não suficiente para entender o funcionamento do índice como um todo. Para compreender melhor os ativos, é necessário obter informações adicionais como Setor, Segmento, Tamanho de mercado, Fundação da empresa e Tempo desde o IPO.

Essas informações são úteis para investigar que tipo de ativos o Ibovespa tende a priorizar ou atribuir maior peso. Como esses dados não estão organizados de forma acessível no site da B3, foi necessário realizar **web scraping** no site [Investidor10](https://investidor10.com.br/). Antes de iniciar o scraping, consultamos o arquivo [robots.txt](https://investidor10.com.br/robots.txt). Vale lembrar que esse arquivo não representa uma regra legal, mas indica quais partes do site estão mais ou menos propensas à coleta automatizada por bots. Selecionamos para raspagem apenas os **87 ativos** que compunham o Ibovespa até 01/04. As informações coletadas foram consolidadas no arquivo `scraping_ativos.csv`, localizado na pasta `data`.

Para o scraping, utilizamos a biblioteca `Selenium`, já que o site possui elementos dinâmicos como anúncios e filtros que exigem interação. Bibliotecas como `requests` e `BeautifulSoup` são mais indicadas para páginas estáticas e não conseguem lidar com interações via JavaScript. Abaixo está um diagrama representando esse processo:

<p align="center">
  <img src="https://github.com/user-attachments/assets/8ba3ba4e-4b68-48eb-ae6c-1703f9a773d8" alt="Diagrama do dataset scraping_ativos.csv" />
</p>
<p align="center">
  <strong>Imagem 1: Diagrama da criação do dataset scraping_ativos.csv.</strong>
</p>

Agora que temos os dados brutos da composição do Ibovespa, podemos estudar as características que compõem este índice. É verdade que na introdução já comentamos alguns filtros que há para os ativos entrarem no índice, mas é preciso saber como o índice distribui esses pesos de participação. Mas ainda não acabou a parte de puxar os dados brutos, é preciso ter o principal: os dados de cotação dos ativos.

A cotação dos ativos são os dados mais importantes neste quesito. Basicamente, os dados de composição (que comentamos acima) servem apenas para entender o negócio, no caso, entender a composição do índice Ibovespa. Mas os dados que vão ser usados de fato são as cotações dos ativos. Não estamos interessados no percentual de ganho ou perda do IBOV e sim em como chegou neste percentual. Para isso, leva-se em conta o percentual do ativo ponderado pelo seu peso no IBOV.É por este motivo que, ao puxar os dados dos ativos, podemos calcular de forma manual como o índice IBOV se comportou ao longo dos anos — claro, de maneira aproximada, visto que o IBOV sempre tem mudanças.

Para a cotação dos ativos, foi simples de puxar. Utilizando a biblioteca `yfinance`, podemos fazer o download da cotação dos ativos. Passamos por parâmetro que queremos os dados diários e do máximo de período que a biblioteca disponibiliza do ativo. O dataset que é baixado é de *candles*, com variáveis do tipo Date, Abertura, Máxima, Mínima e Fechamento. Tem a variável `Adj Close`, que leva em conta os dividendos, Volume e outras variáveis. Neste caso, vamos utilizar apenas a variável Fechamento para calcular o percentual e, claro, a variável Date para verificar de qual dia é a cotação. Este foi um dos vários tratamentos realizados, e assim temos o arquivo `cotacao_ativos.csv`, também localizado na pasta `data`.


<p align="center">
  <img src="https://github.com/user-attachments/assets/ea6ce0d0-487e-4195-9100-dc0a8b17d16e" alt="Diagrama do dataset cotacao_ativos.csv" />
</p>
<p align="center">
  <strong>Imagem 2: Diagrama da criação do dataset cotacao_ativos.csv.</strong>
</p>

Todo este processo de puxar os dados, fazer web scraping, uso das bibliotecas `yfinance`, `Pandas`, `Selenium`, tratamento e limpeza dos dados (limpar valores NaN, conversão de tipos de dados), e claro, habilidades envolvendo a linguagem python como funções, laços de repetição, todo o funcionamento do diagrama, está no arquivo **"1.Criando_Dados.ipynb"**. Ali, as decisões e os pensamentos de como foi implementado o código estão comentados tanto no código como em markdown. Lembrando que, na estruturação do projeto conforme dividido em 3 etapas, esta é a primeira etapa: a exportação e arranjo dos dados brutos.

### 📌 2.2. Entendimento dos Negócios

Para entender melhor a composição do IBOV, embora já existam variáveis que ajudam neste momento, a realização de *feature engineering* contribui para simplificar ainda mais as informações.Por exemplo, na imagem 3 temos o dataset `scraping_ativos.csv` da forma como foi extraído e devidamente tratado. Encontramos informações que, em um primeiro momento, parecem interessantes, mas que ainda podem ser aprimoradas.

<p align="center">
  <img src="https://github.com/user-attachments/assets/52f86c9f-8517-46c0-aa62-61ad6fc53b10" alt="Dataframe do arquivo scraping_ativos.csv sem alterações" />
</p>
<p align="center">
  <strong>Imagem 3: Dataframe do arquivo scraping_ativos.csv sem alterações.</strong>
</p>


Veja o caso da variável `Valor de Mercado`. De fato, ela representa o tamanho do ativo conforme o mercado atribui (Valor de Mercado = Preço do Ativo * Número Total de Ações). Essa variável tenta nos dizer o tamanho da empresa — e faz isso de maneira simples. No entanto, queremos saber não apenas o tamanho da empresa isoladamente, mas também em relação aos outros ativos da carteira.

Para isso, existe uma classificação que categoriza as empresas como `Small Caps`, `Mid Caps` ou `Large Caps`. Para definir em qual classificação o ativo se enquadra, temos dois caminhos: seguir a convenção padrão adotada por investidores e analistas, ou realizar uma análise univariada da variável. Neste caso, nada melhor que uma **análise univariada**.

No arquivo **Analise.xlsx** (Excel), temos 4 planilhas com o objetivo de realizar análises univariadas. A planilha `scraping_ativos` é uma consulta feita por meio do Power Query para importar as informações do dataset `scraping_ativos.csv`. Já comentamos anteriormente, mas vale relembrar: guias da planilha em azul indicam consultas de datasets, enquanto as guias em verde representam análises. Pode-se notar que há três análises feitas para as seguintes variáveis: `Tamanho de Mercado`, `Idade da Empresa` e `Tempo de IPO`. Para não deixar o texto muito longo, vamos comentar apenas a variável `Tamanho de Mercado`, visto que as decisões tomadas se replicam da mesma forma para as outras variáveis — especialmente no que diz respeito à criação de variáveis categóricas e à simplificação das informações.

<p align="center">
  <img src="https://github.com/user-attachments/assets/a9b2f69d-416e-4f8a-9fbb-33f6ba32bc98" alt="Analise Univariada da variavel Tamanho de Mercado" />
</p>
<p align="center">
  <strong>Imagem 4: Analise Univariada da variavel Tamanho de Mercado.</strong>
</p>

Temos uma tabela com as medidas descritivas, um histograma e dois boxplot's, o segundo boxplot tem como objetivo limitar e verificar a variabilidade e algumas medidas estatísticas. 

Ao observar a média e a mediana, nota-se uma grande diferença entre elas. Essa diferença é visível também no boxplot, onde um "X" marca a média e a linha dentro da "caixa" representa a mediana. Essa discrepância indica que valores discrepantes têm forte influência sobre essa variável. Além disso, observa-se a presença de *outliers* no gráfico.

A variabilidade é bastante elevada. Por exemplo, pela amplitude (ponto máximo - ponto mínimo) é possível verificar que a variação atinge 426 bilhões de reais. No mercado de ações brasileiro, essa é uma diferença colossal. Isso indica a presença de empresas com apenas alguns milhões e outras que tem centenas de bilhões, ou seja, o índice não filtra apenas empresas de grande porte. Com relação ao intervalo interquartil, o valor é bem inferior: 38 bilhões. Isso significa que, ao desconsiderar os extremos, a diferença entre empresas menores e maiores, isto é, a maior concentração é de 38 bilhões. Esse intervalo representa a diferença entre o terceiro quartil (75% dos dados) e o primeiro quartil (25% dos dados). A comparação entre essa medida, a amplitude e o desvio padrão (comentado mais adiante) mostra que há poucas empresas consideradas discrepantes. Pelo gráfico do boxplot, nota-se que os valores se concentram entre 10 e 50 bilhões de reais. O desvio padrão, de 81 bilhões, está inflado devido aos valores discrepantes, pois ele mede a distância dos dados em relação à média. Como esses dados discrepantes fazem parte do conjunto, não é possível descartá-los. Cabe decidir qual medida usar: o desvio padrão considera toda a variabilidade, enquanto o intervalo interquartil mostra onde os dados estão mais concentrados, sem ser afetado pelos extremos.

Quanto à distribuição dos dados, fica claro que não segue uma distribuição normal. Por isso, qualquer imputação não deve utilizar a média. Pelo histograma e pela medida de curtose, nota-se uma assimetria positiva, ou seja, há muitas empresas com valor de mercado até 34 bilhões e poucas com valores superiores a 100 bilhões. Essa análise refere-se aos 87 ativos da composição do Ibovespa em 01/04/2025.

A decisão tomada foi a seguinte: valores acima de 100 bilhões de reais são considerados como `Large Caps`, pois estão muito acima do desvio padrão e do limite superior dado por IQR * 1.5. Empresas `Small Caps` devem ser empresas em crescimento. A análise mostra que existem empresas avaliadas em milhões, mas isso não é tão representativo. Por isso, adotou-se o valor de 10 bilhões como referência. No entanto, ao ajustar o histograma com limite de 100 bilhões e 10 bins, o agrupamento ficou até 12 bilhões. Assim, empresas com valor de mercado de até 12 bilhões são consideradas `Small Caps`. Um adendo importante: o histograma precisou de ajustes como número de bins e limite superior. A definição de faixas não foi feita apenas com base visual, mas com base em toda essa análise.

Sobraram então as `Mid Caps`, de 12 bilhões até 100 bilhões. Apesar de ser uma faixa ampla, ela respeita bem a variabilidade próxima ao desvio padrão. A maior concentração das empresas está entre 12 e 40 bilhões, o que justifica não dividir mais. `Mid Caps` são empresas que combinam crescimento com estabilidade, sendo um bom intervalo para essa definição. O nome desta nova variavel categorica é `ClassEmpresa`.

Este foi um exemplo de como foram criadas novas variáveis para o conjunto de dados. O mesmo processo foi replicado para outras duas variáveis.

Além disso, o arquivo `Relatorio.pbix` contém um dashboard que tem como objetivo realizar uma **análise multivariada**. Por exemplo, na visão geral, estão disponíveis as variáveis `Setor` e `Segmento` em relação ao `Peso de Participação`. Nessa análise, foi identificado que o setor financeiro compõe a maior parte de participação no IBOV. Em seguida, aparecem os setores de commodities, como petróleo e materiais básicos (material bruto). Somente esses três setores representam uma grande parcela do índice. Com relação ao `Segmento`, nota-se que os bancos compõem a maior parte. Também é possível observar que empresas de energia elétrica e alimentos, como frigoríficos, possuem participação relevante. Esse cenário evidencia a diferença entre o mercado brasileiro e o mercado americano. Nos Estados Unidos, as maiores empresas — conhecidas como as "magníficas" — são majoritariamente de tecnologia, enquanto no Brasil predominam bancos e empresas de materiais básicos ou commodities, como demonstrado na Imagem 5.

<p align="center">
  <img src="https://github.com/user-attachments/assets/12ac561a-4d2a-4df4-8556-c7144fdd9858" alt="Dashboard Geral da Composição Atual do Ibovespa" />
</p>
<p align="center">
  <strong>Imagem 5: Dashboard Geral da Composição Atual do Ibovespa.</strong>
</p>

Por meio da variável `Tempo de IPO`, foi criada uma variável categórica chamada `Tempo na Bolsa` (a nomenclatura "Tempo de IPO" foi considerada pouco clara; por isso, no Power BI, a variável numérica `Tempo IPO` também aparece como "Tempo na Bolsa", apenas na nomeação ou título do gráfico). Essa nova variável classifica as empresas em três categorias:

- **Consolidada**: empresas com mais de 20 anos de IPO (anteriores a 2005);
- **Normal**: empresas com IPO entre 10 a 20 anos (de 2005 até 2015);
- **Recente**: empresas com IPO nos últimos 10 anos (de 2016 até 2025).

Essa categorização segue a mesma lógica utilizada na criação da variável `ClassEmpresa`.

Com base nessa estrutura, a guia "Participacao" do dashboard apresenta algumas características da composição atual do IBOV. A Imagem 6 ilustra essa distribuição. Em relação à classificação por valor de mercado, empresas **Large Caps** representam um pouco mais da metade da participação do índice. As **Mid Caps** também possuem presença significativa, enquanto as **Small Caps**, apesar de serem numericamente mais numerosas, têm uma representatividade muito pequena — cerca de 7%. Isso evidencia que o índice tende a priorizar empresas de grande porte. Em relação ao tempo de presença na bolsa, empresas com mais de 20 anos de IPO são as mais representativas. Já empresas com menos de 10 anos de IPO representam apenas cerca de 6% da composição do índice. Essa distribuição sugere que o IBOV valoriza segurança e estabilidade nos ativos, priorizando empresas consolidadas e de grande valor de mercado.

Contudo, é importante observar que essa é uma análise **atemporal**, baseada na composição atual do índice. As empresas consideradas grandes e consolidadas hoje podem ter tido uma trajetória completamente diferente há 10 ou 20 anos. Apesar disso, o índice também aloca uma pequena parcela de sua composição em empresas mais recentes e com potencial de crescimento elevado.

<p align="center">
  <img src="https://github.com/user-attachments/assets/28b73135-0eb1-4d00-b5ba-896439688e97" alt="Dashboard da Representatividade das Empresas" />
</p>
<p align="center">
  <strong>Imagem 6: Dashboard da Representatividade das Empresas.</strong>
</p>

Além disso, no arquivo `2.Analises.ipynb`, foi realizada uma análise de correlação entre as variáveis numéricas `Tempo de IPO`, `Idade da Empresa`, `Peso de Participação` e `Valor de Mercado`. A Imagem 7 apresenta um mapa de calor dessas correlações. Observa-se que as variáveis `Valor de Mercado` e `Peso de Participação` apresentam uma **correlação positiva forte**. Embora correlação não implique necessariamente causalidade, os dados sugerem que o índice IBOV considera fortemente o valor de mercado das empresas para determinar sua representatividade. 

Por outro lado, a correlação entre `Idade da Empresa` e `Tempo de IPO` com o `Peso de Participação` é **considerada fraca**, o que contrasta com a análise apresentada na Imagem 6, onde a soma da participação das empresas com mais de 20 anos de IPO representava mais de 70% do índice. Isso evidencia que, apesar da concentração em empresas antigas, o tempo de listagem ou idade da empresa, isoladamente, não possui forte relação linear com a participação no índice.

<p align="center">
  <img src="https://github.com/user-attachments/assets/f8bfe428-8dae-43ca-a130-950e7f678928" alt="Correlação entre as variaveis numericas do dataset scraping_ativos.csv" />
</p>
<p align="center">
  <strong>Imagem 7: Correlação entre as variaveis numericas do dataset scraping_ativos.csv.</strong>
</p>

Na guia **"Multivariada"** do relatório em Power BI, concentram-se análises multivariadas, como o próprio nome indica. Essa seção inclui gráficos de dispersão, como o apresentado na Imagem 7, que resume a correlação entre os ativos. A dispersão entre `Peso de Participação` e `Valor de Mercado` revela uma tendência clara de crescimento, reforçando a relação positiva entre essas variáveis.

Uma questão relevante surge a partir dessa análise: *empresas com alto valor de mercado estão necessariamente associadas ao tempo de listagem na Bolsa?* A **Imagem 8** busca responder a essa pergunta. Observa-se que muitas empresas classificadas como `Consolidadas` (mais de 20 anos de IPO) estão no grupo `Mid Caps`. Surpreendentemente, também há empresas `Small Caps` com mais de 20 anos de IPO. Embora a maioria das `Large Caps` seja composta por empresas consolidadas — e não haja nenhuma empresa recente nessa categoria — a presença de empresas antigas entre as `Small Caps` evidencia que a longevidade na Bolsa não garante um alto valor de mercado. Essa conclusão é compatível com os resultados da análise de correlação entre as variáveis numéricas, na qual o `Valor de Mercado` apresenta **correlação fraca** com o `Tempo em Bolsa` e a `Idade da Empresa`. Ao observar novamente a **Imagem 8**, nota-se que a maioria das empresas é classificada como consolidada, o que pode explicar a expressiva representatividade dessas empresas observada anteriormente na **Imagem 6**.


<p align="center">
  <img src="https://github.com/user-attachments/assets/10d73c28-1486-4374-9956-14ffe31bc997" alt="Associação de Tamanho das Empresas com o Tempo da Empresa na Bolsa" />
</p>
<p align="center">
  <strong>Imagem 8: Associação de Tamanho das Empresas com o Tempo da Empresa na Bolsa.</strong>
</p>

#### O que vimos até agora?

Em resumo, foram criadas variáveis por meio da análise univariada, utilizando técnicas como medidas de estatística descritiva, histogramas e boxplots para classificar os ativos. Essas variáveis têm o objetivo de descrever características comparativas entre os ativos, considerando que, inicialmente, os dados eram apresentados de forma isolada. As análises foram conduzidas no Excel (arquivo `Analises.xlsx`).

Para compreender a composição da carteira do Ibovespa, é essencial avaliar suas características. Embora a introdução apresente os critérios formais de inclusão de ativos, as análises contidas no dashboard (arquivo `Relatorio.pbix`) e no notebook `2.Analises.ipynb` permitem levantar algumas hipóteses sobre o funcionamento dessa composição:

1. Há uma forte presença dos setores de **Finanças** e **Commodities**.
2. Dentro desses setores, os segmentos mais representativos são os **bancos**, seguidos por **empresas elétricas** e **frigoríficos** (embora carnes sejam consideradas commodities, aqui o foco recai sobre petróleo, metais, alumínio, entre outros).
3. Ativos com **alto valor de mercado** tendem a apresentar maior representatividade no índice, evidência observada tanto na correlação entre variáveis numéricas quanto na predominância de `Large Caps`, que somam mais da metade da participação no índice.
4. O **tempo de listagem na Bolsa** (Tempo de IPO) não possui uma relação linear direta com a representatividade. Apesar de empresas com mais de 20 anos de IPO apresentarem elevada participação no índice, a correlação entre tempo de listagem e representatividade é fraca, sugerindo ausência de relação causal.
5. O **valor de mercado** de um ativo não está necessariamente associado ao **tempo em que está na Bolsa**, como evidenciado pela presença de empresas `Small Caps` com mais de 20 anos de IPO.

Essas observações ajudam a compreender melhor os critérios implícitos na composição do índice Ibovespa, além de trazer o entendimento para o nosso principal objeto de estudo: a composição da carteira do IBOV.
