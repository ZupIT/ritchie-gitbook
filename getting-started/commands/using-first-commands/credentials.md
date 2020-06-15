# Credentials

## Set **Credentials** 

It is possible to set credentials on Ritchie to avoid informing datas multiplus times through the terminal.

The command will allow it is $ rit set credential  
  
On the single version, credentials are encrypted locally on the session, through the passphrase informed at the initialization step.

On the team version, credentials are encrypted on the Keycloak session \(online\) through the Vault \(Hashicorp\).  


```text
➜   rit set credential
Use the arrow keys to navigate: ↓ ↑ → ←
Profile to add credential:
  ▸ ME (for you)
     OTHER (for another user)
     ORG (for the organization)
```

Every user can set his own credentials,  
On the Team version, server admins can also set credentials for specific team users or for the whole team.

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

Once the user select the profile option, he needs to select with provider he wishes to add. This provider’s list is setted inside the server configuration file.

```text
➜  rit set credential
✔ ME (for you)
✔ github
Github username:  user
Github token:  *****

```

Once the user select the provider, he need to inform the selected credential’s datas.  
****

![](https://lh4.googleusercontent.com/-JVtQ04rw-nThL0ALvAnk5B63942l5z9gUrjzk34TNPiPU3BNUc4aa-BFSimdtBNO6dMJDTwBgiWr9uEg3sIwQTLiklUwqyKr5ZyWpnaHGpg4P-4GELLnmw3pPaomBM433N_bg0o)

