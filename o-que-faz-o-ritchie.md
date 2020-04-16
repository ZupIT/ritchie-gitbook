# O que faz o Ritchie?

{% hint style="warning" %}
A ferramenta permite criar **automações** \(chamadas de **fórmulas** no contexto do Ritchie\) que são executadas via linhas de comando e, assim, tornar mais fácil o trabalho de programação no dia a dia.
{% endhint %}

Pegando como exemplo um aplicação web de microsserviços que realiza pagamentos. No geral, o processo comum para executar esse projeto é criar toda uma infraestrutura prévia, definindo a linguagem em que o sistema será programado, baixando dependências e definindo as regras que devem ser usadas para projeto. 

Com o Ritchie, é possível fazer o setup desse novo projeto por meio de uma fórmula, permitindo criar essa infraestrutura simplesmente via uma linha de comando, que irá nesse caso entregar as pastas do projeto com todos os arquivos configurados automaticamente. Ou seja, evitamos um gasto de tempo importante em infraestrutura e configurações.

Outro exemplo - bastante comum em equipes que operam por **DevOps** - é o de desenvolvedores que dependem do time de infraestrutura para liberar os logs e, assim, acessarem e operarem em um sistema que está em produção. 

Ao utilizar o Ritchie, é possível criar fórmulas com as permissões de acesso aquele sistema, disponibilizando os logs para usuário no terminal dele. 

Isso, principalmente em casos de onboarding em equipes de desenvolvimento, é muito vantajoso por agilizar os acessos necessários e permitir que os desenvolvedores comecem a produzir assim que são integrados ao projeto.

### Sem Ritchie

![](.gitbook/assets/pt-sem-ritchie.png)

### Com Ritchie

![](.gitbook/assets/pt-com-ritchie.png)

