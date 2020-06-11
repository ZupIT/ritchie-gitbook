# Repository

## Intro

You can have access to more than one repository using Ritchie. We'll show you above some commands that you can use to manage your repo. 

## Add the commons repository

**Community's formulas** are located on the [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas) project on **GitHub**. Those formulas commands won't appear when executing the `rit --help` command if the user doesn't import the **tree.json** of this repository first. 

The tree.json of the ritchie-formulas repository is located on the following url :

```text
https://commons-repo.ritchiecli.io/tree/tree.json
```

This path must be informed through the `rit add repo` command to be added to the local Ritchie-CLI tree. As the example below :

![Example of how to add the commons repository commands to Ritchie](../../.gitbook/assets/rit-add-repo-min.gif)

Once the new repository **tree.json** has been added, its _formulas executable commands_ are added to the Ritchie helper. That means they are now available to the user.

When adding a new repository, the user can also choose the **repository's priority**, giving the formulas of this repository priority over formulas which use the same executable command on another repository. That way, when the CLI will build the main tree, it won't allow any duplicated command, but will always keep the one with the highest priority.

## **Add other** repositories

To add another repository to the CLI, follow the same process as above, except its necessary to have the tree.json of this repository stored somewhere for Ritchie to import it the same way it has been done for the [**ritchie-formulas**](https://github.com/ZupIT/ritchie-formulas) project.

## **Update** a repository

It is possible to update all repositories once they have been setted, using the `rit update repo` command. It will update the repositories tree.json from the URL informed at the repositories additions.

```text
➜ rit update repo

Wait while we update your repositories...
...Successfully got an update from the "commons" formula repository
Done.
```

## **Delete** a repository

It is possible to remove a repository tree from the CLI using the `rit delete repo` command.

The user will need to inform the name he used when he added the repository. It is possible to check the name of the current repositories using the `rit list repo` command.

```text
➜ rit list repo

NAME   	URL
commons	https://commons-repo.ritchiecli.io/tree/tree.json
```

![Example of how to remove the commons repository commands from Ritchie](../../.gitbook/assets/rit-delete-repo-min.gif)

## **Clean** a repository

The `rit clean repo` command allows the user to remove the cache of the repository informed. That way, those commands won't appear on the autocompletion until importing the tree.json of this repository again, next time the user will execute a formula from there. 

