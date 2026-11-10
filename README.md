# Lire et collecter une page web : books.toscrape.com

Projet réalisé dans le cadre du **Bootcamp Data Analyst** (Wild Code School × Simplon), semaine 9 : *Collecter la donnée*.

## Objectif

Collecter le catalogue d'une catégorie du site d'entraînement
[books.toscrape.com](https://books.toscrape.com) sur **deux niveaux** :

1. **les pages de liste** : titre, prix, disponibilité, note, lien vers la fiche ;
2. **les fiches détaillées** : catégorie, stock chiffré, UPC.

Catégorie étudiée : **Childrens** — 29 livres sur 2 page(s).

## Démarche

- **Fiche technique d'abord** : chaque donnée est localisée dans le HTML avec l'inspecteur du navigateur, et chaque sélecteur CSS est testé dans la console avant d'être écrit en Python. La fiche est recopiée en tête du notebook.
- **Pagination** : suivie via le lien `li.next a`, sans écrire les adresses à la main.
- **Collecte respectueuse** : `robots.txt` vérifié, `User-Agent` identifiable, une requête par seconde, garde-fou sur le nombre de pages.
- **Nettoyage** : prix et stock convertis en numérique, note convertie de `One`…`Five` en 1…5.

## Outils

- Python 3.12, environnement géré avec [uv](https://docs.astral.sh/uv/)
- `requests`, `beautifulsoup4`, `pandas`
- Jupyter Notebook

## Structure

```
lire-collecter-une-page/
├── data/                  # CSV produit par la collecte
├── notebooks/
│   └── collecte.ipynb     # fiche technique, code, analyse
├── pyproject.toml
└── uv.lock
```

## Reproduire

```bash
git clone git@github.com:pbejian/lire-collecter-une-page.git
cd lire-collecter-une-page
uv sync
```

Ouvrir ensuite `notebooks/collecte.ipynb` avec le kernel du `.venv`.

## Résultats

Les réponses chiffrées (nombre de livres, stock total, prix moyen,
livre le plus cher, répartition des notes) sont dans le notebook,
section « Analyse ». Données collectées : dossier `data/`.

## Auteur

Pierre BÉJIAN