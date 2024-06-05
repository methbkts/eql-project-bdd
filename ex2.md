# Exercice 2

1- Rechercher tous les produits qui ont un prix compris entre 24,99€ et 49,99€ (inclus)

```mysql
SELECT *
FROM `produits`
WHERE `prix` >= '24.99' AND `prix` <= '49.99';
```

2- Rechercher le nom des produits ayant un prix inférieur à
89,99€ (exclu) et supérieur à 24,99€ (inclu)

```mysql
SELECT `nom`
FROM `produits`
WHERE `prix` >= '24.99' AND `prix` < '89.99';
```

3- Afficher les produits «Jupe en jean» et «Robe cache-coeur»

```mysql
SELECT *
FROM `produits`
WHERE `nom` = 'Jupe en jean' OR `nom` = 'Robe cache-coeur';
```

4- Rechercher les numéros de commande contenant plus de 5 pantalons noir et les numéros
de commande contenant plus de 3 chapeaux en paille.

```mysql
SELECT `commande_id`
FROM `details_commandes`
WHERE `produit_id` = '5' AND `quantite` > '5';

SELECT `commande_id`
FROM `details_commandes`
WHERE `produit_id` = '7' AND `quantite` > '3';
```
