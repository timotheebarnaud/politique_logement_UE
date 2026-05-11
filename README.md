# Logement en Europe : panorama des politiques publiques et de la pression sur les ménages

*À l'approche de l'Affordable Housing Act prévu fin 2026 par la Commission européenne, état des lieux des modèles de logement européens et des tensions financières qui pèsent sur les ménages.*

## Visualisations

1. [Financement public, logement social, emprunts… dans l'Union européenne, des politiques du logement hétérogènes](https://www.datawrapper.de/_/xYYPo/?v=3) — Tableau de bord comparatif des 27 États membres sur 7 indicateurs de politique publique du logement
2. [Logement en Europe : la double pression sur les ménages](https://public.flourish.studio/visualisation/28896207/) — Croisement entre surcharge financière du logement et retards de paiement (loyer ou prêt immobilier)
3. [Avoir une température adéquate dans son logement, un défi pour de nombreux Européens](https://public.flourish.studio/visualisation/28924032/) — Cartographie de l'incapacité à maintenir une température adéquate dans le logement

## Méthodologie

Le tableau de bord central s'appuie sur le [**European Housing Dashboard d'Eurofound**](https://www.eurofound.europa.eu/en/surveys-and-data/data-catalogue/housing-dashboard) (publié le 17/12/2025), qui compile des données de **Hypostat 2025** (European Mortgage Federation), **Eurostat** (code gov_10a_exp) et de sources nationales. Les données "policies" sont disponibles au format **JSON** par pays : un pipeline Python parcourt les 27 fichiers via `json.load` et extrait les indicateurs pertinents par navigation dans les dictionnaires imbriqués.

Les indicateurs outcomes (surcharge financière, retards de paiement, incapacité à chauffer) sont disponibles en téléchargement sous format tableur, mais ont été récupérés directement à la source primaire **Eurostat** via les codes `ilc_lvho07a`, `ilc_mdes06` et `ilc_mdes01` car plus récentes.

**Limites** :

Les données du tableau de bord proviennent d'années variables (entre 2023 et 2025 selon les indicateurs). L'indicateur d'incapacité à maintenir une température adéquate est subjectif et déclaratif : les différences sociales et culturelles entre pays peuvent influencer les réponses.

## Organisation du dépôt

```
├── data/
│   ├── raw/            # 27 fichiers JSON Eurofound + CSV Eurostat
│   └── clean/          # Exports pour les visualisations
├── notebooks/
│   └── logement_UE.ipynb
└── README.md
```

## Outils

Python (pandas, json) · Eurofound European Housing Dashboard · Eurostat (EU-SILC) · Datawrapper · Flourish · Jupyter Notebook

---

Projet réalisé par **Timothée Barnaud**.
