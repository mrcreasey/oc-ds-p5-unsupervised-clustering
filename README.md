# Unsupervised segmentation of customers of an e-commerce site

## Overview

[Olist](https://olist.com/) is a Brazilian company that offers a sales solution for online
marketplaces. The aim of this project is to:

- **create an actionable customer segmentation** that its e-commerce teams can use on a daily basis
  for their communication campaigns;
- **analyse the stability of the segments over time**, in order to determine the frequency at which
  the segmentation must be updated to remain relevant, (for a maintenance contract)

## Motivation

This is project 5 for the **Master in Data Science** (in French, BAC+5) from OpenClassrooms.

The project demonstrates :

- clustering algorithms (Kmeans, Agglomerative Clustering, DBSCAN)
- evaluation of cluster consistency, shape and stability
- visualisation of clusters in 2 dimensions (t-SNE, PCA)
- evolution of clusters over time

## Requirements

To run the notebooks, the dataset must be placed in a DATA_FOLDER ('data/raw'). Python libraries are
listed in `requirements.txt`. Each notebook also includes a list of its own requirements, and a
procedure for `pip install` of any missing libraries.

**Data**: Olist has provided an anonymized database at
<https://www.kaggle.com/olistbr/brazilian-ecommerce>, (~130Mb) with information on order history,
products purchased, satisfaction comments, and customer location since January 2017.

**Python libraries** :
`numpy, pandas, matplotlib, seaborn, scikit-learn, scipy, missingno, dython, squarify, yellowbricks, holoviews, bokeh`

## Files

_Notes_ : Files are in French. _As requested for the project, the jupyter notebooks have not been
"cleaned up" : the focus is on setting up, tuning, visualising and evaluating unsupervised learning
algorithms_.

_Custom functions created in this project for data preprocessing, statistical analysis and data
visualisation are encapsulated within each notebook, to avoid importing and versioning custom
libraries. Open https://nbviewer.org/ and paste notebook GitHub url if GitHub takes too long to
render._

- [P5_01_analyse.ipynb](./P5_01_analyse.ipynb): Data cleaning, exploratory analysis, feature
  engineering
  <a href="https://colab.research.google.com/github/mrcreasey/oc-ds-p5-unsupervised-clustering/blob/main/P5_01_analyse.ipynb" target="blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open in Colab"/></a>

- [P5_02_essais.ipynb](./P5_02_essais.ipynb): Trials of different modeling approaches and selection
  of final model
  <a href="https://colab.research.google.com/github/mrcreasey/oc-ds-p5-unsupervised-clustering/blob/main/P5_02_essais.ipynb" target="blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open in Colab"/></a>

- [P5_03_simulation.ipynb](./P5_03_simulation.ipynb): Simulation to determine the necessary
  frequency of updating the segmentation model (maintenance contract)
  <a href="https://colab.research.google.com/github/mrcreasey/oc-ds-p5-unsupervised-clustering/blob/main/P5_03_simulation.ipynb" target="blank"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open in Colab"/></a>

- [P5_04_support.pdf](./P5_04_support.pdf): Presentation and conclusion

## Approach

### Data Cleaning

- joining 8 tables: aggregation by unique customer, elimination of incomplete orders

### Exploration of available dimensions & Feature Engineering

Creation / selection of indicators of customer behaviour :

- Customer and vendor geolocation : distance between customer and vendor
- Delivery delay: delivery date - forecast date
- Customer satisfaction : Average rating of customer reviews
- Product category simplification; customer favourite product category
- Customer number of commands, preferred payment method and number of payments

### Segmentation (clustering)

- **RFM** Segmentation (Recency, Frequency, Money)
- **KMeans** segmentation - choice of number of clusters K:
  - Consistency (inertia/distortion, Calinski Harabasz, Davies_Bouldin)
  - Shape (silhouette score)
  - Stability (reproducibility on sub-samples, seasonality)
  - Fit time
- **(Hierarchical) Agglomerative Clustering**: Ward, Average, Complete Linkage, Dendrograms
- **DBSCAN** (Density-Based Spatial Clustering of Applications with Noise): Hyperparameter tuning (epsilon, min samples)

### Segment visualisation

- Silhouette plots, Multi Dimensional Scaling (MDS) plot of intercluster distance
- Radar (spider) plots, line (snake) plots, bubble plots, box plots
- Feature importance: PCA visualisation, t-SNE plots coloured by segment / feature

### Stability Simulation

- evaluation of stability (last year of data), by 1-month to 6-month timesteps
- ARI score (adjusted rand index) to measure cluster similarity
- Stability visualisation (Sankey diagrams)

### Conclusions

- Most distinct segmentation based on 5 features : ['MonetaryValue', 'Frequency', 'review_score',
  'mean_nb_payments', 'delivery_delay']: less important features add "noise".
- Best consistency, silhouette scores and stability for 7 customer segments, characterised by small / medium / large purchase,
  frequent / infrequent purchase, and level of satsifaction
- Satisfaction very sensitive to departure from forecast delivery time
- Segments are stable for 2 months; stability depends on season

### Suggestions for Improvement

- Better understand why customers are dissatisfied: specific to certain vendors, product categories?
- Explore further the characteristics of each segment: favourite categories, favoured payment
  methods, number of payments
- Add categorical variables to segmentation: use Kprototype with one-hot encoded favorite categories
- conduct a NLP (Natural Language) analysis of customer review comments and titles
- Segmentation by Kmeans seems very unstable: Check segment stability for different start dates
- 80% of customer purchases concentrated in only 3 of 26 states (SP, PR, MG) - why?

## Features (keywords)

- clustering algorithms (Kmeans, Agglomerative Clustering, DBSCAN)
- evaluation of cluster consistency(), shape (silhouette) and stability
- visualisation of clusters in 2 dimensions (t-SNE, PCA, MDS)
- visual comparison of cluster features (radar plots, line plots)
- evolution of clusters over time (Sankey diagram)

## Skills acquired

- Set up the unsupervised learning model adapted to the business problem
- Transform relevant variables of an unsupervised learning model
- Adapt the hyperparameters of an unsupervised algorithm in order to improve it
- Evaluate the performance of an unsupervised learning model
