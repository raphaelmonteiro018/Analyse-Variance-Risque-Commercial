# 🧠 Méthodologie & Présentation de l'Outil

Cette section détaille le fonctionnement technique de l'outil, la logique mathématique de décomposition des écarts et l'exploitation des indicateurs statistiques pour le pilotage.

---

## 🛠️ 1. Présentation de l'Outil & Workflow

L'outil automatise l'intégralité de la chaîne de valeur analytique via une architecture Python robuste (`VarianceAnalyzer`) :

- **Ingénierie des données** : Traitement de 400 000 transactions avec **Regex Mapping** pour une catégorisation automatique des produits en 8 macro-familles stratégiques.
- **Modélisation Financière** : Simulation d'un environnement P&L complet (injection de cibles de marge et coûts unitaires bruités) pour refléter la réalité opérationnelle.
- **Calculs Haute Performance** : Utilisation de **NumPy** pour une exécution instantanée des calculs matriciels de variance, volatilité et corrélation.
- **Restitution Hybride** : 
    - **Power BI** : Pilotage stratégique et visuel pour le CODIR.
    - **Excel** : Reporting opérationnel via `OpenPyxl` avec formatage conditionnel (Vert/Rouge) automatisé.

---

## 📐 2. Méthodologie : Moteur de Variance PVM

Le cœur mathématique repose sur une décomposition **Prix-Volume-Mix**. Cette approche garantit une **réconciliation à 100%** (zéro résidu) entre le réalisé et le budget.

### Équations de décomposition :

* **Effet Prix** : Impact de la variation du prix de vente unitaire.
    $$Effet\ Prix = (Prix_{Actuel} - Prix_{Budget}) \times Quantité_{Actuelle}$$

* **Effet Volume** : Impact de la croissance de l'activité à structure de panier constante.
    $$Effet\ Volume = \frac{Qty_{Bud}}{Total\ Qty_{Bud}} \times (Total\ Qty_{Act} - Total\ Qty_{Bud}) \times Prix\ Moyen_{Bud}$$

* **Effet Mix** : Impact du glissement de la consommation vers des produits plus ou moins chers (effet "panier").
    $$Effet\ Mix = Variance\ Totale - (Effet\ Prix + Effet\ Volume)$$

> **Note métier** : Isoler l'effet Mix est indispensable pour identifier si une hausse de CA cache en réalité une dégradation de la valeur du panier moyen.

---

## 📈 3. Analyse Statistique & Risque

L'outil intègre des indicateurs avancés pour l'arbitrage du capital et la gestion des stocks.

### Volatilité Pondérée (Decay Factor)
Pour évaluer la santé des segments, le script calcule un **Coefficient de Variation (CV)**. L'innovation réside dans l'application d'un **Decay Factor (0.95)** :
- Les ventes récentes ont plus de poids que les ventes anciennes.
- Permet de détecter une instabilité de marché *actuelle* et d'ajuster les stocks de sécurité en conséquence.

### Matrice de Corrélation
Le moteur calcule la corrélation de Pearson entre les familles de produits :
- **Synergies** : Identifier les segments qui se vendent simultanément.
- **Optimisation du Mix** : Ajuster l'offre commerciale en fonction des comportements d'achat observés.

---

## 🖥️ 4. Visualisation & Aide à la Décision

### Bridge de Variance
Le visuel central permet d'expliquer chaque dollar de dérive. Dans ce projet, il a permis d'isoler un impact de **-56k $** sur le segment *Kitchen & Dining*, principalement dû à un effet Mix défavorable.

### Quadrant Risque-Rendement
Le dashboard Power BI segmente automatiquement le portefeuille :
- **Segments Stables (Cash Cows)** : Marge élevée, faible volatilité.
- **Segments Volatiles** : Nécessitent une surveillance accrue du BFR (ex: *Seasonal & Events* avec **87,88%** de volatilité).

---

## ✅ Conclusion
En combinant la puissance de calcul de **Python** et la clarté de **Power BI**, cet outil transforme des millions de lignes de données en une feuille de route stratégique actionnable pour la direction financière.
