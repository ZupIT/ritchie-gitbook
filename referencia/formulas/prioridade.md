# Prioridade

{% hint style="info" %}
Existe um conceito de **prioridade** entre as árvores de comando dos **repositórios de fórmulas.**

Isso permite **evitar** **comandos** **repetitivos** após a junção das árvores de todos os comandos pelo CLI.
{% endhint %}

Segue a prioridade padrão definida no CLI entre os repositórios :

* Prioridade 0 : Core
* Prioridade 1 : Local
* Prioridade 2 : Outros repositórios 

Essa regra permite que cada usuário \(single\) / empresa \(team\) defina a prioridade entre os demais repositórios.

## **Exemplo**

É possível um usuário escolher entre os 2 cenários abaixo :

![](https://lh4.googleusercontent.com/XwM1MIenWGVB45DjC1A7-t_glfsYaznphkJMe7Bcxaa6RJpmy9pRBVW9hNaNw_LFJO5iEl4Zx9uNGAgpxLkPa6awswyeb_D7JktkN6M-Wntc0ad5e26LHE4I3PjoQe3Wnh29JpES)![](https://lh5.googleusercontent.com/h-6piqq1Yl-T7veYMe5rrlVWGi22P4RMs0Y3vcYn-sITSkW2w2SCXR9NjPq0jgcRwWpZnCTmIoO7jXJgc4hm9-3y1Q9SKyQwl75PtTSow4IIEoZ53Tx71FIkNIl6QsNHOrn_nUca)  
****

### **Cenário 1**

Seria dado prioridade aos comandos **commons** sobre os comandos do seu **time**.

### **Cenário 2**

Seria dado prioridade aos comandos do repositório do **time** sobre os comandos **commons**. 

Isso permitiria por exemplo a um usuário, ou time, de usar um comando que está na árvore do repositório do **ritchie-formulas** para uma fórmulas no repositório dele, realizando uma operação diferente com o mesmo comando, já que teria prioridade.  
****

{% hint style="warning" %}
É possível configurar a prioridade entre os repositórios na pasta **repo** da [pasta .rit](../cli/pasta-.rit.md) onde tem um arquivo **repositories.json** configurável.

Por mais informações sobre como manipular repositórios, confere a documentação aqui :[ Repositório.](https://docs.ritchiecli.io/v/doc-portuguese/primeiros-passos-1/comandos/repositorio)
{% endhint %}

