# Wine Quality — Analyse ACP

Projet de data science visant à identifier les **axes clés de différenciation** des vins à partir de leurs propriétés chimiques, via une **Analyse en Composantes Principales (ACP)**.

## Objectif

Réduire la dimensionnalité d'un dataset de vins (11 variables chimiques) pour :
- Identifier les axes de différenciation (acidité, sucre, SO2, minéralité…)
- Visualiser les vins en 2D/3D
- Comprendre la structure chimique des rouges et des blancs

## Dataset

- Source : [UCI Machine Learning Repository — Wine Quality](https://archive.ics.uci.edu/ml/datasets/wine+quality)
- 6497 vins (1599 rouges, 4898 blancs)
- 11 variables chimiques + 1 note de qualité (3 à 9)

## Démarche

1. **EDA** : distributions, corrélations, détection de redondances
2. **Préprocessing** : encodage du type, standardisation
3. **ACP** en 3 temps :
   - Dataset complet (5 axes, 79.9%)
   - Rouges seuls (4 axes, 70.8%)
   - Blancs seuls (5 axes, ~80%)
4. **Interprétation** : loadings, cercles de corrélation, projections colorées
5. **Analyse différenciée** : comparaison des structures rouges vs blancs

## Résultats principaux

| Axe | Rouges | Blancs |
|---|---|---|
| PC1 | Acidité / structure | Moelleux vs sec |
| PC2 | SO2 / conservation | Acidité |
| PC3 | Qualité perçue | Défaut vs qualité |
| PC4 | Minéralité | Minéralité |

**Enseignements clés** :
- La structure chimique diffère selon le type (rouge/blanc)
- La **minéralité** (chlorures + sulphates) est un axe universel
- La **qualité** n'est jamais le premier axe : elle apparaît en PC3, avec une corrélation faible (|r| max ≈ 0.30)
- L'**acidité volatile** est le marqueur commun d'un défaut

## Structure du projet
