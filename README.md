# Study-case-Minastirith

> Projet pédagogique de manipulation avancée SQL / PL-SQL — modélisation et implémentation d'un système d'information de billetterie événementielle.

## Contexte

La société **MINASTIRITH**, entité d'un grand groupe d'organisateurs d'événements (spectacles, concerts, festivals), souhaite informatiser sa gestion des salles, billets, clients et factures. Ce projet couvre la conception de la base de données et l'implémentation des traitements directement en base (procédures stockées, fonctions, triggers).

## Contenu du repository

```
├── BILLETERIE_MINASTIRITH.ipynb
├── README.md
```

## Modèle de données

10 tables relationnelles :
`CIVILITE` · `CLIENT` · `TELEPHONE` · `SALLE` · `EVENEMENT` · `CATEGORIE_PRIX` · `PLACE` · `BILLET` · `FACTURE` · `CONCERNER`

## Partie 1 — Requêtes SQL

- Création complète du schéma (DDL)
- Requêtes de consultation avec `JOIN`, `GROUP BY`, `LEFT JOIN`, sous-requêtes
- Gestion de fenêtres de dates (`ADD_MONTHS`)
- Insertion transactionnelle de billets et génération de factures

## Partie 2 — PL-SQL avancé

| # | Type | Description |
|---|------|-------------|
| 1 | Procédure | Génération de facture avec gestion d'erreurs (`RAISE_APPLICATION_ERROR`) |
| 2 | Procédure | Réservation de places avec contrôle des 2h avant événement |
| 3 | Fonction | Recherche de places contiguës disponibles (`BULK COLLECT`) |
| 4 | Trigger | Mise à jour automatique des places disponibles (`AFTER INSERT OR DELETE`) |
| 5 | Procédure | Rapport annuel sur 5 ans via curseurs simples et paramétrés (`DBMS_OUTPUT`) |

## 🛠️ Technologies

![Oracle SQL](https://img.shields.io/badge/Oracle-SQL%20%2F%20PL--SQL-red?logo=oracle)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)

- **SGBD :** Oracle (syntaxe `SYSDATE`, `ADD_MONTHS`, `NVL`, `DBMS_OUTPUT`, `RAISE_APPLICATION_ERROR`)
- **Format :** Jupyter Notebook avec magic `%%sql`

## Règles métier implémentées

- Un événement = un seul emplacement à la fois
- Vente interdite moins de **2h** avant le début de l'événement
- Un billet = une seule place (places contiguës possibles)
- Une facture peut couvrir un ou plusieurs billets
- Le stock de places se met à jour automatiquement via trigger

---

> Projet réalisé dans le cadre d'un cours de manipulation avancée SQL/PL-SQL 
