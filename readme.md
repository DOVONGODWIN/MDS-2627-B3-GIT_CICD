# Cours TEST

## Rappel des bases

- Créé par Linus Torvalds en 2005
- Permet de réaliser du versionning (gestion de versions, gestion de l'historique)
- Permet le travail collaboratif (plusieurs personnes sur un même projet, et garantir l'intégrité du travail de chacun)

## Vocabulaire

- `Dossier courant` : C'est le dossier depuis lequel on exécute une commande.
- `Repository` : C'est un dossier qui "utilise" GIT : il dispose d'un sous-dossier caché ".git". Ils peuvent être distants ou locaux.
- `Repository local` : C'est le repository qui est sur une machine à laquelle vous avez généralement accès.
- `Repository distant` : C'est le repository qui est **hébergé et géré** par une plateforme spécialisée (Github, Gitlab, Gitea, etc...). Ils peuvent être publics (accessibles à tous) ou privés (accessibles uniquement à ceux qu'on souhaite).
- `Les branches` : Permettent de gérer plusieurs versions d'un même projet.
- `conflit` : C'est l'événement qui se déclenche lorsque l'intégrité du travail n'est plus assurée.
- `Fork` : C'est un repository distant propriétaire qui est une copie d'un autre repository distant non propriétaire.
- `Pull Request` : Propose de fusionner un fork vers le repository original.
- `Tag` : Étiquette permettant d'indiquer une version importante et stable.


## Commandes

- `git init` : Permet de créer un repository local dans le dossier courant.
- `git remote add origin <url>` : Permet de relier un repository local à un repository distant
- `git clone <url> <folder>` : Permet de créer un repository local à partir du contenu d'un repository distant. Lie automatiquement les deux repository.
- `git add <param>` : Permet d'indexer les fichiers/dossiers passées dans `<param>`.
- `git rm <param>` : Permet de désindexer les fichiers/dossiers passées dans `<param>`.
- `git commit -m "<message>"` : Permet de sauvegarder un état d'indexation. Permet également de décrire le commit grâce au message qui est **obligatoire**. Ils sont datés.
- `git push` : Permet d'envoyer les commits du repository local sur le repository distant. Lors du premier push sur une branche, il faudra utiliser la commande `git push -u origin <branch>`. Si vous l'oubliez, GIT vous le rapellera.
- `git pull` : Permet de récupérer les commits du repository distant sur le repository local.
- `git status` : Permet de voir l'état de la branche actuelle du repository local.
- `git log` : Permet de voir l'historique des commits.
- `git reset --hard` : Permet de supprimer toutes les modifications non commitées.
- `git branch` : Permet de lister les branches du repository local et de voir quelle est la branche active.
- `git branch <nom>` : Permet de créer une branche nommée sur le repository local.
- `git branch -d <nom>` : Permet de supprimer une branche sur un repository local.
- `git push origin --delete` : Permet de propager à distance le suppression de branches en local.
- `git checkout <nom>` : Permet de rendre la branche `<nom>` active (= changer de branche 🙈).
- `git merge <nom>` : Permet de fusionner la branche `<nom>` avec la branche active.
- `git rebase <branch>` : Permet de mettre à jour la branche courante à partir de la branche `<branch>`
- `git tag -a v1.0.0 -m "message de description"` : Permet de créer un tag sur le dernier commit, en spécifiant une version `v1.0.0` et avec un message de description.
- `git push origin v1.0.0` : Permet de pousser un tag spécifique sur le repository distant.
- `git push origin --tags` : Permet de pousser tous les tags sur le repository distant.


## Les conflits

### Comment les gérer ?

Ils peuvent concerner 1 ou plusieurs fichiers

Lorsqu'ils apparaissent, plusieurs options sont possibles :
1. Garder l'ancienne version du fichier et supprimer la nouvelle.
2. Garder la nouvelle version du fichier et supprimer l'ancienne.
3. Garder les deux versions.

Pour identifier un conflit dans un fichier, 3 parties :
- Le début est symbolisé par une série de caractères `<<<<<<<<<<<`
- La fin est symbolisé par une série de caractères `>>>>>>>>> <id_commit>`
- Pour délimiter le code "avant" du code "après", GIT insère une série de caractères `=======`

### Astuces pour les éviter ?

1. L'organisation permet largement d'éviter les conflits ou à minima de les limiter.
2. Penser à `git pull` avant de `git push` permet d'éviter d'en avoir.
3. C'est normal d'en rencontrer, même avec les meilleures pratiques.



