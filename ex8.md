# Exercice 8

1- Avec une sous-requête EXISTS sélectionner les villes pour lesquelles nous avons des clients

```mysql
SELECT DISTINCT ville
FROM villes v
WHERE EXISTS (
    SELECT cl.*
    FROM clients cl
    WHERE cl.code_postal = v.code_postal
);
```

2- Avec une sous-requête EXISTS sélectionner le nom des produits ayant déjà été commandé

```mysql
SELECT nom
FROM produits p
WHERE EXISTS (
    SELECT *
    FROM details_commandes dc
    WHERE p.id = dc.produit_id
);
```

3- Avec une sous-requête EXISTS sélectionner le nom des produits n’ayant jamais été commandé

```mysql
SELECT nom
FROM produits p
WHERE NOT EXISTS (
    SELECT *
    FROM details_commandes dc
    WHERE p.id = dc.produit_id
);
```
