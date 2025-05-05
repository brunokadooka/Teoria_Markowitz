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

Para coletar os dados, não basta apenas obter a cotação do IBOV. Afinal, o índice é composto por diversos ativos, cada um com um peso específico em sua formação. Este estudo visa encontrar uma melhor composição desses pesos e ativos, com o objetivo de tornar o índice mais rentável ou com uma distribuição risco-retorno mais eficiente. No site da B3, é possível encontrar, de forma atualizada, a composição da carteira do Ibovespa — **válida até 01/04/2025**. Este é o primeiro passo: identificar quais ativos fazem parte do IBOV. No entanto, esse documento fornece apenas o nome do ativo e seu respectivo peso de participação, o que é relevante para a análise, mas não suficiente para entender o funcionamento do índice como um todo. Para compreender melhor os ativos, é necessário obter informações adicionais como:

- Setor
- Segmento
- Tamanho de mercado
- Fundação da empresa
- Tempo desde o IPO

Essas informações são úteis para investigar que tipo de ativos o Ibovespa tende a priorizar ou atribuir maior peso. Como esses dados não estão organizados de forma acessível no site da B3, foi necessário realizar **web scraping** no site [Investidor10](https://investidor10.com.br/). Antes de iniciar o scraping, consultamos o arquivo [robots.txt](https://investidor10.com.br/robots.txt). Vale lembrar que esse arquivo não representa uma regra legal, mas indica quais partes do site estão mais ou menos propensas à coleta automatizada por bots. Selecionamos para raspagem apenas os **87 ativos** que compunham o Ibovespa até 01/04. As informações coletadas foram consolidadas no arquivo `scraping_ativos.csv`, localizado na pasta `data`.

Para o scraping, utilizamos a biblioteca `Selenium`, já que o site possui elementos dinâmicos como anúncios e filtros que exigem interação. Bibliotecas como `requests` e `BeautifulSoup` são mais indicadas para páginas estáticas e não conseguem lidar com interações via JavaScript. Abaixo está um diagrama representando esse processo:

<p align="center">
  <img src="https://github.com/user-attachments/assets/8ba3ba4e-4b68-48eb-ae6c-1703f9a773d8" alt="Diagrama do dataset scraping_ativos.csv" />
</p>
<p align="center">
  <strong>Imagem 1: Diagrama da criação do dataset scraping_ativos.csv</strong>
</p>

Agora que temos os dados brutos da composição do Ibovespa, podemos estudar as características que compõem este índice. É verdade que na introdução já comentamos alguns filtros que há para os ativos entrarem no índice, mas é preciso saber como o índice distribui esses pesos de participação. Mas ainda não acabou a parte de puxar os dados brutos, é preciso ter o principal: os dados de cotação dos ativos.

A cotação dos ativos são os dados mais importantes neste quesito. Basicamente, os dados de composição (que comentamos acima) servem apenas para entender o negócio, no caso, entender a composição do índice Ibovespa. Mas os dados que vão ser usados de fato são as cotações dos ativos. Não estamos interessados no percentual de ganho ou perda do IBOV e sim em como chegou neste percentual. Para isso, leva-se em conta o percentual do ativo ponderado pelo seu peso no IBOV.É por este motivo que, ao puxar os dados dos ativos, podemos calcular de forma manual como o índice IBOV se comportou ao longo dos anos — claro, de maneira aproximada, visto que o IBOV sempre tem mudanças.

Para a cotação dos ativos, foi simples de puxar. Utilizando a biblioteca `yfinance`, podemos fazer o download da cotação dos ativos. Passamos por parâmetro que queremos os dados diários e do máximo de período que a biblioteca disponibiliza do ativo. O dataset que é baixado é de *candles*, com variáveis do tipo Date, Abertura, Máxima, Mínima e Fechamento. Tem a variável `Adj Close`, que leva em conta os dividendos, Volume e outras variáveis. Neste caso, vamos utilizar apenas a variável Fechamento para calcular o percentual e, claro, a variável Date para verificar de qual dia é a cotação. Este foi um dos vários tratamentos realizados, e assim temos o arquivo `cotacao_ativos.csv`, também localizado na pasta `data`.


<p align="center">
  <img src="https://github.com/user-attachments/assets/ea6ce0d0-487e-4195-9100-dc0a8b17d16e" alt="Diagrama do dataset cotacao_ativos.csv" />
</p>
<p align="center">
  <strong>Imagem 2: Diagrama da criação do dataset cotacao_ativos.csv</strong>
</p>

Todo este processo de puxar os dados, fazer web scraping, uso das bibliotecas `yfinance`, `Pandas`, `Selenium`, tratamento e limpeza dos dados (limpar valores NaN, conversão de tipos de dados), e claro, habilidades envolvendo a linguagem python como funções, laços de repetição, todo o funcionamento do diagrama, está no arquivo **"1.Criando_Dados.ipynb"**. Ali, as decisões e os pensamentos de como foi implementado o código estão comentados tanto no código como em markdown. Lembrando que, na estruturação do projeto conforme dividido em 3 etapas, esta é a primeira etapa: a exportação e arranjo dos dados brutos.
