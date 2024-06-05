# Exercice 7

1- Sélectionner le nom des produits n’ayant jamais été commandés

```mysql
SELECT `nom`
FROM `produits`
WHERE `id` NOT IN
(SELECT `produit_id`
FROM `details_commandes`);
```

2- Dans la table villes rechercher les villes sans doublons pour lesquelles on a un enregistrement
dans la table client (2 solutions, avec et sans jointure)

```mysql
SELECT DISTINCT `ville`
FROM `villes` v
JOIN `clients` c
ON c.code_postal = v.code_postal;

SELECT DISTINCT `ville`
FROM `villes`
WHERE `code_postal` IN
(SELECT `code_postal`
FROM `clients`);
```

3- Sans faire de jointure, sélectionner le détail des commandes pour le client numéro 1

```mysql
SELECT *
FROM `details_commandes`
WHERE commande_id IN
(SELECT id
FROM commandes
WHERE client_id =1);
```

4- Sélectionner les dates des commandes des clients habitant sur Paris de 2 manières :

- 4.1- Avec des jointures mais sans sous requête

```mysql
SELECT `date_commande`
FROM `commandes`
WHERE `client_id` IN
(
SELECT `id`
FROM `clients` c
JOIN `villes` v ON c.`code_postal` = v.`code_postal`
WHERE v.`ville` = "Paris"
);
```

- 4.2- Sans jointure dans la requête principale mais avec une jointure dans la sous-requête

```mysql
SELECT c.`date_commande`
FROM `commandes` c
JOIN `clients` cl ON c.`client_id` = cl.`id`
JOIN `villes` v ON cl.`code_postal` = v.`code_postal`
WHERE v.`ville` = "Paris";
```
