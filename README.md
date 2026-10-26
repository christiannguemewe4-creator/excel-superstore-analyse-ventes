# Analyse des ventes Superstore – Tableau de bord Excel

Projet d'analyse de données réalisé dans **Excel** (Power Query, tableaux de synthèse, graphiques) sur le dataset **Superstore** (Kaggle) : les ventes d'un distributeur américain de fournitures de bureau, de mobilier et de matériel technologique, de 2014 à 2017.

Le projet est construit comme une mission réelle : un **manager prépare la revue annuelle avec la direction** et demande un tableau de bord d'une page pour répondre à 5 questions, avec 3 recommandations concrètes.

   ![Tableau de bord](Sans%20titredashboard.png)

📊 [Fichier Excel du projet](projet_superstore.xlsx)

---

## Données

- **Source :** [Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final) (Kaggle)
- **Volume :** 9 994 lignes de commande, 5 009 commandes, 793 clients, période 2014–2017
- **Monnaie :** dollars américains (USD)

## Nettoyage (Power Query)

- Dates converties en type Date (`Order Date`, `Ship Date`)
- Types définis : montants en nombre décimal, `Quantity` en entier, `Postal Code` en texte
- Contrôle qualité : aucune valeur vide ni erreur, aucun doublon
- Colonne `Country` supprimée (valeur unique : United States)
- Colonnes `Année` et `Mois` ajoutées pour l'analyse temporelle
- **9 994 lignes conservées**

---

## Les 5 questions du manager

### Q1 – Combien gagne-t-on vraiment ?

| Indicateur | Valeur |
|---|---|
| Ventes totales | 2 297 201 $ |
| Profit total | 286 397 $ |
| Marge | 12,5 % |
| Commandes | 5 009 |
| Panier moyen | 459 $ |

Sur 100 $ vendus, l'entreprise garde **12,50 $** de profit.

### Q2 – Est-ce que l'activité progresse ?

| Année | Ventes | Profit | Marge | Évolution des ventes |
|---|---|---|---|---|
| 2014 | 484 247 $ | 49 544 $ | 10,2 % | – |
| 2015 | 470 533 $ | 61 619 $ | 13,1 % | -2,8 % |
| 2016 | 609 206 $ | 81 795 $ | 13,4 % | +29,5 % |
| 2017 | 733 215 $ | 93 439 $ | 12,7 % | +20,4 % |

**Oui.** Après une légère baisse en 2015, les ventes accélèrent : **+51 % entre 2014 et 2017**. Le profit progresse encore plus vite (**+89 %**). En 2015, malgré la baisse des ventes, la marge passe de 10,2 % à 13,1 %.

### Q3 – Où perd-on de l'argent ?

| Catégorie | Ventes | Profit | Marge |
|---|---|---|---|
| Technology | 836 154 $ | 145 455 $ | 17,4 % |
| Office Supplies | 719 047 $ | 122 491 $ | 17,0 % |
| **Furniture** | 741 999 $ | 18 451 $ | **2,5 %** |

Le **mobilier** ne dégage que 2,5 % de marge. Trois sous-catégories sont **en perte** :

| Sous-catégorie | Profit | Remise moyenne |
|---|---|---|
| Tables | -17 725 $ | 26 % |
| Bookcases | -3 473 $ | 21 % |
| Supplies | -1 189 $ | 8 % |

Tables et Bookcases sont vendues avec des remises élevées (contre 15,6 % en moyenne). Supplies perd de l'argent malgré une remise faible : son prix ou son coût est à revoir.

### Q4 – Quelles régions et quels clients sont les plus rentables ?

| Région | Ventes | Profit | Marge |
|---|---|---|---|
| West | 725 458 $ | 108 418 $ | 14,9 % |
| East | 678 781 $ | 91 523 $ | 13,5 % |
| South | 391 722 $ | 46 749 $ | 11,9 % |
| **Central** | 501 240 $ | 39 706 $ | **7,9 %** |

- **West et East** sont les régions les plus rentables. **Central** a la marge la plus faible.
- Plusieurs États sont **en perte** : Texas (-25,7 k$), Ohio (-17,0 k$), Pennsylvanie (-15,6 k$), Illinois (-12,6 k$).
- Par segment, les marges sont proches : Home Office 14,0 %, Corporate 13,0 %, Consumer 11,5 %.
- **155 clients sur 793** (20 %) font perdre de l'argent sur l'ensemble de leurs achats.

### Q5 – Nos remises nous coûtent-elles trop cher ?

| Remise | Lignes | Ventes | Profit | Marge |
|---|---|---|---|---|
| 0 % | 4 798 | 1 087 908 $ | 320 988 $ | 29,5 % |
| 1–10 % | 94 | 54 369 $ | 9 029 $ | 16,6 % |
| 11–20 % | 3 709 | 792 153 $ | 91 756 $ | 11,6 % |
| **21–30 %** | 227 | 103 227 $ | **-10 369 $** | -10,0 % |
| **31–50 %** | 310 | 195 315 $ | **-48 448 $** | -24,8 % |
| **Plus de 50 %** | 856 | 64 229 $ | **-76 559 $** | -119,2 % |

**Oui.** Le **seuil de perte se situe au-delà de 20 % de remise**. Les lignes vendues avec plus de 20 % de remise (14 % des lignes) font perdre **135 376 $**, soit l'équivalent de **près de la moitié du profit total**.

---

## Recommandations

1. **Plafonner les remises à 20 %**, sauf validation exceptionnelle. C'est le levier le plus fort : jusqu'à 135 k$ de profit récupérable.
2. **Revoir la politique commerciale du mobilier**, en priorité sur les Tables et les Bookcases (remises trop élevées), et revoir le prix ou le coût d'achat des Supplies.
3. **Analyser les États en perte** (Texas, Ohio, Pennsylvanie, Illinois) pour vérifier si les remises y sont plus fortes qu'ailleurs, et s'inspirer des pratiques de la région West.

---

## Outils et compétences

- **Excel** : Power Query (nettoyage, typage, contrôle qualité), formules (`SOMME.SI.ENS`), tableaux de synthèse, graphiques, tableau de bord d'une page
- **Analyse** : indicateurs clés (ventes, profit, marge, panier moyen), analyse temporelle, analyse de rentabilité par catégorie, région, segment et niveau de remise
- **Restitution** : conclusions chiffrées et recommandations orientées décision
