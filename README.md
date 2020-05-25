---
description: >-
  Nesta seção, você encontra informações iniciais sobre o Ritchie antes de se
  aprofundar no produto.
---

# Overview

## O que é o Ritchie ?

{% hint style="info" %}
Ritchie é um **CLI** \(_Command Line Interface_\) que permite **criar, armazenar e compartilhar** automações de forma **simples** e **segura**🔓com uma equipe de profissionais ou com a comunidade inteira.
{% endhint %}

{% embed url="https://www.youtube.com/watch?v=\_NZLDdn42wM&feature=youtu.be" %}

## Instalação

{% page-ref page="primeiros-passos/instalacao/linux.md" %}

{% page-ref page="primeiros-passos/instalacao/windows.md" %}

{% page-ref page="primeiros-passos/instalacao/macos.md" %}

## De onde veio o Ritchie?

O produto foi criado com objetivo de melhorar a experiência dos desenvolvedores, trazendo mais autonomia a eles, automatizando e simplificando a execução de comandos muito usados no processo de criação e desenvolvimento de produtos digitais. 

Seu nome é uma homenagem a Dennis Ritchie, um dos criadores do Unix \(predecessor do Linux\) e também da linguagem C, que permitiu a criação do mundo digital como o conhecemos hoje.  
  
Apesar de existirem equipes mais multidisciplinares no mercado, um desafio ainda muito grande está em diminuir a dependência que desenvolvedores têm de insumos vindo dos times de infraestrutura e operações. O DevOps contribuiu muito para sanar esse gargalo, mas não eliminou completamente a dependência entre áreas. 

{% hint style="warning" %}
Pensando nisso, trazemos uma ferramenta para a comunidade que promove um movimento **NoOps**, ou seja, uma solução que automatize operações repetitivas \(também conhecidas como toil\) e agilize processos muitas vezes travados na infraestrutura. 
{% endhint %}

Isso dará aos desenvolvedores a possibilidade de executar operações que eram exclusivamente de domínio da infraestrutura.

Dessa forma, os profissionais - de todas as frentes - ganham tempo para atuar em tarefas mais complexas e relevantes para gerar valor ao seu projeto.

![Demonstra&#xE7;&#xE3;o de uma  formula seguindo o mindset NoOps](.gitbook/assets/rit-demo-deploy-project.gif)

## O que faz o Ritchie ?

{% hint style="warning" %}
A ferramenta permite criar **automações** \(chamadas de **fórmulas** no contexto do Ritchie\) que são executadas via linhas de comando e, assim, tornar mais fácil o trabalho de programação no dia a dia.
{% endhint %}

Pegando como exemplo um aplicação web de microsserviços que realiza pagamentos. No geral, o processo comum para executar esse projeto é criar toda uma infraestrutura prévia, definindo a linguagem em que o sistema será programado, baixando dependências e definindo as regras que devem ser usadas para projeto. 

![Sem Ritchie](.gitbook/assets/pt-sem-ritchie.png)

Com o Ritchie, é possível fazer o setup desse novo projeto por meio de uma fórmula, permitindo criar essa infraestrutura simplesmente via uma linha de comando, que irá nesse caso entregar as pastas do projeto com todos os arquivos configurados automaticamente. Ou seja, evitamos um gasto de tempo importante em infraestrutura e configurações.

Outro exemplo - bastante comum em equipes que operam por **DevOps** - é o de desenvolvedores que dependem do time de infraestrutura para liberar os logs e, assim, acessarem e operarem em um sistema que está em produção. 

Ao utilizar o Ritchie, é possível criar fórmulas com as permissões de acesso aquele sistema, disponibilizando os logs para usuário no terminal dele. 

Isso, principalmente em casos de onboarding em equipes de desenvolvimento, é muito vantajoso por agilizar os acessos necessários e permitir que os desenvolvedores comecem a produzir assim que são integrados ao projeto.

![Com Ritchie](.gitbook/assets/pt-com-ritchie.png)

## O que torna o Ritchie único ?

Por ser uma ferramenta de CLI, o Ritchie busca melhorar a **experiência operacional dos desenvolvedores** ao máximo, simplificando tarefas repetitivas e de fácil execução que, em muitos casos, demandam muito do profissional em lembrar de todos os comandos, além de seus parâmetros e argumentos.  

O objetivo foi reduzir o retrabalho de procurar essas informações em documentações e, assim, promover mais tempo para que o time de desenvolvimento foque em suas entregas. 

 Sendo assim, em vez de sinalizar nas linhas de comando quais parâmetros e/ou argumentos o usuário precisa informar, fazemos o contrário: o Ritchie apresenta as opções disponíveis e vai, linha a linha, perguntando as informações necessárias para o comando funcionar, de forma interativa. 

{% hint style="warning" %}
O Ritchie funciona como um **repositório único de fórmulas.** Enquanto outros CLI geralmente são focados em apenas operações relacionadas a uma aplicação, no Ritchie você encontra, em um só lugar, as operações relacionadas a todas as suas fórmulas cadastradas.
{% endhint %}

No exemplo abaixo, temos a execução de um comando scaffold com a fórmula coffee. À medida que o usuário sinaliza qual a fórmula quer utilizar, o sistema automaticamente passa, linha a linha, a perguntar quais parâmetros específicos devem ser considerados para executar a ação desejada.

![](https://lh3.googleusercontent.com/joDVqE3Km8ePNO0j7vNvfwvZVHJ8mqq9l4x4Webot9pGDdjyoo6BTp7hr39PEb9EBLC43RhsDkIs_7GmxU_YT2KmSCkhOtmJWxtSA6uGEz0a-7Ar4Bfi5zvHkgy2zaMyRkHNle8w)



