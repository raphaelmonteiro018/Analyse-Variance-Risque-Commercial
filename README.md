## 🏢 Contexte
Ce projet est conçu comme un système d'analyse des écarts pour un acteur du Retail en ligne (à partir d'un dataset de 400k transactions sur 10 mois). L'objectif est de transformer la donnée brute en leviers de performance en isolant les causes réelles de déviation par rapport au budget. L'analyse est réalisée via une modélisation Prix-Volume-Mix ainsi que des matrices décisionnelles, l'outil permet de piloter l'offre commerciale et d'arbitrer l'allocation du capital sur les segments les plus rentables.

## 🎯 Objectifs
- **Industrialiser l'analyse des écarts** : Automatiser la décomposition de la variance du Chiffre d'Affaires (Bridge CA) via un moteur PVM (Price-Volume-Mix) pour expliquer chaque dollar de dérive budgétaire.
- **Arbitrer l'offre via le Risque-Rendement** : Déployer une matrice de décision croisant **volatilité relative** et **taux de marge** pour identifier les segments "Cash Cows" et sécuriser les segments à risque.
- **Modéliser les corrélations inter-segments** : Utiliser l'analyse matricielle pour détecter les synergies de ventes et optimiser le Mix Produit en fonction des comportements d'achat observés.
- **Sécuriser la fiabilité financière** : Garantir une réconciliation mathématique à 100% entre le reporting transactionnel et les objectifs budgétaires (Zéro résidu inexpliqué).

## 🚀 Résultats
- **Maîtrise de la Variance Analysis** : Réconciliation systématique d'un écart budgétaire de **43 972 $**. Le moteur isole précisément l'**effet Mix** (glissement de structure), permettant de comprendre pourquoi une hausse de volume peut diluer la rentabilité globale.
- **Pilotage stratégique de l'offre** : Identification du segment *Kitchen & Dining* comme zone de risque majeure (-56k $ d'impact), déclenchant une alerte sur la cohérence du mix produit actuel.
- **Audit de la volatilité relative** : Segmentation précise du portefeuille (ex: *Seasonal & Events* à 87,88% de volatilité), permettant d'ajuster les niveaux de stocks de sécurité et de préserver le BFR.
- **Gain de productivité & Fiabilité** : Suppression des erreurs de saisie manuelle via un pipeline automatisé Python/Power BI, ramenant le cycle de production de l'analyse des écarts à quelques minutes.

<img width="923" height="404" alt="Analyse de Variance PVM" src="https://github.com/user-attachments/assets/votre-image-pvm" />

## 🔁 Workflow
1. **Data Engineering** : Nettoyage et structuration d'un dataset massif (+500k lignes) sous Python.
2. **Moteur d'Analyse des Écarts** : Modélisation de la décomposition PVM (Price, Volume, Mix) et réconciliation budgétaire automatisée.
3. **Analyse Matricielle** : Calcul des matrices de corrélation et de volatilité relative (CV) pour le pilotage de l'offre.
4. **Business Intelligence Decision-Ready** : Visualisation dynamique sous Power BI pour l'aide à la décision stratégique en CODIR.

## 🏗️ Outils utilisés
- **Power BI** : DAX (Analyse de la variance, Ratios de marge, Time Intelligence)
- **Excel** (Export automatisé pour les opérationnels terrain)
- **Python** : Pandas (Traitement de masse), NumPy (Calcul matriciel de la variance)

## 📁 Contenu du projet
- **Etape 1** : Méthodologie mathématique de l'Analyse des Écarts (PVM).
- **Etape 2** : Pilotage de l'Offre : Matrices de Risque, Rendement et Corrélations.

## Navigation
Pour naviguer entre les différentes étapes du processus veuillez sélectionner les sous-branches nommées dans l'ordre d'exécution.
<img width="1852" height="542" alt="Navigation" src="https://github.com/user-attachments/assets/votre-image-navigation" />
