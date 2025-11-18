# Melanoma-cancer-and-New-plants-disease-classification

Ce projet a pour but d'explorer et de comparer différentes techniques de Deep Learning (apprentissage profond) pour des tâches de classification d'images, en utilisant la bibliothèque PyTorch.

L'objectif principal est de développer des classifieurs efficaces sur deux ensembles de données distincts et d'analyser l'impact des choix d'architecture, des hyperparamètres et des stratégies d'entraînement (apprentissage from scratch vs Transfer Learning).


Les analyses et les développements sont menés sur deux bases de données de Kaggle :

New Plants Disease Dataset : Classification des maladies des plantes
Melanoma Cancer Dataset : Classification des images de lésions pour la détection du cancer du mélanome.

Le projet est divisé en deux grandes approches de modélisation, appliquées à chacun des deux datasets.

1. Construction de CNN From Scratch
Un réseau neuronal convolutif (CNN) est conçu et entraîné entièrement sans l'utilisation de poids pré-entraînés.

Architecture : Définition complète des couches de Convolution, d'Activation, de Pooling et de Normalisation (incluant l'exploration de blocs résiduels).
Analyse d'impact : Étude approfondie de l'influence des hyperparamètres et des choix d'architecture sur les performances, notamment :
Taille et Profondeur du réseau (nombre de filtres/couches).
Impact de la Batch Normalization.
Influence du Taux d'apprentissage (Learning Rate).

2. Application du Transfer Learning
Les performances du CNN from scratch sont comparées à celles obtenues en utilisant des architectures pré-entraînées sur ImageNet.

a. Extracteur de Features Figé (Feature Extractor)
Un réseau pré-entraîné (par exemple, VGG, ResNet) est utilisé, mais ses couches convolutives sont figées (non entraînées) pour servir uniquement d'extracteur de features. Ces features sont ensuite utilisées comme entrée pour un petit réseau Fully Connected (FC) qui, lui, est entraîné pour la classification.

b. Finetuning
Le réseau pré-entraîné est chargé et l'ensemble de ses poids, y compris ceux des couches convolutives, sont légèrement modifiés (finetuned) lors de l'entraînement, pour une meilleure adaptation aux spécificités des datasets de maladies des plantes et de mélanome.
