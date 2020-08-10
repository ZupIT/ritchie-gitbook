---
description: >-
  Você encontrará nessa seção todas as informações iniciais sobre o Ritchie
  antes de se aprofundar no produto.
---

# Visão geral

## O que é o Ritchie?

O Ritchie é um **framework open source** que cria e ajusta o CLI para seu time. Ele permite que você crie, faça o build e compartilhe [**fórmulas**](key-concepts.md#formulas) facilmente.

{% embed url="https://youtu.be/PtKFco2pIqs" %}

## **Versionamento**

Atualmente, o Ritchie possui **duas versões disponíveis** para ser usada. Nesta documentação,  o foco será no **Ritchie versão 2.0.**

### **O que muda?**

As principais diferenças dessa nova versão são: 

* You você não precisa fazer upload de binários para cloud storage porque as fórmulas ficarão no Github ou Gitlab.
* Você pode versionar suas fórmulas usando git tags 
* A árvore de comandos será gerada dinamicamente nos repositórios adicionadas. Logo, você não precisa editar o arquivo tree.json.
* As fórmulas podem ser "buildadas" de maneira mais estável no Windows \(sem dependência de ferramentas de terceiros\).
* A execução de fórmulas é permitida via container \(continua por padrão a execução sem container de maneira nativa\). 
* Você pode usar um comando para listar as credenciais setadas. 
* Você tem um tutorial para te guiar com dicas no CLI 
* Você tem o suporte de autocomplete para 2 novos shells \(fish e powershell\)

## **Como o Ritchie funciona?**

O processo comum para executar um projeto é criar uma infraestrutura prévia, definir a linguagem em que o sistema será programado, baixar as dependências e definir as regras que devem ser usadas para projeto.

![WITHOUT Ritchie](.gitbook/assets/en-sem-ritchie.png)

Com o Ritchie, é possível fazer o setup do projeto por meio de uma fórmula, o que permite criar essa infraestrutura via uma linha de comando. Assim, o sistema entrega as pastas do projeto com todos os arquivos configurados automaticamente e, a partir disso, evitamos um gasto de tempo em infraestrutura e configurações.

![WITH Ritchie](.gitbook/assets/en-com-ritchie.png)

