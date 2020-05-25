# Pasta da fórmula

{% hint style="info" %}
O comando `rit create formula` cria automaticamente uma pasta referente a fórmula no repositório, de acordo com o _input_ informado. 
{% endhint %}

A pasta da fórmula tem a seguinte estrutura :

![](https://lh4.googleusercontent.com/lu-BipM4Ym4qc3EeGXLNoEyvDknCZ1ZUtAvUxWra0v4uyyKi71gZiUAJzwi2n4UlwqPwdhKROps945TJ6g6i_kfi_TmlqC-nC-JOVl7T3Oy6Ks5Fnoy8Ok1lwVViRn36JAV-JAg0)



O conteúdo da pasta **SRC** é padronizado de acordo com a linguagem escolhida, e é sempre composto dos seguintes elementos :

* o arquivo main
* o arquivo Makefile \(da fórmula\)
* o arquivo config.json
* a pasta pkg

O arquivo **main** é o executável da fórmula. Ele que inicia o código que será chamado pelo terminal. Ele será criado de acordo com a linguagem informado como _input_ no comando, e conterá um exemplo padrão de implementação.

O arquivo _**Makefile \(fórmula\)**_ é diferente do arquivo _**Makefile**_ do repositório. O _**Makefile**_ _**\(fórmula\)**_ permite gerar os executáveis da fórmula, enquanto o _**Makefile**_ do repositório permite tanto gerar os executáveis de todas as formulas, quanto testar as formulas localmente adicionando esses executáveis na [pasta .rit](../../cli/pasta-.rit.md).

O arquivo **config.json** contem 3 _**inputs**_ padrões como exemplo, que são extraídos e manipulados no arquivo **main** da fórmula.

A **pasta pkg** será composta dos demais arquivos do código que, junto com o arquivo **main** permitirão a execução da fórmula. Serão criados na linguagem escolhida.

Se você criou uma fórmula pela primeira criando o repositório local, o repositório e a pasta da fórmula seguirão a estrutura abaixo :

![](https://lh5.googleusercontent.com/6oPMzmvLxb9PGmC9a6U7KfLt4oCpEnFhOHXXOoGkgMgmaQi4kKHDo5epvU27HbWbBvM1mC1K2aruXfGPQrtWJMibeXmXmN19NbI7S81Djz11Axc0fCG2GtTNCAYivuI2iMMxMLZK)

## \*\*\*\*

