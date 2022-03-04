# Projet 5 - Segmentez des clients d'un site e-commerce

Openclassrooms parcours **Data Scientist**

## Problématique

[Olist](https://olist.com/), une entreprise brésilienne qui propose une solution de vente sur les
marketplaces en ligne, souhaite une segmentation des clients que ses équipes d'e-commerce pourront
utiliser au quotidien pour leurs campagnes de communication.

## Les données

Olist a fournit une [base de données](https://www.kaggle.com/olistbr/brazilian-ecommerce) anonymisée
comportant des informations sur l’historique de commandes, les produits achetés, les commentaires de
satisfaction, et la localisation des clients depuis janvier 2017.

## Mission

- **comprendre les différents types d'utilisateurs**, grâce à leur comportement et à leurs données
  personnelles, en regroupant des clients de profils similaires. Ces catégories pourront être
  utilisées par l’équipe Marketing pour mieux communiquer.

- **fournir à l’équipe marketing une description actionable** de votre segmentation et de sa logique
  sous-jacente pour une utilisation optimale

- **une proposition de contrat de maintenance**, (fréquence à laquelle la segmentation doit être
  mise à jour pour rester pertinente), basée sur une analyse de la stabilité des segments au cours
  du temps.

La segmentation proposée doit être :

- sur l’ensemble des clients
- différencier les bons et moins bons clients en termes de commandes et de satisfaction
- exploitable et facile d’utilisation par notre équipe Marketing.

## Plan du projet

Le plan de ce projet ce trouve en plus de détail dans le document
[project_plan.md](./project_plan.md).

## Livrables de ce projet

### [P5_01_analyse.ipynb](./P5_01_analyse.ipynb)

- Compréhension du problème
- Import et nettoyage des données
- Analyse exploratoire
- Feature engineering

### [P5_02_essais.ipynb](./P5_02_essais.ipynb)

- Essais des différentes approches de modélisation.
- Le modèle final sélectionné

### [P5_03_simulation.ipynb](./P5_03_simulation.ipynb)

- Simulation pour déterminer la fréquence nécessaire de mise à jour du modèle de segmentation, pour
  définir le délai de maintenance du modèle (contrat de maintenance)

### [P5_04_support.pdf](./P5_04_support.pdf)

- Présentation et conclusion

## Compétences évaluées

- [ ] Mettre en place le modèle d'apprentissage non supervisé adapté au problème métier
- [ ] Transformer les variables pertinentes d'un modèle d'apprentissage non supervisé
- [ ] Adapter les hyperparamètres d'un algorithme non supervisé afin de l'améliorer
- [ ] Évaluer les performances d’un modèle d'apprentissage non supervisé
