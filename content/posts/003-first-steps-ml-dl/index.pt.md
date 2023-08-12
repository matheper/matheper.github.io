---
title: "Primeiros Passos Machine Learning e Deep Learning"
date: 2020-07-22T03:27:00-04:00
draft: false
toc: false
images:
tags:
  - Inteligência Artificial
  - Deep Learning
  - Machine Learning
  - Python
categories:
  - Inteligência Artificial
---

Neste post vou compartilhar alguns links, vídeos, cursos e livros que me ajudaram durante meu processo de aprendizagem de Machine Learning e Deep Learning. Vou descrever a forma como eu aprendi, o que não significa que este é o único caminho existente, nem que este é o caminho correto, é apenas um dos muitos caminhos possíveis.

Como disse, o intuito deste artigo é compilar alguns dos materiais que serviram como fonte de estudo durante o meu processo de aprendizagem, então os links são diretamente ligados a minha experiência e, por consequência, ligados a Python.

O artigo está organizadas em 4 partes:

* Python
* Machine Learning e Deep Learning
* MLOps e IA Aplicada
* Links extras

Por enquanto, serão apenas links e referências para materiais externos, mas com o tempo, vou expandir alguns dos itens em posts específicos. Então fique ligado nos conteúdos do blog para não perder as novidades.

## Python

