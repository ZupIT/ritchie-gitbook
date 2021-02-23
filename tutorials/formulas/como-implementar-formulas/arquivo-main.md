---
description: Você encontra nesta seção mais informação sobre o arquivo main de uma fórmula.
---

# Arquivo Main

## O que é um arquivo main \(main file\)? <a id="what-is-the-main-file"></a>

{% hint style="info" %}
O arquivo Main é usado para extrair os parâmetros de entrada informados no arquivo config.json, salvos como variáveis locais. 

_Os parâmetros de entrada são extraídos pelo nome do campo informado no arquivo config.json em letras maiúsculas._ 
{% endhint %}

Esse arquivo é também onde estão as funções da fórmula, manipulando parâmetros de entrada, que são chamados para realizar uma operação e/ou automação da fórmula. 

### Exemplos de arquivo Main <a id="main-file-examples"></a>

Nos exemplos abaixo, sempre há a classe de uma fórmula com uma função `Run()` .

{% tabs %}
{% tab title="main.go" %}
```text

	input1 := os.Getenv("INPUT_TEXT")
	input2 := os.Getenv("INPUT_LIST")
	input3, _ := strconv.ParseBool(os.Getenv("INPUT_BOOLEAN"))
	input4 := os.Getenv("INPUT_PASSWORD")

	formula.Formula{
		Text:     input1,
		List:     input2,
		Boolean:  input3,
		Password: input4,
	}.Run(os.Stdout)

```
{% endtab %}

{% tab title="Main.java" %}
```
public class Main {

  public static void main(String[] args) {

    String inputText = System.getenv("INPUT_TEXT");
    boolean inputBoolean = Boolean.parseBoolean(System.getenv("INPUT_BOOLEAN"));
    String inputList = System.getenv("INPUT_LIST");
    String inputPassword = System.getenv("INPUT_PASSWORD");

    Formula formula = new Formula(
      inputText, 
      inputBoolean, 
      inputList, 
      inputPassword
    );
    
    formula.Run();
  }
}
```
{% endtab %}

{% tab title="index.js" %}
```
const INPUT1 = process.env.INPUT_TEXT
const INPUT2 = process.env.INPUT_BOOLEAN
const INPUT3 = process.env.INPUT_LIST
const INPUT4 = process.env.INPUT_PASSWORD

run(INPUT1, INPUT2, INPUT3, INPUT4)
```
{% endtab %}

{% tab title="main.py" %}
```
input1 = os.environ.get("INPUT_TEXT")
input2 = os.environ.get("INPUT_BOOLEAN")
input3 = os.environ.get("INPUT_LIST")
input4 = os.environ.get("INPUT_PASSWORD")

formula.Run(input1, input2, input3, input4)
```
{% endtab %}

{% tab title="main.sh" %}
```
//Inputs are not even necessary here, as Shellscript get values from local variables directly.

runFormula '$SAMPLE_TEXT' $SAMPLE_LIST '$SAMPLE_BOOL''$SAMPLE_PASSWORD'
```
{% endtab %}
{% endtabs %}

