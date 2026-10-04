# Viewer d'alignement des annuaires de Paris (1807 / 1808)

Copie, pour hébergement sur Streamlit Community Cloud, du viewer
`numrev view alignment` du dépôt `numerotation_revolutionnaire`
(version du commit `5671d78`). Lecture seule : relecture de l'alignement
des entrées des annuaires 1807 et 1808 (AD75 PER292).

- `app.py` : le script du viewer (`src/numrev/viewers/alignment.py` d'origine) ;
- `numrev/` : le sous-ensemble du paquet `numrev` dont il a besoin, copié tel quel ;
- `annuaires/<volume>/<plage>/<volume>.<plage>.ner.csv` : les entrées des deux annuaires ;
- `annuaires/alignments/` : les alignements bruts (`.dedupe.csv`, `.nw.csv`) ;
- `data/alignment/` : la correspondance manuelle des rubriques (`.sections.csv`)
  et, s'il existe, le patch de corrections des entrées (`.patch.csv`).

Ne pas modifier le code ici : le corriger dans `numerotation_revolutionnaire`
puis recopier les fichiers ci-dessus.

## Lancer en local

```bash
uv sync
uv run streamlit run app.py
```

## Streamlit Cloud

Fichier principal `app.py`, Python 3.13 ; dépendances dans `requirements.txt`
(`uv export --format requirements-txt --no-emit-project -o requirements.txt`
après tout changement de `pyproject.toml`).
