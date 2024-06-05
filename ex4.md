# Exercice 4

1- Rechercher dans la table clients, le nom et le prénom des personnes ayant un nom
commençant par D ou finissant par R

```mysql
SELECT nom, prenom
FROM `clients`
WHERE `nom` LIKE 'D%' OR `nom` LIKE '%R';
```

2- Sélectionner le nom et le prix des 3 jeans classé par taille (2 solutions)

```mysql
SELECT `nom`, `prix`
FROM `produits`
WHERE `nom` LIKE '%jean taille _%';
```

3- Sélectionner tous les produits sauf les produits en jean

```mysql
SELECT *
FROM `produits`
WHERE `nom` NOT LIKE '%jean%';
```

4- Rechercher les commandes effectuées en février pour toutes les années.

```mysql
SELECT *
FROM `commandes`
WHERE `date_commande` LIKE '%-02-%';
```

5- Rechercher les clients habitant dans la ville de Paris

```mysql
SELECT *
FROM `clients`
WHERE `code_postal` LIKE '75%';
```

6- Rechercher les clients n’habitant pas dans la ville de Paris

```mysql
SELECT *
FROM `clients`
WHERE `code_postal` NOT LIKE '75%';
```
