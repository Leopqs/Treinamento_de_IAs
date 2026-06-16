Disciplina de Inteligência Artificial , Professor Munif , Unicesumar 2026

## Integrantes:
- Leonardo Enz - RA: 23011726-2
- Vinícius Zamora - RA: 23003800-2
- Bruno Novodovoski  - RA: 23175971-2  

● Contextualização:

  A diabetes é uma doença em alarmante ascensão no Brasil, segundo o gov, nos últimos 18 anos a diabetes cresceu mais de 135% e, assim como outras doenças, ela pode ser evitada com um diagnóstico antes de ser instaurada. De acordo com a SBD (Sociedade Brasileira de Diabetes) através de diabetes.org.br, o diagnóstico precoce da pré-diabetes pode reverter a doença. Por ser uma doença silenciosa, muitos não sabem dessa condição, o que pode acarretar complicações sérias, como problemas renais e cardiovasculares, neuropatias e até cegueira. Outros, ainda, não têm diabetes, mas estão no limite, conhecido como pré-diabetes, quando é verificado o aumento da glicemia, mas não em níveis altos que diagnostiquem diabetes. 

	“Isso significa que a pessoa apresenta um grande risco para desenvolver o diabetes tipo 2, já que seu organismo não produz insulina em quantidade suficiente para manter a glicose dentro dos parâmetros adequados”, explica dr. Luciano Giacaglia, coordenador do Departamento de Diabetes Tipo 2 e Pré-Diabetes da Sociedade Brasileira de Diabetes. 

  De acordo com o Ministério da Saúde, cerca de 50% dos pacientes que têm o diagnóstico de pré-diabetes desenvolvem o diabetes tipo 2 em até 10 anos. Como não apresenta sintomas, o pré-diabetes só é diagnosticado em exames de rotina, como glicemia em jejum, hemoglobina glicada e teste de tolerância à glicose oral (também conhecido como curva glicêmica). Esses exames devem ser feitos regularmente a partir dos 35 anos, em especial entre pessoas com fatores de risco para diabetes, como sobrepeso ou obesidade e histórico familiar.  “O diagnóstico precoce é muito importante para início do tratamento e reversão da condição”, diz dr. Luciano. Muitas vezes, além de mudanças no estilo de vida, o médico pode receitar medicamentos para ajudar no controle da glicemia. 

https://www.gov.br/saude/pt-br/assuntos/noticias/2026/janeiro/diabetes-cresce-135-no-brasil-em-18-anos-hipertensao-e-obesidade-tambem-avancam-saude-lanca-viva-mais-brasil-com-r-340-mi-para-a-promocao-da-saude

https://diabetes.org.br/pre-diabetes-pode-ser-revertido-se-diagnosticado-precocemente/



● Problema que será resolvido ou investigado:

  O diagnóstico precoce da pré-diabetes é essencial para que os tratamentos para reverter ou controlar o caso comecem. Para facilitar esse processo, idealizamos um modelo que prevê possíveis pacientes com pré-diabetes; esse não será um diagnóstico definitivo, mas uma forma de alertar os pacientes para uma consulta especializada para investigação do caso. Em conjunto com hospitais, o modelo pode agilizar o processo de triagem e coleta de informações sendo um adicional para um diagnóstico mais robusto, ou agindo como um alerta de risco ao médico sobre o paciente.



● Hipótese da equipe:

  O algoritmo utiliza informações de saúde que já são coletadas naturalmente em uma primeira consulta médica, então, em um cenário hospitalar, esse modelo poderá ser usado para efetuar uma triagem para coletar informações prévias para incorporar no diagnóstico médico, de forma a diminuir a demora nos atendimentos, evitar o uso de formulários exaustivos, e consequentemente, diminuir a sobrecarga nos sistemas de saúde.

  Outra possibilidade, é o uso para destacar riscos, assim a população pode tirar a dúvida de saber se estão com algum risco de desenvolver diabetes ou se já possuem uma pré-diabetes.

