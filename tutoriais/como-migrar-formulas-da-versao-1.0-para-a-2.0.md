# Como migrar fórmulas da versão 1.0 para a 2.0?

## **Contexto** <a id="differences-between-version-1-0-and-2-0"></a>

Se você usa a versão 1.0 do Ritchie e deseja migrar para a versão 2.0, **será necessário atualizar a estrutura dos seus repositórios de fórmulas** para ser compatível com a nova versão.

## Como migrar?

Abaixo, segue um **passo a passo** de como você pode fazer isso:

**Passo 1**: Crie um novo repositório do zero usando o comando rit create formula

* Adicionando as mesmas fórmulas usadas no repositório antigo, no repositório novo.

**Passo 2**: Exporte a implementação das  fórmula do repositório antigo para o novo.

* A estrutura continua usando os mesmos arquivos: **`config.json`** , **`main.*`**, **`formula.*`**.
* Copie o código da estrutura antiga para a nova, respeitando o novo layout.

**Passo3**: Publique o novo repositório de fórmulas no **github** ou no **gitlab** \(pode ser **público** ou **privado**\).

**Passo 4**: Gere uma release desse repositório de fórmulas.

**Passo 5**: Adicione o repositório de fórmulas no Ritchie usando o comando **`rit add repo`**.

**Passo 6**: Compartilhe seu repositório de fórmula com sua equipe, seus colegas ou a comunidade.

{% hint style="info" %}
Em case de dúvida, fique à vontade para entrar em contato com a nossa equipe no e-mail **ritchie@zup.com.br** ou **abrindo uma issue** no repositório [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas).
{% endhint %}

