# Instagram Engagement Analysis

## Overview

This project organizes an exploratory Instagram engagement analysis for a company. The documentation is based on the existing notebooks and keeps the analytical conclusions unchanged.

Original analytical sources:

- `data-analysis-instagram-engagement-part01.ipynb`
- `data-analysis-instagram-engagement-part02.ipynb`
- `08. Analisando o engajamento no Instagram.xlsx`

## Problem Context

The central question in the notebooks is:

> Which type of content drives the most engagement on the company's Instagram?

The original guidance is to ignore the `Visualizações` column, focus on likes, comments, and interactions, and treat empty tags as posts without tags.

## Methodology

The analysis is split into two notebooks:

- A general analysis by content type, people, campaigns, and carousel.
- A tag-focused analysis using `split` and `explode` to evaluate combined tags separately.

Main steps include importing the Excel file with pandas, treating carousel null values, reviewing descriptive statistics, plotting likes and comments over time, ranking posts by likes, and grouping metrics with `groupby`.

## Key Insights

The insights below come from the existing notebooks:

- Posts with people have much stronger engagement for this brand.
- Campaign posts also perform better.
- In this dataset, carousel was not a differentiating factor for improving engagement.
- Promotion posts had the highest average engagement in the tag analysis.
- Commemorative dates and trends also showed strong engagement.
- Videos without people performed poorly, while videos with people, trends, or commemorative dates performed better.
- The `Loja` tag should not be judged as poor until it is tested with people or campaigns.
- Continued monitoring is recommended because the dataset still contains limited information.

Selected numeric results already present in the notebook outputs:

- Average likes with people: `14,664.55`.
- Average likes without people: `4,256.67`.
- Average likes with campaigns: `18,173.27`.
- Average likes without campaigns: `7,928.33`.
- Average likes for the `Promoções` tag: `27,458.33`.
- Average likes for the `Datas comemorativas` tag: `20,752.25`.
- Average likes for the `Trends` tag: `20,024.00`.

## Limitations

- The analysis is exploratory and based only on the available history.
- The dataset has a limited number of posts.
- Some combinations of format, people, and campaign status have few observations.
- After using `explode` on tags, the notebook itself recommends using that transformed data only for tag-related analysis.
- Promotion posts may involve costs that are not evaluated in the current metrics.
- The analysis identifies observed patterns, not causal effects.

## Next Steps

- Continue monitoring new posts.
- Test the `Loja` tag with people or campaigns.
- Evaluate the cost and return of promotional campaigns.
- Export figures to `reports/figures/` only when they are generated from the existing analysis.
- In a future task, standardize notebook paths to `data/raw/` without changing analytical conclusions.

## Project Structure

See [data/README.md](../../data/README.md) for dataset handling and [reports/final_report.md](../../reports/final_report.md) for the consolidated report.

## Running Locally

```bash
pip install -r requirements.txt
jupyter notebook
```

Run the notebooks from the repository root so the current Excel path remains valid.