● Descrição do dataset utilizado:

  Foi utilizado o dataset Diabetes Health Indicators Dataset, disponível em: https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset/data?select=diabetes_binary_health_indicators_BRFSS2015.csv. Contendo indicadores de saúde relacionados ao diagnóstico de diabetes.


  Os dados são provenientes do Behavioral Risk Factor Surveillance System (BRFSS) 2015, um sistema de pesquisas de saúde pública conduzido pelo Centers for Disease Control and Prevention. O dataset foi disponibilizado no Kaggle para fins de pesquisa e aprendizado de máquina.

  O dataset contém 253.680 amostras.
    21 atributos preditores; 
    1 variável alvo (Diabetes_binary);
    Totalizando 22 colunas.

  Tratamento e preparação dos dados:
    Os dados foram divididos em:
    X = atributos preditores
    Y = Diabetes_binary,
    onde:
      X contém as variáveis independentes;
      Y contém a variável alvo.

  Foi aplicada a técnica de balanceamento SMOTE (Synthetic Minority Over-sampling Technique), utilizada para gerar exemplos sintéticos da classe minoritária (pacientes com diabetes), reduzindo o desbalanceamento entre as classes, além de Tomek Links, utilizada para remover observações ambíguas próximas à fronteira entre as classes, melhorando a separação dos grupos.

  Divisão treino/teste:
    80% Treino (aproximadamente 202.944 registros)
    20% Teste (aproximadamente 50.736 registros)
  
  Para baixar o dataset, acesse a pasta “2bimestre” depois “trabalho” deste repositório e baixe o arquivo “diabetes_binary_health_indicators_BRFSS2015.csv” ou acesse o link https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset/data?select=diabetes_binary_health_indicators_BRFSS2015.csv.  e faça o download da pasta zipada via kagglehub. Após extrair os arquivos, a terceira planilha “diabetes_binary_health_indicators_BRFSS2015” é a fonte de dados utilizada no trabalho. Por ele conter diversos indicadores de saúde de pessoas saudáveis, diabéticas e pré-diabéticas, isso a torna uma ótima base de dados para treinar um algoritmo preditivo e ver o que ele acha que mais impacta uma pessoa a desenvolver diabetes.

● Métodos de IA utilizados:

  O primeiro algoritmo utiliza o método Naive Bayes e o segundo um Stacking de Random Forest, Gradient Boosting e Knn. Ambos tiveram seus dados reamostrados com as técnicas de SMOTE e Tomek links, para tentar ao máximo evitar classes majoritárias e o enviesamento do modelo.

● Avaliação dos modelos:
  
  Naive Bayes:
![metricas_NB](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/metricasNB.png)
![metricas_detalhadas_NB](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/metricasDetalhadasNB.png)
![matriz_confusão_NB](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/MCNB.png)
![curva_ROC_NB](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/CurvaROCNB.png)
![balanceamento_NB](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/balanceamentoNB.png)

  
  Stacking:
![metricas_stacking](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/metricasStacking.png)
![metricas_detalhadas](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/metricasDetalhadasStacking.png)
![matriz_confusão_stacking](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/MCStacking.png)
![curva_ROC_stacking](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/CurvaROCStacking.png)

  
● Comparação dos resultados:
  
  Naive Bayes:
![metricas_NB](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/metricasNB.png)
  
  Stacking:
![metricas_stacking](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/metricasStacking.png)

  
  Pelas métricas gerais é possível dizer que o modelo stacking uma performance mais satisfatória provavelmente pela base de dados ser bem grande, então um modelo complexo cairia melhor. Ainda assim, o algoritmo NB acertou mais verdadeiros positivos, talvez indicando um enviesamento do stacking.

  Matrizes de confusão:
  
  NB:
![matriz_confusão_NB](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/MCNB.png)
  
  Stacking:
![matriz_confusão_stacking](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/MCStacking.png)

  
  Pela matriz de confusão conseguimos ver mais claramente o motivo da diferença de recall dos modelos e quantos exatamente ele acertou, o stacking consegui diminuir muito a taxa de erro para pessoas não diabéticas, porém falha em identificar mais pessoas diabéticas do que o NB. A causa pode estar ligada também com enviesamento.


  Curvas ROC:
  
  NB:
![balanceamento_NB](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/balanceamentoNB.png)

  
  Stacking: 
![curva_ROC_stacking](https://github.com/Leopqs/Treinamento_de_IAs/blob/main/2bimestre/graficos_trabalho/CurvaROCStacking.png)

  
  O gráfico da curva roc não apresenta diferenças discrepantes, pois como vimos anteriormente na matriz de confusão, quando o stacking diminuiu muito a sua taxa de classificação de falsos positivos ele não conseguiu classificar tantos verdadeiros positivos quanto o NB. Consequência que pode estar relacionada também ao enviesamento do algoritmo.

● Conclusão:
  
  Não podemos concluir que o stacking realmente foi melhor do que o NB, porque por mais que ele apresente melhores métricas, devemos lembrar de que inicialmente a base de dados estava desbalanceada para a classe de não diabetes, e como foi visto na matriz de confusão, o algoritmo NB acertou mais classes diabetes do que o algoritmo stacking, indicando um possível enviesamento e necessidade de reajuste de pesos. Em uma solução cujo objetivo é identificar um problema de saúde é melhor dar um falso positivo do que um falso negativo, então a melhor escolha seria o NB.
