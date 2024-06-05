# Exercice

1- Rechercher les clients et leur ville en effectuant une jointure entre les tables clients et villes,
mettre un alias pour les colonnes code_postal afin d’identifier leur table d’appartenance

```mysql
SELECT c.id, c.nom, c.prenom, c.age, c.email, c.adresse, v.ville, c.pays, c.code_postal AS cp1, v.code_postal AS cp2
FROM clients c
JOIN villes v
ON c.code_postal = v.code_postal;
```

2- Depuis la requête précédente, effectuez les 3 types de jointures, qu’observez-vous ?

```mysql
SELECT c.id, c.nom, c.prenom, c.age, c.email, c.adresse, v.ville, c.pays, c.code_postal AS cp1, v.code_postal AS cp2
FROM clients c
JOIN villes v
ON c.code_postal = v.code_postal;

SELECT c.id, c.nom, c.prenom, c.age, c.email, c.adresse, v.ville, c.pays, c.code_postal AS cp1, v.code_postal AS cp2
FROM clients c
LEFT JOIN villes v
ON c.code_postal = v.code_postal;

SELECT c.id, c.nom, c.prenom, c.age, c.email, c.adresse, v.ville, c.pays, c.code_postal AS cp1, v.code_postal AS cp2
FROM clients c
RIGHT JOIN villes v
ON c.code_postal = v.code_postal;
```

3- Depuis la table details_commandes, effectuez les jointures nécessaire pour sélectionner le
numéro de commande, la date de la commande, le produit commandé et la quantité

```mysql
SELECT dc.commande_id AS numero_commande, c.date_commande, p.nom, dc.quantite
FROM details_commandes dc
JOIN commandes c
ON dc.commande_id = c.id
JOIN produits p
ON dc.produit_id = p.id;
```

4- Depuis la requête précédente rajoutez une jointure avec la table clients afin de voir apparaitre le
client à l’origine de la commande (nom et prénom)

```mysql
SELECT dc.commande_id AS numero_commande, c.date_commande, p.nom, dc.quantite, cl.nom, cl.prenom
FROM details_commandes dc
JOIN commandes c
ON dc.commande_id = c.id
JOIN produits p
ON dc.produit_id = p.id
JOIN clients cl
ON c.client_id = cl.id;
```

5- Depuis la requête précédente rajoutez la jointure avec la table villes pour ajouter la ville
d’appartenance du client dans la séléction

```mysql
SELECT dc.commande_id AS numero_commande, c.date_commande, p.nom, dc.quantite, cl.nom, cl.prenom, v.ville
FROM details_commandes dc
JOIN commandes c
ON dc.commande_id = c.id
JOIN produits p
ON dc.produit_id = p.id
JOIN clients cl
ON c.client_id = cl.id
JOIN villes v
ON cl.code_postal = v.code_postal;
```
