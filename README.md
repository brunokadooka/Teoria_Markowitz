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