Se você fizer uma pesquisa rápida sobre Machine Learning na internet, perceberá que a maior parte dos resultados serão relacionamos com [Python](https://www.python.org/). Isso porque grande parte das tecnologias de Machine Learning, como [NumPy](https://numpy.org/), [Pandas](https://pandas.pydata.org/), [Scikit-Learn](https://scikit-learn.org/), [TensorFlow](https://www.tensorflow.org/) e [PyTorch](https://pytorch.org/) utilizam Python em sua fundação. Isso faz de Python uma ferramenta indispensável no seu arsenal.

Pessoalmente, aprendi Python, há quase dez anos, com três apostilas do Josué Labaki (Módulo A: Bem-Vindo a Python, Módulo B: Python Orientado a Objetos e Módulo C: Tkinter!).
Não inclui referências pois acho que estes materiais não foram atualizados desde então, mas se você encontrar apostilas com as capas do Hulk, Batman e Supergirl, são estas as apostilas.

O que recomendo, atualmente são os próprios sites da linguagem: [python.org](https://www.python.org/) e [python.org.br](https://python.org.br/). Se você preferir um material mais estruturado, recomendo o curso [Python para Zumbis](https://www.pycursos.com/python-para-zumbis/), do Fernando Masanori. Eu também estudei o livro [Python para Desenvolvedores](https://ricardoduarte.github.io/python-para-desenvolvedores/), do Luiz Eduardo Borges, que é um material voltado para quem já tem alguma experiência com programação. 

Se você já tem experiência tanto com programação quanto com Python, eu ainda recomendo o [Fluent Python](https://github.com/fluentpython), do Luciano Ramalho. Este é um livro que utilizo como referência até hoje e tenho uma curiosidade relacionada a ele: assim que cheguei no escritório aqui no Canadá, Fluent Python foi o primeiro livro que encontrei na mesa de um colega.

Uma observação que vale para quase todos os livros que eu citar aqui: os autores disponibilizam os exemplos utilizados nos livros em forma de código aberto no GitHub. 
As bibliotecas Python também são repositórios de código aberto. Você pode acessar o código fonte de [NumPy](https://github.com/numpy/numpy), [Pandas](https://github.com/pandas-dev/pandas), [Dask](https://github.com/dask/dask), [TensorFlow](https://github.com/tensorflow/tensorflow), [PyTorch](https://github.com/pytorch/pytorch). Você pode inclusive acessar o [repositório do Python](https://github.com/python/cpython) ou de quer outra linguagem de programação de código aberto.

Esteja familiarizado com o código fonte e, o mais importante, sempre leia a documentação oficial de qualquer tecnologia que você utilizar. Quanto antes você começar a desenvolver este hábito, mais rápido você chegará a um nível profissional em programação.

## Machine Learning e Deep Learning

Começando com Machine Learning (ML) e Deep Learning (DL), o conceito mais importante que você deve ter em mente, é o de que seu programa aprende a partir de dados, em oposição à programação convencional onde implementamos regras explícitas para resolver problemas específicos.

Duas playlists do canal Google Developers são excelentes para quem está começando: [Machine Learning Recipes with Josh Gordon](https://www.youtube.com/playlist?list=PLOU2XLYxmsIIuiBfYad6rFYQU_jL2ryal) e [AI Adventures](https://www.youtube.com/playlist?list=PLIivdWyY5sqJxnwJhe3etaK7utrBiPBQ2), com o Yufeng Guo. Particularmente, considero AI Adventures a melhor série atualmente disponíveis para quem está começando com ML.

Também do Google Developers, a playlist [Machine Learning Foundations](https://www.youtube.com/playlist?list=PLOU2XLYxmsII9mzQ-Xxug4l2o04JBrkLV), com o Laurence Moroney, é excelente para quem está dando os primeiros passos com redes neurais. Esta playlist acabou de ser lançada, então os algoritmos já são implementados com TensorFlow 2.0. A série apresenta exemplos de visão computacional com redes neurais convolucionais (Convolutional Neural Network, CNN ou ConvNet) e processamento de linguagem natural (Natural Language Processing, NLP) com redes neurais recorrentes (Recurrent Neural Network, RNN).

Como você pode imaginar ao assistir as playlists, os dados fazem parte da essência de ML. Em uma tradução livre de um trecho do primeiro vídeo do AI Adventures, ML pode ser simplificado em uma única frase: usar dados para responder questões.

Os dados fazem parte da etapa de construção (building) e treinamento (training) de um modelo de Machine Learning. Responder questões se refere a etapa de inferência, quando utilizamos modelos treinados para fazer previsões (predictions) a partir do que foi aprendido durante a etapa de treinamento.

Sabendo disso, as bibliotecas [NumPy](https://numpy.org/) e [Pandas](https://pandas.pydata.org/) são suas principais ferramentas quando o assunto é manipulação e exploração de dados em Python. Mas é preciso se familiarizar com estas bibliotecas pois elas apresentam algumas particularidades quando comparadas a outras não relacionada a ML.

Primeiramente, você precisa compreender suas estruturas de dados: [NumPy Arrays](https://numpy.org/doc/stable/reference/arrays.html), [Pandas Series](https://pandas.pydata.org/pandas-docs/stable/reference/series.html) e [Pandas Dataframe](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html).
Também é importante estar confortável com a [manipulação de índices, slicing e selects](https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html), que funcionam de forma similar aos índices e slices de Python, e operações básicas como [merge, join, concatenate](https://pandas.pydata.org/pandas-docs/stable/user_guide/merging.html), [reshape](https://pandas.pydata.org/pandas-docs/stable/user_guide/reshaping.html) e [group_by](https://pandas.pydata.org/pandas-docs/stable/user_guide/groupby.html).

Os tipos de dados também são um pouco diferente quando trabalhamos com NumPy e Pandas. NumPy suporta uma variedade de [tipos numéricos](https://numpy.org/devdocs/user/basics.types.html) maior do que Python e Pandas implementa alguns tipos de dados adicionais como [categorical](https://pandas.pydata.org/pandas-docs/stable/user_guide/categorical.html) e [integer](https://pandas.pydata.org/pandas-docs/stable/user_guide/integer_na.html) e [boolean](https://pandas.pydata.org/pandas-docs/stable/user_guide/boolean.html) que permitem valores nulos (missing values).

Isso nos leva a outros dois pontos que considero importante se você está iniciando com ML: [missing data](https://pandas.pydata.org/pandas-docs/stable/user_guide/missing_data.html) e [dados esparsos](https://pandas.pydata.org/pandas-docs/stable/user_guide/sparse.html).

Missing data, como o nome sugere, está relacionado a falta de dados. Quando trabalhamos com datasets (conjunto de dados) reais, as informações podem ser representadas de diferentes formas e muitas vezes de maneira incompleta. Estas informações incompletas são expressas por meio dos tipos NaN, NaT ou None, dependendo do tipo original (int, float, datetime, object).

Datasets contendo missing data podem causar problemas para muitos dos algoritmos de Machine Learning. Então, é uma prática comum remover estas entradas ou preencher os valores faltantes com alguma medida estatística como média ou mediana ([missing data imputation](https://machinelearningmastery.com/statistical-imputation-for-missing-values-in-machine-learning/)).

Dados esparsos (sparse data), por outro lado, são conjuntos de dados com muitos valores iguais a zero ou nulo. Diferentemente de missing data, estes valores em branco fazem parte da informação representada no dataset e geralmente são relacionados a dados coletados por sensores.

Em um sensor de presença que monitora uma casa vazia, por exemplo, é esperado que a maior parte do tempo não haja registro algum de movimentação. Mas, se você quiser treinar um modelo para detectar padrões de furtos, você precisará tanto de dados de quando houve alguma movimentação quanto de momentos onde não havia ninguém na casa, que podemos imaginar, será a maior parte do tempo.

Pandas conta com um tipo especial de estrutura para representar dados esparsos, [SparseArray](https://pandas.pydata.org/pandas-docs/stable/user_guide/sparse.html#sparsearray), que aproveita o fato dos dados apresentarem estes espaços em branco para otimizar a forma como as informações são armazenadas e processadas.

Finalmente, uma das tarefas relacionadas ao universo de  Machine Learning é traduzir dados em insights e comunicá-los para outras pessoas. Para ajudar nesta tarefa, alguns exemplos de bibliotecas de [visualização de dados](https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html) são [Matplotlib](https://matplotlib.org/), [Seaborn](https://seaborn.pydata.org/) e [Plotly](https://plotly.com/).
Comunicar suas descobertas de forma clara e significativa é uma arte, ao dominá-la, suas descobertas terão maior alcance e impacto.

#### Modelos

Depois de estar familiarizado com Python, NumPy e Panda, é hora de mergulhar de cabeça nas técnicas de Machine Learning e Deep Learning.

Este é um tópico em alta, estamos em meio a um hype onde todas as atenções estão voltadas para este assunto. Isso faz com que novidades apareçam a todo instante. Por conta disso, é comum sentir a frustração de achar que não sabemos o suficiente sobre ML.

Esta foi uma experiência que vivi pessoalmente. Minha lista de estudo crescia dia após dia, enquanto eu mal aprendia os primeiros items. Cada novidade que eu encontrava em artigos, livros ou vídeos expandia minha lista, mas ao mesmo tempo me paralisava em meio a tanta informação. Meu conselho para superar essa dificuldade é o seguinte: domine a fundação, gerencie suas expectativas e aprenda novos algoritmos e técnicas gradualmente.

#### Playlists

Machine Learning é sobre encontrar características e padrões que descrevem um problema a partir de dados. Por isso, grande parte da teoria por trás de ML é fundamentada nos campos da Álgebra Linear, Cálculo e Estatística. Um material divisor de águas nos meus estudos foi a playlist [Neural networks](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) do canal [3Blue1Brown](https://www.youtube.com/channel/UCYO_jab_esuFRV4b17AJtAw).

Esta série de vídeos me fez compreender o funcionamento de redes neurais, backpropagation e gradiente descendente. Também a partir desta playlist cheguei ao livro [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/index.html)  do Michael Nielsen, com [repositório](https://github.com/mnielsen/neural-networks-and-deep-learning) disponível no GitHub. A partir destes vídeos também cheguei ao [colah's blog](http://colah.github.io/).

Por conta da qualidade do canal [3Blue1Brown](https://www.youtube.com/channel/UCYO_jab_esuFRV4b17AJtAw), foi impossível não assistir todas as outras playlists que, de qualquer forma, também são relacionadas com Machine Learning:
[Essence of linear algebra](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab),
[Essence of calculus](https://www.youtube.com/playlist?list=PLZHQObOWTQDMsr9K-rj53DwVRMYO3t5Yr)
e
[Differential equations](https://www.youtube.com/playlist?list=PLZHQObOWTQDNPOjrT6KVlfJuKtYTftqH6).

A série [Neural Networks from Scratch in Python](https://www.youtube.com/playlist?list=PLQVvvaa0QuDcjD5BAw2DxE6OF2tius3V3), do canal sentdex, também é uma ótima referência para compreender conceitos de Machine Learning que frameworks como TensorFlow e PyTorch implementam como layers e funções de ativação.

Por fim, nos canais do Google você ainda encontra playlists como [Coding TensorFlow em português](https://www.youtube.com/playlist?list=PLQY2H8rRoyvz8oumEhsqSG4bl7JH7_YSG),
[Coding TensorFlow](https://www.youtube.com/playlist?list=PLQY2H8rRoyvwLbzbnKJ59NkZvQAW9wLbx),
[Natural Language Processing (NLP) Zero to Hero](https://www.youtube.com/playlist?list=PLQY2H8rRoyvzDbLUZkbudP-MFQZwNmU4S).

No geral, os canais [TensorFlow](https://www.youtube.com/channel/UC0rqucBdTuFTjJiefW5t-IQ) e [Google Cloud Platform](https://www.youtube.com/channel/UCJS9pqu9BzkAMNTmzNMNhvg) sempre trazem novidades interessante.
Não esquecendo de [AI Adventures](https://www.youtube.com/playlist?list=PLIivdWyY5sqJxnwJhe3etaK7utrBiPBQ2)
e [Machine Learning Foundations](https://www.youtube.com/playlist?list=PLOU2XLYxmsII9mzQ-Xxug4l2o04JBrkLV), as playlists que recomendo sem pensar duas vezes.


#### Cursos Online

Depois de se familiarizar com os conceitos de ML, você pode começar com alguns cursos online. O primeiro deles é o lendário [Machine Learning](https://www.coursera.org/learn/machine-learning), do Andrew Ng. Depois deste, também o curso [Deep Learning Specialization](https://www.coursera.org/specializations/deep-learning), mais um vez, do Andrew Ng. Quando fiz o curso Machine Learning pela primeira vez, eu não tinha o background suficiente para entender seu conteúdo. Acredito que assistir as playlists citadas anteriormente pode ajudar  bastante se você não estiver familiarizado com o assunto.

Outro curso que também me ajudou a entender melhor os conceitos de ML, foi o [Machine Larning Crash Course](https://developers.google.com/machine-learning/crash-course), do Google. Este curso traz uma visão completa da área, além de ser um dos poucos até aqui que apresenta conceitos relacionados à engenharia para ML.

Se você se interessar por visão computacional, o curso
[CS231n: Convolutional Neural Networks for Visual Recognition](https://www.youtube.com/playlist?list=PL3FW7Lu3i5JvHM8ljYj-zLfQRF3EO8sYv), da universidade de Stanford está disponível no youtube e em sua [página oficial](http://cs231n.stanford.edu/). Este é um curso extremamente completo e que requer uma quantidade considerável de empenho para ser finalizado. Somente em vídeo, são aproximadamente 20 horas de curso. A universidade de Stanford também disponibiliza o curso [Natural Language Processing with Deep Learning](https://www.youtube.com/playlist?list=PL3FW7Lu3i5Jsnh1rnUwq_TcylNr7EkRe6), também com mais de 20 horas de vídeo. Ainda não tive a oportunidade de assistí-lo, mas ele é o próximo da minha lista "assistir mais tarde".

#### Livros

Quanto aos livros, [Hands-On Machine Learning with Scikit-Learn and TensorFlow](https://www.oreilly.com/library/view/hands-on-machine-learning/9781491962282/), do autor Aurélien Géron, foi minha primeira leitura na área. O livro já está na versão 2, com exemplos implementados em TensorFlow 2, que tem uma API muito mais intuitiva do que TensorFlow 1. Ambos os repositórios de exemplos estão disponíveis no GitHub, [handson-ml](https://github.com/ageron/handson-ml) e [handson-ml2](https://github.com/ageron/handson-ml2).

O segundo livro que recomendo é o [Deep Learning with Python](https://www.manning.com/books/deep-learning-with-python), do François Chollet. Diferente do Hands-On Machine Learning, que traz exemplos mais gerais de ML com Scikit-Learning, Deep Learning with Python se aprofunda em exemplos com TensorFlow e Keras. François Chollet é o criador do [Keras](https://keras.io/), fazendo essa leitura obrigatória para quem trabalha ou deseja trabalhar com DL. Os [notebooks de exemplos](https://github.com/fchollet/deep-learning-with-python-notebooks) também podem ser encontrados no GitHub.

Na minha lista de próximos livros está [The Hundred-Page Machine Learning Book](http://themlbook.com/) do Andriy Burkov e [Deep Learning](https://www.deeplearningbook.org/), dos autores Ian Goodfellow, Yoshua Bengio and Aaron Courville.

## MLOps e IA Aplicada

Treinar seu modelo é apenas uma de muitas partes envolvidas no desenvolvimento de uma aplicação de ML. Na realidade, o treinamento de um modelo (ML Code) corresponde a aproximadamente 5% ou menos do esforço necessário para colocar um serviço de ML em produção (fonte: [Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/production-ml-systems)). Por isso, aqui estão listadas algumas referências de tecnologias que utilizo no meu dia a dia, ou que pelo já tive a oportunidade de testar, e que são relacionadas com ML em produção.

![ML System](https://developers.google.com/machine-learning/crash-course/images/MlSystem.svg)
Esquema de um sistema de ML, fonte: [Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/production-ml-systems)

Dados que não cabem em memória será o primeiro problema que você encontrará quando começar a trabalhar com aplicações reais e, infelizmente, NumPy, Pandas e Scikit-Learn não estão preparados para lidar com dados em grande escala.

A boa notícia é que [Dask](https://dask.org/) é uma solução com APIs compatíveis com estas bibliotecas e que entrega escala e paralelismo a um custo praticamente zero em relação a refatoração de código.

Dask implementa [Arrays](https://docs.dask.org/en/latest/array.html) e [Dataframes](https://docs.dask.org/en/latest/dataframe.html) compatíveis com NumPy e Pandas que podem carregar dados maiores do que a capacidade de memória da máquina, além de permitir que estas estruturas sejam distribuídas para processamento em cluster, [Dask Distributed](https://distributed.dask.org/en/latest/). Dask também implementa alguns algoritmos de ML, [Dask-ML](https://ml.dask.org/), semelhante aos modelos de Scikit-Learn, porém otimizados para processamento distribuído.

Outro problema que você possivelmente enfrentará com aplicações reais, é a execução de algoritmos em tempo viável. Se você tem restrições de tempo e performance para seus modelos, a biblioteca [RAPIDS](https://rapids.ai/) pode ser uma boa aliada. RAPIDS é uma solução relativamente nova que permite a execução de algoritmos de ML clássicos em GPU.

Outra ótima notícia é que [Dask e RAPIDS](https://rapids.ai/dask.html) integram-se muito bem, permitindo a execução de algoritmos de ML clássicos em escala, com processamento distribuído em clusters multi-nodos e até multi-GPUs. Quando menciono ML clássico, me refiro a algoritmos implementados,  por exemplos, em Scikit-Learn, uma vez que Deep Learning com TensorFlow ou PyTorch suportam processamento distribuído e em GPU de forma nativa.

Como você viu na figura acima, treinar modelos é apenas uma pequena parte de um sistema de Machine Learning em produção. Quando se desenvolve uma solução de ML, é preciso se preocupar com coisas como coleta de estatísticas e metadados, preparação dos dados, treinamento, avaliação, tuning, deploy, prediction e monitoramento.
Além disso, estas etapas devem ser replicáveis e idealmente agnósticas à infraestrutura, ou seja, o mesmo código deve ser capaz de executar em sua máquina, em um servidor ou um provedor cloud como AWS, Google Cloud ou Azure.

Na categoria de ferramentas que colaboram para esta tarefa estão [Kubeflow](https://www.kubeflow.org/), um projeto dedicado gerenciamento do ciclo de vida e deploy de workflows de ML em Kubernetes, [MLFlow](https://mlflow.org/), outra ferramenta para gerenciamento de ciclo de vida de projetos de ML, e [TensorFlow Extended (TFX)](https://www.tensorflow.org/tfx), uma plataforma end-to-end também para deploy de pipelines, mas desta vez voltada para o ecossistema [TensorFlow](https://www.tensorflow.org/).

Todas estas tecnologias disponibilizam os componentes necessários para a implementação, deploy e monitoramento de pipelines de ML em produção. A playlist [TensorFlow Extended (TFX)](https://www.youtube.com/playlist?list=PLQY2H8rRoyvxR15n04JiW0ezF5HQRs_8F), do canal TensorFlow, e [Kubeflow 101](https://www.youtube.com/playlist?list=PLIivdWyY5sqLS4lN75RPDEyBgTro_YX7x), do canal Google Cloud Platform, são minhas recomendações, além das documentações oficiais, é claro.

Outra opção é você mesmo representar pipelines em forma de [grafos acíclicos dirigidos](https://pt.wikipedia.org/wiki/Grafos_ac%C3%ADclicos_dirigidos) ([Directed Acyclic Graph - DAG](https://en.wikipedia.org/wiki/Directed_acyclic_graph)) e utilizar algum orquestrador de workflow como [Argo workflow](https://argoproj.github.io/projects/argo), [Apache Airflow](https://airflow.apache.org/) ou 
[Luigi](https://github.com/spotify/luigi). Estas opções trazem maior flexibilidade para sua solução de Machine Learning ao preço de um maior custo de implementação e manutenção do sistema.

Obviamente muitas coisas ficaram de  fora desta lista, definitivamente vale citar as diversas tecnologias Apache que muitas vezes fazem parte de uma solução de ML, como [Spark](https://spark.apache.org/), [Kafka](https://kafka.apache.org/), [Beam](https://beam.apache.org/), [Hadoop](https://hadoop.apache.org). Além das próprias soluções de containers e deployment como [Docker](https://www.docker.com/) e [Kubernetes](https://kubernetes.io/), que são a base para as soluções MLOps apresentadas na seção anterior.

Qualquer tecnologia poderia fazer parte desta lista, uma vez que Machine Learning pode ser integrado a qualquer tipo de sistema, seja um modelo que rode em um super-cluster, um servidor que recebe requisições através de uma API simples, seu PC ou até seu celular ou Raspberry Pi.

## Links Extras

Aqui estão algumas referências que ainda não tive a oportunidade de explorar, mas que me pareceram interessantes a primeira vista:

[Introduction to Computational Thinking and Data Science - MIT](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-0002-introduction-to-computational-thinking-and-data-science-fall-2016/), 
[youtube](https://www.youtube.com/watch?v=C1lhuz6pZC0&list=PLUl4u3cNGP619EG1wp0kT-7rDE_Az5TNd)

[Mathematics of Big Data and Machine Learning - MIT](https://ocw.mit.edu/resources/res-ll-005-mathematics-of-big-data-and-machine-learning-january-iap-2020/), 
[youtube](https://www.youtube.com/playlist?list=PLUl4u3cNGP62uI_DWNdWoIMsgPcLGOx-V)

[Artificial Intelligence - MIT](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-034-artificial-intelligence-fall-2010/), 
[youtube](https://www.youtube.com/playlist?list=PLUl4u3cNGP63gFHB6xb-kVBiQHYe_4hSi)

[Brains, Minds and Machines Summer Course - MIT](https://ocw.mit.edu/resources/res-9-003-brains-minds-and-machines-summer-course-summer-2015/), 
[youtube](https://www.youtube.com/playlist?list=PLUl4u3cNGP61RTZrT3MIAikp2G5EEvTjf)

[Introduction to Neural Computation - MIT](https://ocw.mit.edu/courses/brain-and-cognitive-sciences/9-40-introduction-to-neural-computation-spring-2018/), 
[youtube](https://www.youtube.com/watch?v=PnJEj6TokDA&list=PLUl4u3cNGP61I4aI5T6OaFfRK2gihjiMm)

[MIT 6.S191: Introduction to Deep Learning](http://introtodeeplearning.com/),
[youtube](https://www.youtube.com/playlist?list=PLtBw6njQRU-rwp5__7C0oIVt26ZgjG9NI)


[Lecture Collection | Machine Learning - Stanford](https://www.youtube.com/playlist?list=PLA89DCFA6ADACE599)

[Deep learning at Oxford 2015](https://www.youtube.com/playlist?list=PLE6Wd9FR--EfW8dtjAuPoTuPcqmOV53Fu)

[Learn End-to-End Machine Learning with TensorFlow from Google Cloud](https://www.youtube.com/playlist?list=PLVext98k2evh0yh4pbS88S2DK6dOyqG4X)

[Distill](https://distill.pub/)

[Introduction to Machine Learning Course - Udacity](https://www.udacity.com/course/intro-to-machine-learning--ud120)

[Machine Learning - Udacity](https://www.udacity.com/course/machine-learning--ud262)

[Intro to TensorFlow for Deep Learning - Udacity](https://www.udacity.com/course/intro-to-tensorflow-for-deep-learning--ud187)

[Intro to Data Analysis - Udacity](https://www.udacity.com/course/intro-to-data-analysis--ud170)

[Intro to Descriptive Statistics - Udacity](https://www.udacity.com/course/intro-to-descriptive-statistics--ud827)

[Deep Learning - Udacity](https://www.udacity.com/course/deep-learning-nanodegree--nd101)

[An Introduction to Statistical Learning - Book](http://faculty.marshall.usc.edu/gareth-james/ISL/)

[TensorFlow.js - Intelligence and Learning do canal The Coding Train](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6YIeVA3dNxbR9PYj4wV31oQ)