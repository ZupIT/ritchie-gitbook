# Credenciais

### **Comando Credenciais**  <a id="comando-credenciais"></a>

Comando: **`$ rit set credential`**

Este comando permite que você configure credenciais no Ritchie, de maneira que você não precisa informar o mesmo dado diversas vezes no terminal. Lembrando que, na [**Versão Single**](https://docs.ritchiecli.io/v/doc-portuguese/primeiros-passos/escolhendo-versao#versao-single), as credenciais são criptografadas localmente na sessão por meio da passphrase informada no[ **processo de inicialização**](https://docs.ritchiecli.io/v/doc-portuguese/primeiros-passos/inicializacao#versao-single). Já na [**Versão Team**](https://docs.ritchiecli.io/v/doc-portuguese/primeiros-passos/escolhendo-versao#versao-team), as credenciais são criptografadas na sessão online do **Keycloak** através do **Vault**.

```text
➜   rit set credential
Use the arrow keys to navigate: ↓ ↑ → ←
Profile to add credential:
  ▸ ME (for you)
     OTHER (for another user)
     ORG (for the organization)
```

Cada um pode configurar suas próprias credenciais**.** No caso da Versão Team, o admin do servidor pode também configurar credenciais para específicos usuários ou para toda a equipe.

```text
➜  rit set credential
✔ ME (for you)
Use the arrow keys to navigate: ↓ ↑ → ←
Provider:
 ▸ darwin
     email-org
     github
     gitlab
     jenkins
     kubeconfig
     aws
```

Depois que você selecionar as opções para cada perfil, será necessário selecionar para qual provedor deseja adicioná-los. Esta lista será organizada dentro da pasta de configuração do servidor.

```text
➜  rit set credential
✔ ME (for you)
✔ github
Github username:  user
Github token:  *****
```

 Uma vez que você selecionar o provider, ele irá solicitar as informações das credenciais selecionadas:

![](https://lh4.googleusercontent.com/_U93uVcs1Tu9TIUy59wuVfDCKgHbqO-lt5pPPSmlmDqwaFG1oew-nG_ntixSNFVRvmknMNca0X2G5WhYAowGS84V3Bf1OCZmurcCnK-Xkn9HZkf67ZWe6Jy6Wi2f9BNL6ggdO4sI)

