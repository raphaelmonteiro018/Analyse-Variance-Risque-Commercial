# 🧠 Méthodologie & Présentation de l'Outil

Cette section détaille le fonctionnement technique de l'outil, la logique mathématique de décomposition des écarts et l'exploitation des indicateurs statistiques pour le pilotage.

---

## 🛠️ 1. Présentation de l'Outil & Workflow

L'outil automatise l'intégralité de la chaîne de valeur analytique via une architecture Python robuste :

- **Ingénierie des données** : Traitement de 400 000 transactions avec **Regex Mapping** pour une catégorisation automatique des produits en 8 familles de produits.
- **Modélisation Financière** : Simulation d'un environnement P&L (injection de cibles de marge et coûts unitaires à l'échelle individuelle) pour refléter la réalité opérationnelle.
- **Calculs Haute Performance** : Utilisation de **NumPy** pour une exécution instantanée des calculs matriciels de variance, volatilité et corrélation.
- **Restitution Hybride** : 
    - **Power BI** : Pilotage stratégique et visuels explicites / dynamiques.
    - **Excel** : Export uniformisé pret à l'emploi pour Power BI et scinder en plusieurs onglets pour faciliter la lecture ainsi que les controles.

### Détail de l'export automatisé - Excel
- Le fichier étant trop lourd pour etre partagé voici les captures de l'export généré par le script :

<img width="1860" height="678" alt="image" src="https://github.com/user-attachments/assets/b6e7b293-7b97-4b9c-8a0a-af29f2406fa1" />

<img width="1897" height="670" alt="image" src="https://github.com/user-attachments/assets/c99fc48d-dbad-420e-b8e0-d19c153d5f54" />
Les effets à 0 indiquent que le produit a été lancé sur le mois cloturé, il n'y a donc aucun précédent sur cet item.

<img width="1503" height="680" alt="image" src="https://github.com/user-attachments/assets/38af317f-4780-4dde-8516-44092d7a7db9" />

<img width="1043" height="674" alt="image" src="https://github.com/user-attachments/assets/3503f907-28bc-4c18-99c5-728ba0ec9ce4" />

<img width="1045" height="679" alt="image" src="https://github.com/user-attachments/assets/c476f4b6-e627-40c8-bd96-f579316ec949" />

<img width="1713" height="673" alt="image" src="https://github.com/user-attachments/assets/18fcd32f-8496-4fe2-97ba-28d7ef2a5fc0" />

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
- **Optimisation du Mix** : Ajuster l'offre commerciale en fonction des comportements d'achat observés (détecter de potentielles synergies pour des ventes croisées).

---

## 🖥️ 4. Visualisation & Aide à la Décision

### Bridge de Variance
Le visuel central permet d'expliquer chaque dollar de dérive. Dans ce projet, il a permis d'isoler un impact de **-56k $** sur le segment *Kitchen & Dining*, principalement dû à un effet Mix défavorable.

<img width="968" height="681" alt="image" src="https://github.com/user-attachments/assets/66433f13-2e62-41b7-9062-c2eb94f17bb7" />


### Quadrant Risque-Rendement
Le dashboard Power BI segmente automatiquement le portefeuille :
- **Segments Stables (Cash Cows)** : Marge élevée, faible volatilité (en haut à gauche).
- **Segments Volatiles** : Nécessitent une surveillance accrue du BFR (en bas à droite).

<img width="1320" height="708" alt="image" src="https://github.com/user-attachments/assets/dec0c00c-524a-489b-af4d-eae18c37a1d7" />

---

## ✅ Conclusion
En combinant la puissance de calcul via **Python** et la clarté de **Power BI**, cet outil transforme une base de données "sale" en une feuille de route stratégique actionnable pour la direction financière.
