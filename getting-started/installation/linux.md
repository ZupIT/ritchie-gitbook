# Linux

## How does it work? 

To install the **latest version of Ritchie**, you just have to execute the command below at your terminal according to the version you want to use.

### Installing Team Version

The command used to install Ritchie Team at your terminal is: 

```bash
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | sed -e 's/curl -SLO "https:\/\/commons-repo.ritchiecli.io\/${STABLE_VERSION}\/${OPERATIONAL_SYSTEM}\/rit"/curl -SLO "https:\/\/commons-repo.ritchiecli.io\/1.0.0-legacy\/${OPERATIONAL_SYSTEM}\/team\/rit"/g' | bash
```

### 

### Installing Single Version

The command used to install Ritchie Single at your terminal is: 

```text
curl -fsSL https://commons-repo.ritchiecli.io/install.sh | sed -e 's/curl -SLO "https:\/\/commons-repo.ritchiecli.io\/${STABLE_VERSION}\/${OPERATIONAL_SYSTEM}\/rit"/curl -SLO "https:\/\/commons-repo.ritchiecli.io\/1.0.0-legacy\/${OPERATIONAL_SYSTEM}\/single\/rit"/g' | bash
```



If you prefer, you also can follow with[ **manual installation**.](manual-installation.md)  


