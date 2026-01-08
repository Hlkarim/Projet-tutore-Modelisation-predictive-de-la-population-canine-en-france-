
# 🐶 Modélisation Prédictive de la Population Canine en France

Ce projet, réalisé dans le cadre d'un Master 2, vise à prédire le nombre de chiens par commune en France en se basant sur des données socio-démographiques.

### 📋 Résumé du projet

* 
**Objectif :** Estimer la population canine pour optimiser les prises de décision (ex: implantation de rayons animalerie).


* 
**Données :** Croisement des bases **I-CAD** (Identification des Carnivores Domestiques) et **INSEE** sur la période 2013-2020.


* **Méthodologie :**
* Nettoyage avancé et imputation temporelle des données manquantes.


* Feature Engineering incluant le **Spatial Lag** (prise en compte du voisinage).


* Modélisation via **Random Forest**.



### 📊 Résultats clés

* 
**Performance :** Le modèle atteint un ** de 0.90** avec une erreur médiane absolue (MAE) de **38 chiens** par commune.


* 
**Facteur dominant :** La population humaine est la variable la plus prédictive (83% de l'importance), suivie par les effets de contexte local (voisinage).


* 
**Validation :** Absence de biais géographique significatif (Indice de Moran sur les résidus ).


# Carte des résidus



# Examination des résultats

## Statistiques Descriptives des résultats de la mosélisation

| Statistique       | ratio_exact_20 | Lower_Bound | Upper_Bound | Po_chien20 | Po_chien_clean | Pop_huma20 | pred_chiens | residu_abs  | residu_relatif | densite_pop |
|-------------------|----------------|-------------|-------------|------------|-------------------------|------------|-------------|--------------|-----------------|--------------|
| count            | 302            | 523         | 523         | 302        | 523                     | 523        | 523         | 523          | 523             | 523          |
| mean             | 0.0798         | 0.00413     | 0.399153    | 35.202     | 17.086                  | 1424.344   | 129.326     | -112.240     | -1851.781       | 159.668      |
| std              | 0.241987       | 0.011264    | 0.036891    | 82.510     | 38.327                  | 3878.666   | 281.689     | 255.522      | 1722.136        | 533.276      |
| min              | 0.0004         | 0           | 0.269626    | 1          | 1                       | 4          | 3.526       | -4112.564    | -6999.960       | 0.35         |
| 25%              | 0.004033       | 0           | 0.368576    | 1          | 1                       | 207        | 25.285      | -115.639     | -2804.870       | 21.525       |
| 50% (médiane)    | 0.011441       | 0           | 0.400335    | 5          | 3                       | 487        | 49.390      | -44.854      | -1234.834       | 50.63        |
| 75%              | 0.027752       | 0.000333    | 0.425443    | 38         | 13                      | 1334       | 130.407     | -23.057      | -457.536        | 130.55       |
| max              | 2.384615       | 0.078765    | 0.469099    | 1096       | 381                     | 67967      | 4304.564    | -2.526       | -200.491        | 7968        |


---

## **Observations Clés**
1. **Asymétrie des données** : Les colonnes comme `Pop_huma20`, `pred_chiens`, et `densite_pop` montrent une **grande variabilité** (écarts-types élevés), présence d'outliers.
2. **Résidus** : Les résidus négatifs (`residu_abs` et `residu_relatif`) indiquent que le modèle **sous-estime** systématiquement les valeurs prédites.
3. **Valeurs manquantes** : Certaines colonnes (ex : `ratio_exact_20`) ont moins d'entrées (`count=302`) que d'autres (`count=523`), ce qui peut refléter des **données manquantes** ou des filtres appliqués.

---


### 👥 Auteurs

Abdelkarim HADDAD, Cheick NIANG, Adam GBAGUIDI.

*Université Paris 8 - Encadré par M. Vincent GODARD*.
