---
title: "Machine Learning no Device ou Servidor"
description: "Transferência de Estilo com Flutter e TensorFlow"
date: 2020-12-07T03:24:00-04:00
draft: false
toc: false
images:
tags:
  - Flutter
categories:
  - Desenvolvimento de Software
  - Inteligência Artificial
series: ["Transferência de Estilo com Flutter e TensorFlow"]
series_order: 4
---

No post [Flutter e suporte ao TensorFlow Lite](https://matheper.com/2020/09/07/flutter-e-suporte-ao-tensorflow-lite/), mencionei a mudança de planos para servir nosso modelo de Machine Learning (ML) utilizando FastAPI em vez de integrá-lo ao app Flutter. Entretanto, apesar de estar empolgado com a implementação do backend em Python, existem vantagens e desvantagens em rodar um modelo em um servidor ou diretamente no device. Então vamos a algumas considerações quanto ao processo de inferência.

## Treinamento x Inferência

A implantação de um sistema de Machine Learning envolve diferentes etapas, desde a coleta e limpeza de dados (data collection, data cleaning), extração de características (feature extraction) e treinamento (training), até servir (serving) e monitorar (monitoring) seus modelos em produção. Você pode conferir estas e outras etapas no artigo [Hidden Technical Debt in Machine Learning Systems](https://papers.nips.cc/paper/5656-hidden-technical-debt-in-machine-learning-systems.pdf), publicado pelo Google ainda em 2015.

Cada uma destas etapas têm seus próprios desafios, por exemplo, coleta e limpeza de dados é uma tarefa que demanda boa parte dos recursos e tempo de um projeto de Machine Learning. Diversas pesquisas apontam que [cientistas de dados gastam mais de 60% do seu tempo com limpeza de dados](https://www.forbes.com/sites/gilpress/2016/03/23/data-preparation-most-time-consuming-least-enjoyable-data-science-task-survey-says).

Os desafios relacionados as etapas de treinamento e inferência também são diferentes, enquanto o primeiro requer disponibilidade de recursos computacionais e expertise em modelos de ML, inferência precisa rodar o mais rápido possível e preferencialmente consumindo poucos recursos. Você não quer que seu carro leve alguns segundos para decidir se deve freiar ou não em uma situação de risco, assim como não quer que seu smartphone fique sem bateria após alguns minutos porque está rodando algum aplicativo que utiliza Machine Learning.

Treinamento requer poder computacional pois durante esta etapa, o aprendizado do modelo acontece por meio de repetidas interações sobre um conjunto de dados de treinamento, um processo que pode ser custoso, especialmente para Deep Learning, e que normalmente acontece em um hardware potente, muitas vezes com auxílio de [GPUs](https://developer.nvidia.com/deep-learning) ou até mesmo hardwares especializados como [TPUs](https://cloud.google.com/tpu/docs/tpus) (Tensor Processing Unit).

Para inferência, você não precisa de todo este poder computacional, em vez disso, precisa de respostas o mais rápido possível. Imagine que, ao contrário de um processo interativo e custoso como o treinamento, em uma analogia com um laço de repetição, inferir um resultado é uma execução única, uma interação em vez de uma repetição extensiva.

## Trade-offs de Inferência

No geral, a performance do seu modelo é o requisito com maior importância quando você está decidindo onde seu modelo irá rodar (dispositivo ou servidor). Porém, outros requisitos também devem ser levados em consideração dependendo da sua aplicação, por exemplo, a capacidade de processamento do seu dispositivo, consumo de energia e acesso à internet.

Se o dispositivo não tiver acesso à internet, por exemplo, você não terá outra opção que não rodar seu modelo diretamente no device. Por outro lado, se o seu dispositivo não tiver capacidade suficiente, seja de processamento ou memória, você precisará de um servidor para rodar inferência e que o seu dispositivo esteja conectado na internet.

Quando seu dispositivo tem acesso à internet e recursos suficientes, você ainda precisa considerar coisas com velocidade: é mais rápido rodar inferência no dispositivo móvel, que provavelmente é mais lento, ou enviar dados pela rede até um servidor mais potente, o que gera delays e maior consumo de dados, fazer a inferência no servidor e enviar o resultado de volta pela rede.

Como estamos falando de trafegar dados pela rede, existe também a questão de segurança e privacidade. Se seu modelo rodar diretamente no dispositivo, você pode garantir que os dados  do usuário estarão protegidos. Você também pode garantir isso em um servidor com conexão segura, mas a questão é que você pode rodar todo o processo de inferência diretamente no device, sem enviar informação alguma do usuário para fora do próprio dispositivo do usuário.

### Inferencia no Servidor:

* Vantagens:
	* Maior poder computacional, o modelo não estará limitado à capacidade do dispositivo.
	* Maior portabilidade, seu modelo está disponível por meio de um simples request HTTP/HTTPS.
	* O modelo pode ser atualizado a qualquer momento, sem necessidade de atualização do aplicativo.
	* Fácil integração com outros serviços de backend ou lógicas de negócio já existentes.
	* O aplicativo rodando no dispositivo será menor e mais level.
* Desvantagens:
	* Dispositivo precisa de acesso à internet. Esta é a principal desvantagem, o aplicativo só funcionará conectado à internet.
	* Infraestrutura extra, tanto de hardware como de software, para rodar o servidor de inferência.
	* Consumo extra de internet. Todas as informações precisam trafegar pela rede.
	* Servidor como gargalo e ponto único de falha. Imagine um servidor que rode uma inferência simples, mas para milhares de usuário. O servidor precisa suportar esta carga de trabalho e implementar um mecanismo de auto-scaling e redundância, o que significa maior complexidade de infraestrutura. Se a inferência rodasse diretamente no dispositivo, este processamento seria naturalmente distribuído, com cada dispositivo processando suas próprias inferências.
 
### Inferência no Device:

* Vantagens:
	* Aplicativo não depende de acesso à internet para rodar inferência.
	* Na maioria dos casos, inferência rodará mais rápido no dispositivo do que o tempo de request, processamento e resposta de um servidor.
	* Não há nacessidade de um servidor de inferência, o que significa menos código e complexidade de infraestrutura.
	* Processamento naturalmente distribuído, cada dispositivo processa sua própria demanda.
* Desvantagens:
	* Empacotar o modelo de Machine Learning torna o aplicativo maior e mais pesado.
	* É necessário atualizar o aplicativo toda vez que houver uma modificação do modelo.
	* Pode ser necessário implementações específicas do modelo para diferentes tipos de plataformas.
	* O modelo está limitado à capacidade de processamento do dispositivo.


## Conclusão:

Não há uma solução ideal ou bala de prata que funcione para todos os casos. A melhor opção será aquela que atender ao maior número de requisitos sabendo-se que abrimos mão de algumas vantagens e precisaremos lidar com algumas desvantagens e limitações com qualquer uma das escolhas.

No caso do nosso aplicativo, rodar o modelo diretamente no dispositivo faria mais sentido, mas como escolhemos implementar o app em Flutter, esbarramos em uma limitação tecnológica. Por este motivo,  vamos seguir o projeto com a inferência do lado do servidor, implementado com FastAPI.

Se você quiser utilizar este mesmo modelo diretamente no dispositivo móvel, eu recomendo partir diretamente para uma implementação nativa com Kotlin para Android, ou Swift para iOs. Você pode encontrar exemplos de transferência de estilo para [Android](https://github.com/tensorflow/examples/tree/master/lite/examples/style_transfer/android) e [iOS](https://github.com/tensorflow/examples/tree/master/lite/examples/style_transfer/ios) no [GitHub do TensorFlow](https://github.com/tensorflow/examples).