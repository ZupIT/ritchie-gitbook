# Login

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

