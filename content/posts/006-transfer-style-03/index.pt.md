---
title: "Flutter e suporte ao TensorFlow Lite"
description: "Transferência de Estilo com Flutter e TensorFlow"
date: 2020-09-07T07:55:00-04:00
draft: false
toc: false
images:
tags:
  - Flutter
categories:
  - Desenvolvimento de Software
  - Inteligência Artificial
series: ["Transferência de Estilo com Flutter e TensorFlow"]
series_order: 3
---

Hoje o post é um update em relação ao nosso projeto de transferência de estilo. Tem uma boa notícia e uma má notícia em relação a isso. Como de costume, vamos começar pela má notícia e ao final, você descobrirá qual é a boa. A propósito, a boa notícia me deixou ainda mais animado com o projeto!

## Flutter plugins para TensorFlow
Como disse no primeiro post da série, estou implementando nosso app ao mesmo tempo que escrevo os posts. Então alguns pontos do nosso planejamento poderiam mudar ao longo do tempo.

Direto ao ponto, a má noticia é que, depois de duas semana fazendo alguns testes com Flutter e os pluging disponíveis para integração com TensorFlow, posso afirmar que, no momento em que escrevo este post, não há suporte oficial de TensorFlow para Flutter.

Explicando melhor o que aconteceu nas duas semanas em que fiz os testes, comecei com algumas pesquisas, pois não tinha certeza se seria possível integrar nossos modelos TensorFlow ao Flutter.

