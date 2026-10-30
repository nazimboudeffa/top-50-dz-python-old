# DZ TOP 50 — Moteur de classement musical

Projet indépendant de classement musical algérien. Le pipeline collecte les données accessibles, normalise les titres, calcule un score, conserve un historique et exporte le classement en CSV, Excel, JSON et HTML.

## Structure

```
notebooks/
  TOP_50_DZ_Notebook.ipynb   # pipeline complet
data/
  raw/                       # CSV sources : title,artist,rank
  history/                   # archives dz_top50_AAAAMMJJ.csv
exports/
  2026-10-30/                # un dossier par date d'exécution
    DZ_TOP_50_20261030.csv
    DZ_TOP_50_20261030.xlsx
    DZ_TOP_50_20261030.json
    DZ_TOP_50_20261030.html
    instagram_caption_20261030.txt
```

## Lancer

1. Ouvrir `notebooks/TOP_50_DZ_Notebook.ipynb` dans Jupyter ou Colab.
2. Exécuter les cellules dans l'ordre.
3. Spotify est collecté automatiquement (playlist éditoriale **Hot Hit Algeria**).
4. Les exports sont écrits dans `exports/<date>/` et l'archive dans `data/history/`.

Aucune clé Spotify n'est nécessaire. Apple Music reste optionnel via `APPLE_MUSIC_DEVELOPER_TOKEN`.

## Sources

- **Spotify** : ordre de la playlist éditoriale Hot Hit Algeria (`metric = playlist_order`), pas un nombre d'écoutes.
- **Apple Music** : chart catalogue officiel, optionnel.
- **Autres plateformes** : CSV déposés dans `data/raw/` (`title,artist,rank`).

## Exemple

Le dossier `exports/2026-10-30/` contient un run réel avec 50 titres Spotify.
