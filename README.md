# Marketing campaign
Marketing Campaign Data Analysis and Modeling 

Segmenting customers based on these attributes enables businesses to tailor their marketing strategies and enhance customer satisfaction.
## Context
A response model can provide a significant boost to the efficiency of a marketing campaign by increasing responses.
The objective is to predict who will respond to an offer for a product or service.
## Inspiration
The main objective is to train a predictive model which allows the company to maximize the profit of the next marketing campaign.

## Source
The dataset is sourced from: [Kaggle](https://www.kaggle.com/datasets/rodsaldanha/arketing-campaign)


# Analyse

## Preprocessing

Problème : LabelEncoder impose un ordre numérique arbitraire aux catégories. Exemple :

Education = {“Basic” → 0, “Graduation” → 1, “Master” → 2, “PhD” → 3}
Cela pourrait induire une relation d’ordre inexistante et biaiser les modèles, notamment les distances (KNN, SVM, etc).

👉 Alternatives plus adaptées :

- One-Hot Encoding:	Ne suppose aucun ordre, robuste. Ajoute beaucoup de colonnes (curse of dimensionality)
- Target Encoding:	Encode selon la moyenne de la cible (Response). Risque de surapprentissage si pas encodé correctement (fuite de données)
- OrdinalEncoder avec catégories définies:	Permet un encodage ordonné si l’ordre est logiqu. Pas applicable si l’ordre n’existe pas

Dans ce cas :

Education → on peut supposer un ordre raisonnable (Basic < 2n Cycle < Master < PhD), donc OrdinalEncoder est plus juste que LabelEncoder

Marital_Status → aucun ordre naturel → One-Hot Encoding préférable
