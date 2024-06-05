# Exercice 9

1- Sélectionner les produits plus cher que les chaussures en utilisant la commande ALL

```mysql
SELECT *
FROM `produits`
WHERE `prix` > ALL (
  SELECT `prix`
  FROM `produits`
  WHERE `nom` LIKE '%chaussures%'
);
```

2- Sélectionner les clients qui ne sont pas dans Paris en utilisant la commande ANY

```mysql
SELECT *
FROM clients cl
WHERE cl.code_postal = ANY (
  SELECT v.code_postal
  FROM villes v
  WHERE `ville` NOT LIKE "Paris"
);
```