Depois de alguns cliques, cheguei ao [pub.dev](https://pub.dev/) que é um gerenciador de pacotes do Flutter, na verdade o gerenciador de pacotes do [Dart](https://dart.dev/), assim como [pip](https://pypi.org/project/pip/) é o gerenciador de pacotes do Python ou [npm](https://www.npmjs.com/) do JavaScript.

Pesquisando por `TensorFlow`, encontrei 3 pacotes disponíveis: tensorflow, tflite e tfliteflutter.

![Flutter e TensorFlow Plugins](https://matheper.com/media/images/Screen_Shot_2020-07-24_at_9.33.58_PM.original.png)

Apesar de não ter experiência com Flutter, fiz uma análise rápida das informações disponíveis na própria página do pub.dev: Likes, Popularity, Versão, Data de Publicação e Pub Points. Eu não sabia o que eram esses Pub Points, mas assumi que maior é melhor, depois descobri que é uma [medida de qualidade oficial do pub.dev](https://pub.dev/help/scoring).

Ao analisar estas informações, descartei o pacote tensorflow: publicado em 2018, versão 0.0.0, poucos likes, pub points ruim e popularidade baixa. Depois disso, precisei decidir por qual começar meus testes: [tflite](https://pub.dev/packages/tflite) ou [tflite_flutter](https://pub.dev/packages/tflite_flutter).

Ambos os pacotes tinham boas avaliações e foram publicados recentemente. tfliteflutter tem o pub points de 100 (máximo) em comparação aos 90 do tflite, mas uma informação em especial me fez escolher tflite: ele está em uma versão estável (1.1.1), enquanto tfliteflutter está em uma versão de desenvolvimento (0.5.0).

A maior parte das bibliotecas que você encontra disponíveis na internet seguem o [sistemas de versionamento semântico](https://semver.org/lang/pt-BR/) ([versão em inglês](https://semver.org/)). Em uma versão de desenvolvimento, começando com zero (0.y.z), não há garantias de que as interfaces da biblioteca são estáveis, isso significa que as funções que você utiliza no seu código podem sofrer mudanças significativas em versões futuras, fazendo a manutenção do seu proprio sistema muito mais complicada.

Bibliotecas com versão 1.0.0 ou maior precisam definir o que chamam de API pública. A API pública é a assinatura de qualquer recurso da biblioteca com que você interage no seu próprio código, como classes, métodos, funções, etc. Como assinatura, você pode considerar coisas como nomes de classes, métodos e funções; número, order, nomes e tipos de parâmetros; tipos de retorno; e por aí vai.

### TFLite

Depois de decidir começar pelo [tflite](https://pub.dev/packages/tflite), acessei seu [repositório no GitHub](https://github.com/shaqian/flutter_tflite), que também tem boas métricas e uma comunidade ativa, boa documentação, commits recentes, mais de um contribuidor, issues organizadas e com comentários tentando resolvê-las.

Este plugin disponibiliza alguns modelos pré-selecionados de TensorFlow Lite para classificação de imagens e detecção de objetos, por exemplo, mas não permite o acesso direto à API do TensorFlow Lite. Cada modelo disponível com este pacote é implementado diretamente no plugin, ao contrário de permitir que o programador escolha seu próprio modelo e o utilize como se estivesse implementando seu código diretamente para Android ou iOS.

Infelizmente, o modelo de transferência de estilo não está disponível enquanto escrevo este post e a forma como o pacote funciona não nos permite experimentar outros modelos além dos já implementados, a menos que você integre o modelo ao plugin (o que ainda está além dos meus conhecimentos em Flutter). Por estes motivos não utilizaremos o pacote TFLite no nosso projeto.

De qualquer forma, é bem divertido ver seu celular rodando alguns algoritmos de Machine Learning em tempo real. Você pode encontrar alguns exemplos de [classificação de imagens](https://github.com/shaqian/flutter_tflite/tree/master/example) e [detecção de objetos](https://github.com/shaqian/flutter_realtime_detection) implementados com TFLite.

Tendo [Flutter instalado](https://matheper.com/2020/08/31/transferencia-de-estilo-com-flutter-e-tensorflow-2/) basta clonar um dos repositórios e rodar os comandos `flutter packages get` e `flutter run`

```
flutter packages get
flutter run
```

### TensorFlow Lite Flutter

Este plugin é muito mais interessante do que o anterior pois nos permite carregar um modelo em memório e interagir diratemente com o [TensorFlow Lite interpreter](https://www.tensorflow.org/lite/guide/inference#running_a_model), como é feito quando utilizamos TFLite com Java, Swift, C++ ou Python.

Em meus testes rodei um exemplo de [classificação de texto](https://github.com/am15h/tflite_flutter_plugin/tree/master/example) (se um texto expressa um sentimento positivo, neutro ou negativo) e fiz algumas alterações para rodar nosso modelo de transferência de estilo.

Utilizando a câmera do celular (o post sobre câmera com Flutter já está no forno), fiz alguns testes com um modelo de classificação de imagens e tudo funcionou bem. Porém, quando tentei integrar nosso modelo te transferência de estilo, algumas coisas começaram a dar errado.

Depois de um ou dois dias debugando código e tentando entender a lógica implementada pelo plugin (o que foi ótimo, pois aprendi bastante sobre Dart e Flutter no meio do caminho), descobri que o pacote não suporta o formato de imagem necessário para nosso modelo.

Na mesma semana em que estava fazendo meus testes, alguém abriu uma [issue no GitHub](https://github.com/am15h/tflite_flutter_helper/issues/15) exatamente relacionada ao modelo de transferência de estilo. Eu compartilhei alguns dos meus achados dos dias anteriores e estou de olho para fazer novos testes assim que a biblioteca suportar este modelo.

Quem sabe eu até me aventure e tente contribuir para o projeto, mesmo sendo iniciante com Flutter. Por enquanto, a issue ainda está aberta e o plugin não suporta nosso caso de uso, então precisamos de um plano B.

## Bem Vindo, FastAPI!

Como não tivemos sucesso com a integração Flutter - TensorFlow, vamos utilizar um backend Python para fazer o trabalho pesado. Existem algumas opções como [Flask](https://flask.palletsprojects.com) ou [Django Rest Framework](https://www.django-rest-framework.org)  para construirmos uma API que hospede nosso modelo, mas quero aprender algo diferente, assim como estou fazendo com Flutter.

Então vamos experimentar o framework Python que todos estão falando no momento: FastAPI !

Fiz alguns testes durante a semana e estou realmente animado para utilizar FastAPI no nosso projeto. Até agora, estou gostando muito da forma como o framework foi projetado e de como ele funciona. Já consigo entender porque tantas pessoas têm bons feedbacks em relação a ele.

Nos próximos posts da série vou falar mais especificamente sobre FastAPI e seu design, mas antes quero discutir outro assunto: vantagens e desvantagens em rodar um modelo de Machine Learning em um servidor em vez de rodá-lo diretamente no dispositivo móvel. Então o próximo post será um bate-papo sobre cada uma destas abordagem.