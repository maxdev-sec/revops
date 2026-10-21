# RevOps: Genomics Inc Revenue Data Platform

<!-- Replace {org} with your Azure DevOps organization and {definitionId} with the pipeline id. Both appear in the pipeline's URL. -->
[![Azure Pipelines](https://img.shields.io/azure-devops/build/{org}/revops/{definitionId}?logo=data:image/svg%2Bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZD0iTTEyIDEyQzEwIDkgOC41IDguMiA2LjggOC4yQTMuOCAzLjggMCAxIDAgNi44IDE1LjhDOC41IDE1LjggMTAgMTUgMTIgMTJDMTQgOSAxNS41IDguMiAxNy4yIDguMkEzLjggMy44IDAgMSAxIDE3LjIgMTUuOEMxNS41IDE1LjggMTQgMTUgMTIgMTJaIiBmaWxsPSJub25lIiBzdHJva2U9IiNmZmYiIHN0cm9rZS13aWR0aD0iMi4yIiBzdHJva2UtbGluZWNhcD0icm91bmQiLz48L3N2Zz4%3D&label=azure%20pipelines)](https://dev.azure.com/{org}/revops/_build/latest?definitionId={definitionId}&branchName=main)

## Case study

Genomics Inc is an early stage startup that licenses de-identified genomic and DNA datasets to pharma, biotech R&D teams, and academic research labs.

Marketing and sales run on HubSpot. Data runs on Azure.

This project builds the revenue data platform that lets the AI and sales teams use that data and turn those signals into account insights. It uses ETL and reverse ETL to put the full story back in HubSpot, where the sales team already works.

**Products:** annual dataset licenses, sold by cohort and across tiers.

**Go to market:** we sell to scientists, so outreach leads with data.

## Problems this solves

1. **Fragmented view.** Sales sees fragments of data. No rep sees the full engagement story of an account.
2. **No usage signal.** We do not know which customers actually use their licensed data, so renewals are guesses.
3. **No attribution.** We cannot say which campaign or webinar drove a sale, so marketing cannot plan well.

## Tech stack

| Layer | Tool |
| --- | --- |
| CI/CD | Azure DevOps |
| Compute and orchestration | Azure Functions, Queue Storage |
| Streaming | Event Hubs with Kafka |
| Processing and modeling | Databricks |
| AI | Azure OpenAI |
| Secrets | Azure Key Vault |
| Observability | Azure Log Analytics |
| CRM | HubSpot |

## Data sources

All data is mock. The data dictionary, datasets, and model live in [data/](data/).

| Source | Used for |
| --- | --- |
| AACT (CTTI, Duke) | Pharma market |
| NIH RePORTER | Academic labs and grants |
| NCI GDC | Dataset specs |
| Maven Analytics public CRM sample | CRM records |

## Repository layout

| Path | Contents |
| --- | --- |
| [azure/](azure/) | Azure Functions and queue workers |
| [databricks/](databricks/) | Notebooks and jobs |
| [infra/](infra/) | Infrastructure as code |
| [data/](data/) | Data dictionary, mock datasets, model |
