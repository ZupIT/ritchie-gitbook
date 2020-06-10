# Inicialização

## **Introdução** 

Quando você finalizar o [**processo de instalação**](https://docs.ritchiecli.io/v/doc-portuguese/primeiros-passos/instalando-ritchie), é preciso realizar a inicialização da ferramenta e este procedimento varia conforme a [**versão**](https://docs.ritchiecli.io/v/doc-portuguese/primeiros-passos/escolhendo-versao) que você estiver utilizando. 

O comando necessário para rodar a inicialização é:**`$ rit init`**

## Versão Single

Para inicializar o Ritchie nesta versão, é necessário executar o comando abaixo, no caso, a **passphrase** que será usada para criptografar as informações localmente. 

```text
➜ rit init
Define a passphrase for your machine: ******
```

## Versão Team

Para inicializar o Ritchie nesta versão, é necessário informar: 

* A **organização** na qual você quer acessar; 
* A **URL do servidor** usada pela organização.

{% hint style="warning" %}
Você não pode usar a versão **Team** **sem ter configurado o servidor**.
{% endhint %}

* **se o usuário quiser fazer login** para a organização agora, ou depois usando o comando**`$ rit login`.**

```text
➜ rit init
Enter your organization:  zup
URL of the server [http(s)://host]:  https://ritchie-server.zup.io
Use the arrow keys to navigate: ↓ ↑ → ←
You can perform login to your organization now, or later using [rit login] command. Perform now?
    no
  ▸ yes
```

## **Comando do Login**

A partir do comando **`rit login`**, é possível criar uma sessão para armazenar dados que podem ser reaproveitadas em diversas fórmulas.

Portanto, isso não funciona da mesma forma para cada versão:

### Versão Team

Nessa versão, esse comando cria uma sessão usando o _Keycloak_ após o usuário ter informado sua organização com seus dados \(email & senha\). Nessa sessão, o usuário pode, por exemplo, definir suas credenciais para diversas ferramentas \(github, aws, etc…\). 

Nesse caso, as credenciais ficam armazenadas no _Vault_. Isso permite que se o usuário executar o login no Ritchie com seus dados, na máquina de uma outra pessoa, ele conseguirá buscar essas credenciais no _Vault_, apesar de ter configuradas elas na sua máquina local.

### Versão Single 

Já, na versão **Single**, o cenário anterior não é possível, pois esse comando **`rit login`** nem está disponível. 

Essa versão não usa o _Keycloak_, no lugar é criada uma sessão criptografada na máquina do usuário através de um _pathphrase_ que ele precisará informar quando executar o primeiro comando do Ritchie. Aqui, as credenciais não serão mais salvas no _Vault_, mas ficarão criptografadas localmente através do _passphrase_ informado**.**

![Exemplo da formula do login no Ritchie](https://lh5.googleusercontent.com/Nnh0Otg0Re0ogLbSa3qCkJ44LFzl4cRhima-3szJ4SarmQ24OFwH6ii-Y35qcbhBtbL9j6KILGOIz5jKEfT0o2KjFZbjjnbMOjELYO25tMPIPrtdlxDVPIGneGTNbThYIEtvNdH6)

No exemplo acima, podemos observar que o usuário teve acesso a novos comandos após efetuar o login na organização Zup \(versão **Team**\).

{% hint style="warning" %}
O comando**`rit logout`** permite ao usuário finalizar a sessão atual.
{% endhint %}

