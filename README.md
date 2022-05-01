# 18_Base_article_scientifique
Créer une base Mongo, une collection, d’y insérer des données et de l’interroger grâce à Python. 

**************************************************************************************************************
## Contexte du projet :
Mise en place une base de données MongoDB, orientée documents, pour gérer l'accès à ces publications. 
Teste des datas grâce à un petit script Python.

**************************************************************************************************************
## les étapes suivantes pour réaliser le projet : 

- Rentrer dans mongodb : ```docker exec -it mongodb mongo -u root -p pass12345```
- Créer la base DBLP : ```use DBLP```
- Ajouter une collection publis : ```db.createCollection("publis")```
- Importer dans la base les données du fichier dblp.json : (après avoir importer le fichier dans le répertoir)
  - mettre le fichier dans le container : ```docker cp dblp.json <id container>:/dblp.json```
  - importer avec mongoimport : ```docker exec -it mongodb mongoimport -u=root -p=pass12345 --authenticationDatabase=admin --db=DBLP -c=publis --file=/dblp.json```
- Ecrire le script Python pour tester la base :

**************************************************************************************************************
## Le script Python *publications.py* contient :
- Compter le nombre de documents de la collection publis; 
- Lister tous les livres (type “Book”) ; 
- Lister les livres depuis 2014 ; 
- Lister les publications de l’auteur “Toru Ishida” ; 
- Lister tous les auteurs distincts ; 
- Trier les publications de “Toru Ishida” par titre de livre ; 
- Compter le nombre de ses publications ; 
- Compter le nombre de publications depuis 2011 et par type ; 
- Compter le nombre de publications par auteur et trier le résultat par ordre croissant ;

Tous les affichages se font dans la console.

**************************************************************************************************************
## En plus : script qui demande le chemin d'un fichier json, insére un ou plusieurs nouveaux documents, à partir de ce fichier, dans la collection publis.





