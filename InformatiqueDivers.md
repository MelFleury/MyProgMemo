### Difference gzip and zip
For instance, gzip excels when working with **larger files or streams of data** because it provides continuous compression over single file content. 
On the other hand, zip shines by offering higher overall compression ratios on **smaller multiple files packed together**

### Remove software
```python
sudo apt remove <name_program>
```

### Install software
```python
sudo apt install <name_program>
```

### Amazon S3
Amazon S3 est un service de stockage d'objets entièrement géré qui a été lancé par Amazon Web Service (AWS) en 2006. L'objectif, au moment de sa conception, était de créer un service capable de stocker, de traiter et d'extraire n'importe quelle quantité de données à partir de n'importe quel endroit du web, ce qui en fait un composant essentiel de plusieurs applications modernes axées sur les données. 
Les principaux composants sont :
    - **Objets** (*object*): Les données sont stockées sous forme d'"objets" - des fichiers de n'importe quel type ou taille, et toutes les métadonnées qui décrivent le fichier. Chaque objet peut atteindre une taille de 5 To.
    - **Seaux** (*bucket*): sont des conteneurs d'objets. Si vous souhaitez stocker des données dans Amazon S3, vous devez d'abord créer un godet et spécifier un nom de godet et une région AWS. Ensuite, les données sont téléchargées sous forme d'objets dans le panier Amazon S3.  
    - **Touches** (*keys*): Chaque objet d'un seau est identifié par une "clé" unique, semblable à un nom de fichier.

### Droits Unix
Exemple : *drwxr-xr-x*
    - *d* = directory otherwise "-"
    - *rwx* = personal rights (read, write, execute)
    - *r-x* = droits du groupe (read, execute)
    - *r-x* = droit tout loger (read, execute)
On peut supprimer ses propres droits. Ex. Éviter de supprimer des fichiers très importants par exemple

/!\ La commande *rm -rf* (f = force) change les droits des fichiers du path avant de les supprimer

### commande "man"
```bash
man <nom_logiciel> # manuel du nom logiciel
```

### Bash file
Interpréteur de ligne de commande

### Batch file
Le terme batch désigne en informatique l'automatisation d'une suite de commandes exécutées en série sur un ordinateur sans qu'il soit nécessaire qu'un opérateur intervienne pour réaliser cette opération. On le traduit la plupart du temps par le terme "lot" en français et par l'expression "traitement par lots".
--> source https://www.journaldunet.fr/web-tech/dictionnaire-du-webmastering/1203563-batch-definition-traduction/

### Connexion to a server
1. Generate a ssh key : `ssh-keygen -t rsa`
2. Sending public key (.pub) to admin server
3. Final connexion : `ssh -A -i ~/.ssh/id_rsa <personal_name_server>`
   Ex. `ssh -A -i ~/.ssh/id_rsa mfleury@134.214.213.148`

### Change sudo password
`sudo passwd root`

## MINIO
### Copy
```bash
mc cp SOURCE TARGET
```
