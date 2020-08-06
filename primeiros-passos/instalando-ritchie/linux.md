# Linux

## Como funciona? 

Para baixar a **versão mais atualizada do Ritchie** no Linux, basta executar o comando abaixo no seu terminal de acordo com a versão que deseja usar.  


### Instalando Versão Team 

O comando para adicionar o Ritchie Team ao seu terminal é: 

```bash
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | sed -e 's/curl -SLO "https:\/\/commons-repo.ritchiecli.io\/${STABLE_VERSION}\/${OPERATIONAL_SYSTEM}\/rit"/curl -SLO "https:\/\/commons-repo.ritchiecli.io\/1.0.0-legacy\/${OPERATIONAL_SYSTEM}\/team\/rit"/g' | bash
```

### Instalando Versão Single

O comando para adicionar o Ritchie Single ao seu terminal é:

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | sed -e 's/curl -SLO "https:\/\/commons-repo.ritchiecli.io\/${STABLE_VERSION}\/${OPERATIONAL_SYSTEM}\/rit"/curl -SLO "https:\/\/commons-repo.ritchiecli.io\/1.0.0-legacy\/${OPERATIONAL_SYSTEM}\/single\/rit"/g' | bash
```

\_\_

Vale lembrar que, se preferir, também é possível seguir com a[ **instalação manual**.](instalacao-manual.md)  


