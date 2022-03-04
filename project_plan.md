# Plan du projet

Ce document note les idées pour structurer le projet

- Les sections sont remplis itérativement, pas nécessairement en ordre

# 1. Compréhension du problème

## L'énoncé du problème

[Olist](https://olist.com/), une entreprise brésilienne qui propose une solution de vente sur les
marketplaces en ligne, souhaite une **segmentation des clients** que ses équipes d'e-commerce
pourront utiliser au quotidien pour leurs campagnes de communication.

## Objectifs commerciaux

- **comprendre les différents types d'utilisateurs**, grâce à leur comportement et à leurs données
  personnelles, en regroupant des clients de profils similaires. Ces catégories pourront être
  utilisées par l’équipe Marketing pour mieux communiquer.

- **fournir à l’équipe marketing une description actionable** de votre segmentation et de sa logique
  sous-jacente pour une utilisation optimale

- **une proposition de contrat de maintenance**, (fréquence à laquelle la segmentation doit être
  mise à jour pour rester pertinente), basée sur une analyse de la stabilité des segments au cours
  du temps.

## 1.3 Les objectifs d'analyse pré-exploratoire

## Critères de réussite

- les indicateurs de coportement sont identifiés
- les variables pour segmenter sont nettoyés

## Source d'information

# 2. Compréhension des données

**Sources des données** Les données d'olist sont à télécharger à
[cette adresse](https://www.kaggle.com/olistbr/brazilian-ecommerce)

## 2.1 Définition des données (metadata)

- read json metadata

## 2.2 Import des données

## 2.3 Décrire des données

- Evaluation de la qualité des données

## 2.4 Nettoyage des données

- Colonnes non-pertinentes
- Valeurs manquantes
- Outliers

# 3. Analyse exploratoire des données

## Analyses descriptives

## Analyses graphiques

## Valeurs aberrantes et anomalies

## Explorer les relations de données

# 4. Feature engineering

# 5. Essais de modélisation classiques (baseline)

**Objectifs** :

- comprendre l'importance des indicateurs
- créer une baseline pour justifier les modèles plus avancées

## RFM

Pour établir des segments de clients homogènes, la segmentation RFM prend en compte:

- la **Récence** (date de la dernière commande);
- la **Fréquence** des commandes; et
- le **Montant** (de la dernière commande ou sur une période donnée)

La segmentation RFM permet de cibler les offres, d'établir des segments basés sur la valeur des
clients et de prévenir l'attrition en identifiant des segments à risque.

### Références

- <https://www.definitions-marketing.com/definition/segmentation-rfm/>

## Pareto

- <https://www.e-marketing.fr/Thematique/academie-1078/fiche-outils-10154/analyse-Pareto-306757.htm>

# 6. Essais de modélisation non-supervisée

## Kmeans Simple

- Environ 4 à 5 segments, 3 ou 4 indicateurs

## Kmeans avancé

- Entre 8 et 12 segments, plusieurs indicateurs

# 7. Sélectionne du modèle final

# 8. Simulation de la stabilité des clusters (fréquence des mises à jours)
