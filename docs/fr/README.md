# Analyse de l'engagement Instagram

## Vue d'ensemble

Ce projet organise une analyse exploratoire de l'engagement Instagram d'une entreprise. La documentation est basée sur les notebooks existants et conserve les conclusions analytiques inchangées.

Sources analytiques originales :

- `data-analysis-instagram-engagement-part01.ipynb`
- `data-analysis-instagram-engagement-part02.ipynb`
- `08. Analisando o engajamento no Instagram.xlsx`

## Contexte du problème

La question centrale des notebooks est :

> Quel type de contenu génère le plus d'engagement sur l'Instagram de l'entreprise ?

Les consignes originales indiquent d'ignorer la colonne `Visualizações`, de se concentrer sur les likes, commentaires et interactions, et de traiter les tags vides comme des publications sans tag.

## Méthodologie

L'analyse est divisée en deux notebooks :

- Une analyse générale par type de contenu, présence de personnes, campagnes et carrousel.
- Une analyse centrée sur les tags avec `split` et `explode` pour évaluer séparément les tags combinés.

Les principales étapes incluent l'import du fichier Excel avec pandas, le traitement des valeurs nulles de carrousel, les statistiques descriptives, les graphiques de likes et commentaires dans le temps, le classement des publications par likes et les agrégations avec `groupby`.

## Principaux insights

Les insights ci-dessous proviennent des notebooks existants :

- Les publications avec des personnes ont un engagement beaucoup plus fort pour cette marque.
- Les publications de campagne performent également mieux.
- Dans ce jeu de données, le carrousel n'a pas été un facteur différenciant pour améliorer l'engagement.
- Les promotions ont obtenu le meilleur engagement moyen dans l'analyse par tags.
- Les dates commémoratives et les trends ont aussi montré un fort engagement.
- Les vidéos sans personnes ont eu de faibles résultats, tandis que les vidéos avec des personnes, des trends ou des dates commémoratives ont mieux performé.
- Le tag `Loja` ne doit pas être considéré comme mauvais avant d'être testé avec des personnes ou des campagnes.
- La poursuite du suivi est recommandée, car la base contient encore peu d'informations.

Résultats numériques sélectionnés déjà présents dans les outputs des notebooks :

- Likes moyens avec personnes : `14 664,55`.
- Likes moyens sans personnes : `4 256,67`.
- Likes moyens avec campagnes : `18 173,27`.
- Likes moyens sans campagnes : `7 928,33`.
- Likes moyens pour le tag `Promoções` : `27 458,33`.
- Likes moyens pour le tag `Datas comemorativas` : `20 752,25`.
- Likes moyens pour le tag `Trends` : `20 024,00`.

## Limites

- L'analyse est exploratoire et basée uniquement sur l'historique disponible.
- Le jeu de données contient un nombre limité de publications.
- Certaines combinaisons de format, personnes et campagnes ont peu d'observations.
- Après l'utilisation de `explode` sur les tags, le notebook recommande de limiter l'analyse transformée aux relations impliquant les tags.
- Les promotions peuvent avoir des coûts qui ne sont pas évalués dans les métriques actuelles.
- L'analyse identifie des motifs observés, pas des effets causaux.

## Prochaines étapes

- Continuer à suivre les nouvelles publications.
- Tester le tag `Loja` avec des personnes ou des campagnes.
- Évaluer le coût et le retour des campagnes promotionnelles.
- Exporter les figures dans `reports/figures/` uniquement lorsqu'elles sont générées depuis l'analyse existante.
- Dans une tâche future, standardiser les chemins des notebooks vers `data/raw/` sans modifier les conclusions analytiques.

## Structure du projet

Voir [data/README.md](../../data/README.md) pour la gestion des données et [reports/final_report.md](../../reports/final_report.md) pour le rapport consolidé.

## Exécution locale

```bash
pip install -r requirements.txt
jupyter notebook
```

Exécutez les notebooks depuis la racine du dépôt afin de conserver le chemin Excel actuel.
