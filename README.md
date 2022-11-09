# Procedure-git
# Git

### Initier un projet. 

#### Vous n'avez encore rien fait dans votre projet.

	git init mon_projet

Cela va créér un répertoire "mon_projet" dans le dossier courant.

#### Vous avec déjà débuté votre projet.
Votre répertoire "mon_projet" existe donc déjà, et il contient déjà des fichiers. Placez vous dans votre répertoire et exécutez la commande suivante:

	git init

### Ajoutez des fichiers à votre git.

Votre répertoire contient des fichiers, il faut les ajouter à git pour qu'il puisse tenir compte de ces fichiers.

	git add my_file

Ou si plusieurs fichiers:

	git add my_file1 my_file2

Ou pour ajouter tous les fichiers du répertoire:

	git add .

### Afficher le statut de votre git. 

	git status

Vous obtiendrez ainsi la liste des fichiers non encore ajoutés à votre git, et la liste des fichiers déjà ajoutés, mais n'ayant pas encore été mis a jour dans votre git depuis leur dernière modification.

### Faire un commit.

Vous avez modifié un fichier (par exemple my_file1), il faut alors faire un commit pour que git enregistre ces modifications:

	git commit my_file1 -m "ajout de la fonction md2html"

L'argument -m permet d'ajouter un bref commentaire décrivant votre modification. Ce commentaire est obligatoire; si vous n'ajoutez pas l'argument -m et son commentaire, l'éditeur nano s'ouvrira alors pour que vous puissiez ajouter votre commentaire.

### Obtenir une liste de tous vos commit et de leurs commentaires.

	git log

Pour chaque commit, la première ligne correspond au sha du commit.

### Revenir à un ancien commit.

Il faut faire un `git log` pour connaitre son sha.

	git checkout sha_du _vieux_commit

Pour revenir au dernier commit (le plus récent):

	git checkout master

### Créér une branche.

Vous voulez faire une modification sur l'un de vos fichiers tout en conservant votre dernier commit intacte; il faut pour cela créér une branche.

	git branch nom_de_la_branche

Pour savoir dans quelle branche vous vous situez:

	git branch

Vous verrez alors vos differentes branches: la branche master (c'est la branche principale), et votre nouvelle branche.
L'astérix devant master signifie que vous êtes toujours dans la branche master. Il faut alors changer de branche avant de faire vos modifications:

	git checkout nom_de_la_branche

Pour créér une branche en se plaçant directement dans celle ci:

	git checkout -b nom_de_la_branche

### Merger une branche avec le master.

Les modifications apportées dans la branche vous conviennent. Il faut alors fusionner votre branche et votre master. Placer vous dans la branche master:

	git checkout master

Puis :

	git merge nom_de_la_branche

Pour effacer la branche devenue inutile:

	git branch -D nom_de_la_branche

### Cloner un repository ou un gist

	git clone path_du_repository_ou_du_gist path_du_repertoire_a_creer_en_local
	
### Changer d'éditeur de texte par défaut globalement

	git config --global core.editor "vi"
	
### Liste des configurations

	git config --list --show-origin

### Votre identité

La première chose à faire après l’installation de Git est de renseigner votre nom et votre adresse de courriel. 
Les validations dans Git utilisent cette information et elle est indélébile dans toutes les validations que vous pourrez réaliser :

$ git config --global user.name "John Doe"  
$ git config --global user.email johndoe@example.com

Cette étape n’est nécessaire qu’une fois si vous passez l’option --global, parce que Git utilisera toujours cette information pour tout ce que votre utilisateur fera sur ce système. Si vous souhaitez surcharger ces valeurs avec un nom ou une adresse de courriel différents pour un projet spécifique, vous pouvez lancer ces commandes sans option --global lorsque vous êtes dans ce projet.
