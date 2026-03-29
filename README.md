## 🏢 Contexte
Ce projet fournit une lecture analytique et stratégique de la performance commerciale d’un acteur du Retail (+500k transactions). L'outil permet de dépasser le simple constat du Chiffre d'Affaires pour décomposer les causes réelles de la croissance et identifier les glissements de rentabilité (Effet Mix) nécessitant un arbitrage du capital ou des stocks.

## 🎯 Objectifs
- **Isoler les leviers de performance (PVM)** : Décomposer la variation du CA en trois piliers : l'impact des prix, la dynamique des volumes et l'évolution de la structure des ventes (Mix produit).
- **Cartographier le risque commercial** : Segmenter l'offre via une matrice "Risque-Rendement" basée sur la **volatilité relative** (Coefficient de Variation) pour sécuriser les marges.
- **Optimiser le mix produit** : Détecter les synergies de ventes entre segments via une matrice de corrélation automatisée afin d'orienter les campagnes promotionnelles.
- **Garantir la fiabilité financière** : Assurer une réconciliation mathématique à 100% entre les données transactionnelles brutes, le budget cible et les effets de variance calculés.

## 🚀 Résultats
- **Rigueur du Bridge CA** : Réconciliation systématique des **43 972 $** d'écart au budget. Le modèle isole précisément l'effet Volume (croissance organique) de l'**Effet Mix** (impact de la modification du portefeuille produit).
- **Identification des segments critiques** : Mise en évidence de la sous-performance du segment *Kitchen & Dining* (-56k $ de contribution), révélant un glissement défavorable du mix produit malgré une hausse globale des volumes.
- **Audit de la volatilité** : Classification des segments selon leur stabilité, révélant une volatilité extrême sur le segment *Seasonal & Events* (**87,88%**) nécessitant un pilotage spécifique des stocks de sécurité.
- **Gain de productivité** : Automatisation complète du pipeline de données (du nettoyage Python à l'export Excel/Power BI), transformant un processus de clôture manuel de plusieurs heures en un script exécutable en quelques minutes.

<img width="923" height="404" alt="Analyse de Variance PVM" src="https://github.com/user-attachments/assets/votre-image-pvm" />

## 🔁 Workflow
1. **Data Engineering** : Nettoyage et structuration d'un dataset de +500k lignes sous Python (Pandas/NumPy).
2. **Moteur de Variance PVM** : Modélisation de la décomposition additive (Price, Volume, Mix) et réconciliation systématique avec les objectifs budgétaires.
3. **Analyse Statistique** : Génération automatisée des matrices de corrélation inter-segments et de volatilité relative (CV).
4. **Business Intelligence** : Visualisation dynamique sous Power BI pour le pilotage de la performance et l'aide à la décision CODIR.

## 🏗️ Outils utilisés
- **Power BI** : DAX (Mesures de Time Intelligence & Ratios de marge)
- **Excel** (Export automatisé pour les opérationnels)
- **Python** : Pandas (Traitement de masse), NumPy (Calcul matriciel de la variance)

## 📁 Contenu du projet
- **Etape 1** : Méthodologie mathématique du PVM & Réconciliation budgétaire.
- **Etape 2** : Analyse Risque-Rendement & Matrices de corrélation.

## Navigation
Pour naviguer entre les différentes étapes du processus veuillez sélectionner les sous-branches nommées dans l'ordre d'exécution.
<img width="1852" height="542" alt="Navigation" src="https://github.com/user-attachments/assets/votre-image-navigation" />