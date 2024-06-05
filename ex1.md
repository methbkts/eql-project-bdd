# Exercice 1

1- Rechercher le « nom », le « prenom » et le «email » dans la table « clients »
correspondant au client n° 1

```mysql
SELECT `nom`, `prenom`, `email` FROM `clients` WHERE `id` = 1;
```

2- Recherche tous les noms des villes presentes dans la table « villes » sans aucun
doublon

```mysql
SELECT DISTINCT ville FROM villes;
```

3- Comptez les lignes presentes dans la table villes sans aucun doublons de nom de ville

```mysql
SELECT COUNT(DISTINCT ville) FROM villes;
```

4- Rechercher tous les produits qui ont un prix supérieur ou égal à 59,99€

```mysql
SELECT * FROM produits WHERE  prix >= 59.99;
```

5- Rechercher tous les produits qui ont un prix différent de 59,99€ (2 solutions)

```mysql
SELECT * FROM produits WHERE  prix != 59.99;
```
