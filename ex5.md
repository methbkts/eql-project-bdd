# Exercice 5

1- Rechercher les produits par prix croissant

```mysql
SELECT *
FROM `produits`
ORDER BY `prix`;
```

2- Rechercher les produits par prix décroissant en limitant le nombre de résultats à 10

```mysql
SELECT *
FROM `produits`
ORDER BY `prix` DESC
LIMIT 10
```

3- Sélectionner les client ordonnés par code postal croissant en utilisant l’alias id_client pour la
colonne id

```mysql
SELECT `id` AS `id_client`
FROM `clients`
ORDER BY `code_postal`;
```

4- Sélectionner les chaussures puis les robes dans une seule requête

```mysql
SELECT *
FROM `produits`
WHERE `nom` LIKE '%chaussures%'
UNION
SELECT *
FROM `produits`
WHERE `nom` LIKE '%robe%';
```

5- Sélectionner les codes postaux de la table villes et concaténer les codes postaux de la table
client. Utiliser UNION et UNION ALL, quelle différence observez vous ?

```mysql
# sans doublons
SELECT `code_postal`
FROM `villes`
UNION
SELECT `code_postal`
FROM `clients`;

# avec doublons
SELECT `code_postal`
FROM `villes`
UNION ALL
SELECT `code_postal`
FROM `clients`;
```
