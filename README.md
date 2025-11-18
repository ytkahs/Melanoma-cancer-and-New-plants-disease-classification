# 🚀 Melanoma & Plant Disease Classification | Deep Learning avec PyTorch

## 🌟 Aperçu du Projet

Ce projet académique explore et compare différentes **stratégies de Deep Learning (DL)** pour résoudre des problèmes de **classification d'images** critiques, en se concentrant sur les maladies des plantes et le cancer du mélanome. L'objectif principal est de développer des classifieurs efficaces en utilisant la bibliothèque **PyTorch** et d'analyser l'impact des choix architecturaux et des hyperparamètres.

---

## 🎯 Objectifs Clés de l'Analyse

Nous étudions l'efficacité et les performances de deux approches de modélisation majeures : l'apprentissage *from scratch* et le *Transfer Learning*.

1.  **Exploration de PyTorch :** Se familiariser avec le framework (gestion du chargement des données, définition des architectures, boucle d'apprentissage).
2.  **Analyse de l'Impact :** Comprendre l'influence de la taille/profondeur du réseau, du *Learning Rate*, de la *Batch Normalization*, etc.
3.  **Comparaison Stratégique :** Évaluer et justifier les performances d'un **CNN *From Scratch*** par rapport aux techniques de **Transfer Learning** (Extracteur de Features vs. Fine-tuning).

---

## 📂 Datasets

L'ensemble des développements et des analyses est appliqué à deux bases de données d'images distinctes, toutes deux issues de Kaggle :

| Dataset | Description | Liens (Kaggle) |
| :--- | :--- | :--- |
| **New Plants Disease Dataset** | Classification des images de feuilles pour la détection et l'identification de **maladies des plantes**. | [Lien vers le Dataset](https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset) |
| **Melanoma Cancer Dataset** | Classification des images de lésions cutanées pour la détection du **cancer du mélanome**. | [Lien vers le Dataset](https://www.kaggle.com/datasets/bhaveshmittal/melanoma-cancer-dataset) |

---

## 🧠 Approches de Modélisation

Le projet structure les développements autour de deux méthodes principales de construction de **Réseaux Neuronaux Convolutifs (CNN)**.

### 1. Construction d'un CNN *From Scratch*

Cette approche implique la conception et l'entraînement d'un **réseau neuronal convolutif (CNN)** à partir de poids initialisés de manière aléatoire, sans aucune connaissance pré-entraînée.

* **Architecture Détaillée :** Définition complète des couches de **Convolution**, **Activation**, **Pooling** et **Normalisation** (incluant l'exploration de blocs résiduels ).
* **Hyperparamètres à l'Étude :**
    * Taille et Profondeur du réseau (nombre de filtres/couches).
    * Impact de la **Batch Normalization**.
    * Influence du **Taux d'apprentissage** (*Learning Rate*).

### 2. Application du *Transfer Learning*

Les performances sont comparées en exploitant des architectures puissantes pré-entraînées sur le vaste corpus **ImageNet**.

#### a. Extracteur de Features Figé (Feature Extractor)

Un modèle pré-entraîné (ex: VGG, ResNet) est utilisé, mais ses couches convolutives sont **figées** (non entraînées), agissant uniquement comme un extracteur de *features*. Les *features* extraites alimentent ensuite un petit réseau **Fully Connected (FC)** qui, lui, est entraîné pour la classification finale. 

#### b. Finetuning

Le réseau pré-entraîné est chargé, mais cette fois, **l'ensemble de ses poids** (y compris une partie ou la totalité des couches convolutives) sont légèrement **mis à jour (*finetuned*)** lors de l'entraînement. Cette technique vise à mieux adapter les *features* génériques d'ImageNet aux spécificités des images de mélanome et de maladies des plantes.

---

## 🚀 Installation & Lancement

Le projet nécessite l'environnement Python avec les bibliothèques suivantes.

```bash
# Installation recommandée
pip install torch torchvision sklearn seaborn matplotlib numpy
