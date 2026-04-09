# 🏢 Système d'Analyse de Variance (Prix-Volume-Mix) & Pilotage de l'Offre

Ce projet est conçu comme un système d'analyse des écarts pour un acteur du Retail en ligne. L'objectif est de transformer la donnée brute en outil d'analyse en isolant les causes de déviation par rapport au budget. L'analyse est réalisée via une modélisation Prix-Volume-Mix ainsi que des matrices décisionnelles, l'outil permet de piloter l'offre commerciale et d'arbitrer l'allocation du capital sur les segments les plus rentables selon leur volatilité des ventes (approche risque-rendement).

---

## 📊 Aperçu du Pilotage (Power BI)

Le dashboard est structuré pour offrir une lecture multiniveaux, du KPI stratégique à l'analyse de corrélation granulaire.

### 1. Synthèse Chiffre d'Affaires & Marge Brute
Monitoring de la performance commerciale, répartition géographique et par segment d'activité.
insérer image power bi

### 2. Moteur d'Analyse de Variance (Bridge PVM)
Visualisation de la décomposition mathématique de l'écart au budget par effet et par segment.
insérer image power bi

### 3. Matrice Risque-Rendement & Corrélations
Pilotage de l'offre selon la profitabilité et la volatilité des ventes de chaque segment et analyse de corrélations
insérer image power bi

---

## 🎯 Objectifs
- **Industrialiser l'analyse des écarts** : Automatiser la décomposition de la variance du Chiffre d'Affaires via un moteur PVM (Prix-Volume-Mix) pour expliquer l'écart avec le prévisionnel.
- **Arbitrer l'offre via le Risque-Rendement** : Déployer une matrice de décision croisant **volatilité relative** et **taux de marge** pour identifier les segments "Cash Cows" et sécuriser les segments à risque.
- **Modéliser les corrélations inter-segments** : Utiliser l'analyse matricielle pour détecter les synergies de ventes et optimiser le Mix Produit en fonction des comportements d'achat observés.
- **Sécuriser la fiabilité financière** : Garantir une réconciliation mathématique entre le réalisé et les objectifs budgétaires.

---

## 🚀 Résultats
- **Maîtrise de l'analyse de variance** : Réconciliation à 100% de l'écart budgétaire et décomposition propre des effets Prix-Volume-Mix.
- **Pilotage stratégique de l'offre** : Identification du segment *Kitchen & Dining* comme étant défaillant sur le mois étudié (**-56k $ d'impact**).
- **Audit du rapport risque-rendement** : Etude des segments via le taux de marge et la volatilité des ventes, le découpage du graphique permettant de déterminer leur positionnement à travers un quadrant "risque-rendement". 
- **Gain de productivité & Fiabilité** : Suppression des erreurs de saisie manuelle via un pipeline automatisé Python/Excel/Power BI, ramenant le cycle de production de l'analyse des écarts à quelques minutes.

---

## 🔁 Workflow
1. **Ingénierie de données** : Nettoyage et structuration d'un dataset d'environ 400k lignes transactionnelles sous Python.
2. **Moteur d'Analyse des Écarts** : Modélisation de la décomposition PVM et réconciliation budgétaire automatisée.
3. **Analyse Matricielle** : Calcul des matrices décisionnelles (matrice de corrélations et matrice risque-rendement).
4. **Business Intelligence** : Visualisation dynamique sous Power BI pour l'aide à la décision.

---

## 🏗️ Outils utilisés
- **Power BI** : Formules DAX
- **Excel** : Export automatisé via Python
- **Python** : Pandas (Traitement de masse), NumPy (Calcul matriciel de la variance et pondération temporelle)

---

## 📁 Contenu du projet
- **Méthodologie & Présentation de l'analyse**

## Navigation
Pour naviguer entre les différentes étapes du processus veuillez sélectionner les sous-branches nommées dans l'ordre d'exécution.
insérer image navigation
