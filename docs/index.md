# GA4Dataform Docs

## Introduction

### Overview
GA4Dataform is a one-click solution for transforming GA4 event data in BigQuery into actionable insights. Ideal for digital analysts, marketers, data teams, and developers.

### Versions
- **Open-source version**: Publicly available on GitHub.
- **Installer version**: Available as a 'one-click' app in the Superform Labs store.

### About Us
GA4Dataform is created by Superform Labs OÜ, a remote team with expertise in web and marketing analytics.

- **Jules Stuifbergen** | Data Analyst | [LinkedIn](https://www.linkedin.com)
- **Krisztián Korpa** | Analytics Engineer | [LinkedIn](https://www.linkedin.com)
- **Artem Korneev** | Analytics Developer | [LinkedIn](https://www.linkedin.com)
- **Simon Breton** | Analytics Engineer | [LinkedIn](https://www.linkedin.com)
- **Johan van de Werken** | Data Analyst | [LinkedIn](https://www.linkedin.com)

### License
GA4Dataform is licensed under the GNU General Public License.

## Getting Started

### Requirements
1. An active GA4 property linked to a Google Cloud project with billing enabled.
2. A license key (received after purchase).

### Installation Guide
1. **New installation**: Instructions are provided by the app.
2. **Update**: (To be completed).

### Dataform Repository
- **Structure overview**:
definitions ├── 01_sources ├── 02_intermediate ├── 03_outputs ├── assertions ├── extra ├── unit_testing ├── includes


- **Directories description**:
- **01_sources**: Contains declarations and staging models.
- **02_intermediate**: Intermediate models.
- **03_outputs**: Output models.
- **assertions**: Data quality checks.
- **extra**: Optional extra files.
- **unit_testing**: Contains unit testing models.
- **includes**: Reusable JS variables/functions.

- **Models**:
- **stg_ga4_events**: Staging events table for GA4 data.
- **stg_ga4_sessions**: Creates session-level dimensions.
- **int_ga4_events**: Intermediate table with additional dimensions.
- **ga4_sessions**: Fixes broken sessions and attribution.

### Using GA4Dataform after installation
1. **First SQL workflow run**.
2. **Change schedule**.
3. **Git Connection**: Not available yet.
4. **Releases and Scheduling**: Set by installer; customizable via Dataform UI.

## Product Features

### Core Features
- Incremental loading.
- Partitioning & clustering.
- Fix session breakage at midnight.
- Last non-direct click attribution.
- Data quality checks (assertions).
- Event ID creation.
- Looker Studio report templates.

### Custom Configuration
- Custom GA4 parameters.
- Event filters.
- Time struct (event and session timestamps).

### Assertions
Assertions verify data quality, divided into:
- **Uniqueness**.
- **Validity**.
- **Timeliness**.
- **Freshness**.
- **Completeness**.

## Looker Studio Report Templates
1. Website diagnostics.

## Troubleshooting
Details to be added.

## Support & Contact
Open-source and Core variant users are not eligible for support. Contact: hello@ga4dataform.com.
