# Windows

## Como funciona? 

Para baixar a **versão mais atualizada do Ritchie \(1.0.0-beta.14\)** no Windows, basta clicar nos links disponíveis para cada versão. 

No entanto, é importante ter em mente alguns pré-requisitos antes de iniciar a instalação na sua máquina. 

### Requisitos 

Para você conseguir usar eficientemente o Ritchie no Windows, nossa recomendação é que tenha instalado os seguintes programas: 

* Powershell
* Cygwin

{% hint style="warning" %}
No caso Cygwin, você também precisará configurar o arquivo **/etc/nsswitch.conf** dentro da pasta dele \(/ProgramFiles\) e adicionar essa linha não comentada:**`db_home: /%H`**
{% endhint %}

Vale lembrar que, se preferir, também é possível seguir com a[ **instalação manual**.](instalacao-manual.md)  


### Instalando Versão Team 

Clique no link para[ instalar o Ritchie Team](https://commons-repo.ritchiecli.io/1.0.0-beta.14/windows/team/rit.exe)

### Instalando Versão Single

Clique no link para [instalar a Versão Single](https://commons-repo.ritchiecli.io/1.0.0-beta.14/windows/single/rit.exe)



## Usar Ritchie no Windows

{% hint style="warning" %}
O **PATH** para usar o Ritchie no Windows NÃO é configurado quando você o baixa.  
  
Enquanto que não tenha sido configurado, o usuário terá que entrar na pasta em que o **arquivo** **rit.exe** foi baixado para executar o Ritchie através desse arquivo. Exemplo: **`rit.exe init`**
{% endhint %}

Você encontrará um guia sobre como definir um caminho aqui : [Como definir ou alterar a variável de sistema PATH?](https://www.java.com/en/download/help/path.xml)



