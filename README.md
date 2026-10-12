# Analyse d'un championnat de football avec Pandas

TP2 du cours **Python Avancé** — Licence 3 Intelligence Artificielle, ISM École d'ingénieurs (Dakar).
Enseignant : Elias BADJI · Binôme : Hamze Abdoulkarim ADEN et Moussa CISSÉ · Octobre 2026.

## Contexte

La « Ligue Pro » est un championnat **fictif** de 20 clubs. Les données couvrent trois saisons (2023-2024 à 2025-2026, 380 matchs par saison) et ont été volontairement saisies avec des erreurs. L'objectif est de les nettoyer, de reconstruire les classements, puis de produire les indicateurs d'un rapport de fin de saison, avec **Pandas et NumPy uniquement** et sans boucle sur les lignes des DataFrames.

## Contenu du dépôt

| Fichier | Description |
|---|---|
| `TP2_ADEN_CISSE.ipynb` | Notebook complet : code, résultats, justifications et interprétations |
| `rapport_ligue.xlsx` | Export final : classements des 3 saisons, meilleurs buteurs et affluence 2025-2026 |
| `data/` | Les 4 fichiers CSV sources (`equipes`, `matchs`, `joueurs`, `buts`) |
| `requirements.txt` | Bibliothèques Python nécessaires |

## Démarche

1. **Diagnostic** des quatre tables : types, valeurs manquantes, doublons, valeurs incohérentes.
2. **Nettoyage** : suppression de doublons exacts, harmonisation de 16 variantes de postes en 4, conversion des salaires saisis avec des espaces, imputation par médiane de groupe (salaires, affluences), découpage des minutes de temps additionnel (« 90+3 »).
3. **Classements** : transformation de chaque match en deux lignes (une par équipe), agrégation par saison et par club, tri réglementaire, contrôles de cohérence par `assert`.
4. **Analyses** : meilleurs buteurs, avantage du terrain, affluence, répartition des buts dans le temps, duos passeur-buteur, lien masse salariale / points, carrières des joueurs, contrôles croisés entre tables.
5. **Export** Excel multi-feuilles.
6. **Bonus** : course au titre journée par journée.

## Quelques résultats

- Presqu'île Racing est champion 2025-2026 avec 75 points, devant l'Étoile du Cap-Vert (73), seul club présent sur le podium des trois saisons.
- L'équipe qui reçoit gagne environ 43 à 48 % des matchs, contre 26 à 29 % pour l'équipe qui se déplace.
- La masse salariale et les points sont fortement corrélés en 2025-2026 (r = 0,82), ce qui ne suffit pas à établir un lien de cause à effet.
- 8,6 % des buts sont marqués dans le temps additionnel.
- La tête du championnat 2025-2026 a changé 7 fois de mains, et le titre ne s'est joué qu'aux deux dernières journées.

## Outils

Python 3.13 · Pandas · NumPy · Jupyter (VS Code) · openpyxl

## Reproduire l'analyse

```bash
git clone https://github.com/hamze-ISM/tp2-pandas-championnat-football.git
cd tp2-pandas-championnat-football
python -m venv .venv
.venv\Scripts\python.exe -m pip install -r requirements.txt   # Windows
```

Ouvrir ensuite `TP2_ADEN_CISSE.ipynb`, sélectionner le noyau `.venv`, puis « Redémarrer et tout exécuter ».

## Source des données

Données entièrement fictives, fournies par l'enseignant dans le dépôt du cours : [github.com/Techbadji/pythonavance](https://github.com/Techbadji/pythonavance) (dossier `data/`). Elles sont reproduites ici uniquement pour permettre la réexécution du notebook.