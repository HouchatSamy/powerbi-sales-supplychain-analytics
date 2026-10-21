# Power BI — Sales & Supply Chain Analytics

Ce dépôt regroupe mes travaux décisionnels et analytiques réalisés avec **Microsoft Power BI**.

L’objectif de ce projet est de concevoir un rapport interactif permettant de piloter et d'analyser les ventes, les livraisons (Supply Chain), les objectifs commerciaux et la rentabilité globale de l’entreprise selon plusieurs dimensions :

- **Produits & Catégories** : performance par gamme et prix catalogue ;
- **Clients & Segments** : segmentation de la clientèle et fidélisation ;
- **Régions & Canaux de vente** : couverture géographique et efficacité commerciale ;
- **Analyse temporelle** : tendances, saisonnalités et évolutions périodiques ;
- **Rentabilité** : chiffre d’affaires, remises, coûts de revient et marges ;
- **Supply Chain** : délais de livraison, retards, qualité de service et taux de service (OTIF) ;
- **KPI & Objectifs** : suivi des indicateurs clés de performance et atteinte des objectifs.

---

## Modèle de données & Schéma en étoile

Le modèle relationnel repose sur un **schéma en étoile (Star Schema)** reliant des tables de faits et des tables de dimensions standardisées (dossier `Donnees_CSV/`) :

### Tables de dimensions
* `DimClient.csv` : identifiants, profils et segments clients ;
* `DimProduit.csv` : nomenclature produits, catégories et tarification ;
* `DimRegion.csv` : hiérarchie géographique et secteurs commerciaux ;
* `DimCanal.csv` : canaux de distribution (direct, distributeurs, web) ;
* `DimDate.csv` : table calendrier continue et gestion des périodes fiscales.

### Tables de faits
* `FactVentes.csv` : transactions de vente, volumes, montants bruts, remises, coûts et retours ;
* `FactLivraisons.csv` : commandes, dates promises, dates réelles d'expédition et statuts de service ;
* `FactObjectifs.csv` : quotas et objectifs commerciaux cibles par période, canal et région.

### Paramètres
* `ParamRemise.csv` : table de simulation et gestion des seuils de remises additionnelles.

---

## Contenu du dépôt

* `powerbi-sales-supplychain-analytics.pbix` : rapport Power BI Desktop complet avec modèle de données, mesures DAX et tableaux de bord interactifs ;
* `Donnees_CSV/` : ensemble des jeux de données sources (tables de faits, de dimensions et paramètres) ;
* `README.md` : documentation de présentation du projet.

---

## Compétences mises en pratique

* **ETL & Préparation de données** : extraction, nettoyage et transformation avec Power Query ;
* **Modélisation dimensionnelle** : conception du schéma en étoile, cardinalités (1-*), relations actives/inactives et gestion de la table Date ;
* **Calculs & Logique DAX** : mesures d'agrégation, calculs de ratios, fonctions de Time Intelligence (`SAMEPERIODLASTYEAR`, `YTD`, `TOTALYTD`), filtres de contexte (`CALCULATE`, `FILTER`) ;
* **Data Visualisation & Storytelling** : tableaux de bord ergonomiques, cartes KPI, filtres croisés et aides visuelles à la décision ;
* **Analyse de performance métier** : pilotage du chiffre d'affaires, marge commerciale et suivi des engagements logistiques (Supply Chain).

---

## Consultation du rapport

1. Installer **Microsoft Power BI Desktop** ;
2. Cloner ou télécharger le dépôt :
   ```bash
   git clone https://github.com/hctsamyUCT/powerbi-sales-supplychain-analytics.git
   ```
3. Ouvrir le fichier `powerbi-sales-supplychain-analytics.pbix` dans Power BI Desktop ;
4. Si nécessaire, réajuster le chemin de la source de données vers le dossier local `Donnees_CSV/` (*Transformer les données > Paramètres de la source de données*) ;
5. Cliquer sur **Actualiser**.