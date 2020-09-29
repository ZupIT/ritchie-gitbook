# MacOS

## Como funciona? 

Para baixar a **versão mais atualizada do Ritchie** no MacOS, execute um dos comandos abaixo no seu terminal conforme a versão que deseja usar.

No entanto, é importante ter em mente **alguns pré-requisitos** antes de iniciar a instalação na sua máquina. 

### Requisitos 

Para você conseguir usar eficientemente o Ritchie no _MacOS_, nossa recomendação é que configurar os seguintes elementos: 

* o comando **make** \([Como usar "make" no macOS](https://stackoverflow.com/questions/1469994/using-make-on-os-x)\)
* a ferramenta **md5sum** 

{% hint style="warning" %}
Comando para instalar **md5sum** com _**Homebrew**_ : `brew install md5sha1sum`

Comando para instalar **md5sum** com _**MacPorts**_ : `sudo port install md5sha1sum`
{% endhint %}



### Instalando Versão Team 

O comando para adicionar o Ritchie Team ao seu terminal é: 

```bash
curl -fsSL https://commons-repo.ritchiecli.io/install_legacy.sh | bash
```

### Instalando Versão Single

O comando para adicionar o Ritchie Single ao seu terminal é:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install_single_legacy.sh | bash
```

Vale lembrar que, se preferir, também é possível seguir com a[ **instalação manual**.](instalacao-manual.md)

