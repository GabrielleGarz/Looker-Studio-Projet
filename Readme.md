# 📊 Projet de Business Intelligence - Dashboard Novatel (Looker Studio & BigQuery)

## 🎯 1. But du projet
Ce projet vise à concevoir un tableau de bord interactif et décisionnel sous **Looker Studio** afin d'analyser la performance commerciale, le comportement d'achat des clients et le suivi des opérations financières de l'entreprise **Novatel**.

---

## 📝 2. Description
Le projet couvre toute la chaîne de valeur de la donnée, de la modélisation dans le Data Warehouse jusqu'à la restitution visuelle :
1. Structuration d'un modèle de données en étoile dans **BigQuery**.
2. Nettoyage, préparation et transformation des données via des requêtes **SQL**.
3. Création d'une vue dédiée au reporting analytique.
4. Restitution visuelle et dynamique dans **Looker Studio** (KPIs, filtres, graphiques d'évolution).

---

## 🛠️ 3. Logiciels & Technologies utilisées

* **Google Cloud Platform (GCP) / BigQuery :** Entrepôt de données (Data Warehouse) pour le stockage et l'exécution des requêtes SQL.
* **SQL (Standard SQL) :** Langage de requête pour la transformation des données, la gestion des jointures et la création de vues.
* **Looker Studio :** Outil de Dataviz pour la création du tableau de bord et des filtres interactifs.
* **GitHub :** Versionnage des scripts SQL et centralisation de la documentation du projet.

---

## 📊 4. Données (Dataset `novatel`)

Le projet s'appuie sur une architecture en étoile basée sur le projet Google Cloud `ageless-thought-510710-m7` et le dataset `novatel` :

### 📈 Table de Faits
* **`fact_transactions`** : Centralise l'ensemble des transactions (dates, montants, clés étrangères vers les dimensions).

### 🏷️ Tables de Dimensions
* **`dim_client`** : Informations et profil des clients.
* **`dim_produit`** : Référentiel des produits.
* **`dim_poin_vente`** : Liste et localisation des points de vente.
* **`dim_type_operation`** : Catégories et types d'opérations.
* **`dim_date`** : Axe temporel pour l'analyse des tendances.

---

## ⚙️ 5. Vues SQL & Pipeline de Transformation

Afin d'optimiser les performances de Looker Studio, la logique de données est encapsulée dans BigQuery au travers de deux vues principales :

1. **`vw_transactions_clean`** : Vue intermédiaire assurant le nettoyage des données brutes (normalisation des formats, filtrage et cohérence).
2. **`vw_transactions_reporting