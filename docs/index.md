# GA4Dataform Docs

## Introduction

### Overview
GA4Dataform is your one-click solution to harness the full power of GA4 data in BigQuery, without the hassle. Transform your raw GA4 event data into actionable insights with industry-leading, enterprise-level efficiency and precision. Designed for digital analysts, technical marketers, data teams, and developers.

### Versions
#### Open-source version
The open-source version of GA4Dataform is available as a public repository on Github. This version contains the Dataform models without the ‘one-click’ installer app. The open-source version contains the same .sqlx and .js files as the ‘Core’ variant of GA4Dataform.

#### Installer version
The installer version of GA4Dataform is a ‘one-click’ app that handles the complete installation of the package. This version is available in the Superform Labs store.

#### Premium
Coming soon

### About Us
GA4Dataform is a product by Superform Labs OÜ. Our company is settled in Estonia (EU), but we work remotely from different countries across the world. Together we have decades of experience in web and marketing analytics.

- **Jules Stuifbergen** | Data Analyst | [LinkedIn](https://www.linkedin.com)
- **Krisztián Korpa** | Analytics Engineer | [LinkedIn](https://www.linkedin.com)
- **Artem Korneev** | Analytics Developer | [LinkedIn](https://www.linkedin.com)
- **Simon Breton** | Analytics Engineer | [LinkedIn](https://www.linkedin.com)
- **Johan van de Werken** | Data Analyst | [LinkedIn](https://www.linkedin.com)

### License
GNU General Public License. This file is part of "GA4 Dataform Package". Copyright (C) 2023-2024 Superform Labs <hello@ga4dataform.com> Artem Korneev, Jules Stuifbergen, Johan van de Werken, Krisztián Korpa, Simon Breton. "GA4 Dataform Package" is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>.

## Getting Started

### Requirements
To use GA4Dataform you need:
- An active GA4 property linked to a Google Cloud project with billing enabled. If the link is configured in the right way you’ll see a data set analytics_<property_id> in BigQuery.
- A license key. You’ll receive the license key in the receipt email after ordering the product in the Superform Labs store. The license key is linked to the email address used in the store. License keys are valid for a limited time (dependent on the product plan) and can be used as often as you want, unless there is a reason to disable your license key.

### Permissions

| **Permissions**                               | **Why do we need it?**                                 | **What roles have this permission?**                                                     |
|------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------|
| `bigquery.datasets.get`                        | List out the available GA4 datasets                     | BigQuery Data Viewer, BigQuery User, BigQuery Admin                                       |
| `dataform.releaseConfigs.create`               | Create release configurations for Dataform workflows    | Dataform Admin                                                                           |
| `dataform.releaseConfigs.list`                 | List release configurations                             | Dataform Admin, Dataform Editor, Dataform Viewer                                          |
| `dataform.repositories.create`                 | Create Dataform repositories                            | Dataform Admin, Dataform Editor, Code Creator, Code Editor, Code Owner                    |
| `dataform.repositories.fetchHistory`           | Fetch the commit history of a repository                | Dataform Admin, Dataform Editor, Dataform Viewer, Code Creator, Code Editor, Code Owner, Code Viewer |
| `dataform.repositories.get`                    | Get details of a specific repository                    | Dataform Admin, Dataform Editor, Dataform Viewer, Code Creator, Code Editor, Code Owner, Code Viewer |
| `dataform.repositories.list`                   | List all repositories                                   | Dataform Admin, Dataform Editor, Dataform Viewer, Code Creator, Code Editor, Code Owner, Code Viewer |
| `dataform.repositories.update`                 | Update repository settings                              | Dataform Admin, Code Owner                                                                |
| `dataform.workflowConfigs.create`              | Create workflow configurations                          | Dataform Admin                                                                           |
| `dataform.workflowConfigs.list`                | List workflow configurations                            | Dataform Admin, Dataform Editor, Dataform Viewer                                          |
| `dataform.workspaces.commit`                   | Commit changes to a workspace                           | Dataform Admin, Code Editor, Code Owner, Dataform Editor                                  |
| `dataform.workspaces.create`                   | Create new workspaces                                   | Dataform Admin, Code Editor, Code Owner, Dataform Editor                                  |
| `dataform.workspaces.fetchFileGitStatuses`     | Get Git status of files in a workspace                  | Dataform Admin, Dataform Editor, Dataform Viewer, Code Creator, Code Editor, Code Owner, Code Viewer |
| `dataform.workspaces.get`                      | Get details of a specific workspace                     | Dataform Admin, Dataform Editor, Dataform Viewer, Code Creator, Code Editor, Code Owner, Code Viewer |
| `dataform.workspaces.installNpmPackages`       | Install NPM packages in a workspace                     | Dataform Admin, Code Editor, Code Owner, Dataform Editor                                  |
| `dataform.workspaces.list`                     | List all workspaces                                     | Dataform Admin, Dataform Editor, Dataform Viewer, Code Creator, Code Editor, Code Owner, Code Viewer |
| `dataform.workspaces.makeDirectory`            | Create directories in a workspace                       | Dataform Admin, Code Editor, Code Owner, Dataform Editor                                  |
| `dataform.workspaces.pull`                     | Pull changes from a repository to a workspace           | Dataform Admin, Code Editor, Code Owner, Dataform Editor                                  |
| `dataform.workspaces.push`                     | Push changes from a workspace to a repository           | Dataform Admin, Code Editor, Code Owner, Dataform Editor                                  |
| `dataform.workspaces.queryDirectoryContents`   | List contents of a directory in a workspace             | Dataform Admin, Dataform Editor, Dataform Viewer, Code Creator, Code Editor, Code Owner, Code Viewer |
| `dataform.workspaces.readFile`                 | Read files in a workspace                               | Dataform Admin, Dataform Editor, Dataform Viewer, Code Creator, Code Editor, Code Owner, Code Viewer |
| `dataform.workspaces.writeFile`                | Write files in a workspace                              | Dataform Admin, Code Editor, Code Owner, Dataform Editor                                  |
| `iam.serviceAccounts.setIamPolicy`             | Set IAM policies for service accounts                   | Service Account Admin, Project IAM Admin                                                  |
| `resourcemanager.projects.get`                 | Get project details                                     | Viewer, Editor, Owner                                                                     |
| `resourcemanager.projects.getIamPolicy`        | Get IAM policies for projects                           | Security Reviewer, Project IAM Admin                                                     |
| `resourcemanager.projects.setIamPolicy`        | Set IAM policies for projects                           | Project IAM Admin, Owner                                                                  |
| `serviceusage.services.enable`                 | Enable GCP services                                     | Service Usage Admin, Owner                                                                |
| `serviceusage.services.list`                   | List available GCP services                             | Service Usage Consumer, Service Usage Admin                                               |


### Installation Guide
1. **New installation**: Instructions are provided by the app.
2. **Update**: (To be completed).

### Dataform Repository
**Structure overview**:
```
definitions
├── **01_sources**
│   ├── `declarations.js`
│   ├── `stg_ga4_events.sqlx`
│   ├── `stg_ga4_sessions.sqlx`
├── **02_intermediate**
│   ├── `int_ga4_events.sqlx`
│   ├── `int_ga4_sessions.sqlx`
├── **03_outputs**
│   ├── **aggregated**
│   │   ├── `demo_daily_sessions_report.sqlx`
│   │   ├── `demo_diagnostics.sqlx`
│   ├── **base**
│   │   ├── `ga4_events.sqlx`
│   │   ├── `ga4_sessions.sqlx`
├── **assertions**
│   ├── `assertion_logs.sqlx`
│   ├── `assertions_event_id_uniqueness.sqlx`
│   ├── `assertions_session_duration_validity.sqlx`
│   ├── `assertions_session_id_uniqueness.sqlx`
│   ├── `assertions_sessions_validity.sqlx`
│   ├── `assertions_tables_timeliness.sqlx`
│   ├── `assertions_transaction_id_completeness.sqlx`
│   ├── `assertions_user_pseudo_id_completeness.sqlx`
├── **extra**
│   ├── **ga4**
│   │   ├── `source_categories.js`
├── **unit_testing**
│   ├── `unit_test.sqlx`
├── **includes**
│   ├── `core_params.js`
│   ├── `custom_config.js`
│   ├── `helpers.js`
├── `.gitignore`
├── `dataform.json`
├── `package-lock.json`
├── `package.json`
```

**Directories description**:
| Directory                    | Description                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------|
| **01_sources**               | Contains declarations and staging models                                                          |
| **02_intermediate**          | Contains intermediate models                                                                      |
| **03_outputs**               | Contains output models                                                                            |
| **03_outputs/aggregated**    | Contains different aggregated tables that can be directly connected to Looker Studio or other visualization tools |
| **03_outputs/base**          | Contains output tables that should be used for aggregations                                       |
| **assertions**               | Contains all the assertions that check the data quality of our model                               |
| **extra**                    | Is it needed?                                                                                     |
| **unit_testing**             | Contains models related to unit testing                                                           |
| **includes**                 | Contains all JS files with reusable variables and functions that help manage the repository        |


**Model**:
| Model                        | Description                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| **stg_ga4_events**           | GA4 staging events table that incrementally queries the raw GA4 export and applies partitioning, clustering, cleaning, and several fixes |
| **stg_ga4_sessions**         | GA4 staging sessions table that incrementally queries `stg_ga4_events` table and creates session-level dimensions and metrics |
| **int_ga4_events**           | GA4 intermediate events table that widens the staging table with useful dimensions                                        |
| **int_ga4_sessions**         | GA4 intermediate sessions table that widens the staging table with useful dimensions                                      |
| **ga4_events**               | GA4 output events table that can be used for further transformations or aggregations                                      |
| **ga4_sessions**             | GA4 output sessions table that fixes sessions broken by midnight, adds last non-direct click attribution, and can be used for further transformations or aggregations |
| **demo_daily_sessions_report** |                                                                                                                         |
| **demo_diagnostics**         |                                                                                                                         |
| **unit_test**                |                                                                                                                         |


### Using GA4Dataform after installation
1. **First SQL workflow run**.
2. **Change schedule**.
3. **Git Connection**: GA4Dataform is not (yet) linked to any git repository. If any changes and customisation are made to the project, changes should be committed to the default Dataform repository. Versioning is not available. 
4. **Releases and Scheduling**: Set by installer; customizable via Dataform UI. The installer will automatically create a Release and a Workflow configuration using the dataform API. The release will be triggered at 9AM UTC+00:00 and the workflow will be triggered at 10AM UTC+00:00. These values can be modified directly from the dataform UI without impacting the functionality of the project. 

BigQuery Project
GA4Dataform generates tables in BigQuery. Everything will be under the dataform-package project with the following structure: 

```
Dataform-package (project)
├── superform_outputs (dataset)
│   ├── demo_daily_sessions_report (tables)
│   ├── demo_diagnostics
│   ├── ga4_events
│   ├── ga4_sessions
├── superform_transformations
│   ├── int_ga4_events
│   ├── int_ga4_sessions
│   ├── source_categories
│   ├── stg_ga4_events
│   ├── stg_ga4_sessions
├── Superform_quality
│   ├── assertion_logs
```


#### Releases and Scheduling


#### Project Location
Location of the dataform project is set during the installation. It is based on the Location of the GA4 dataset



## Product Features

### Core Features
#### Basic features | No support & updates
##### Incremental loading
The code shared is part of a GA4 data pipeline using Dataform. The incrementality works by processing only new or updated GA4 event data from BigQuery without reprocessing the entire dataset. Here's a summary of how this is implemented:

1. **Checkpoint Management:**
- A `date_checkpoint` variable is declared and set to the day after the most recent `event_date` found in the existing table (`stg_ga4_events`).
- This ensures that only data newer than the most recent processed date is considered for the next load.

set date_checkpoint = (
  select max(event_date) + 1 
  from `cst-gcp-projects.superform_transformations.stg_ga4_events` 
  where is_final = true
);

2. **Deletion of Updated Data:**
- Any existing records from the target table (`stg_ga4_events`) where `event_date` is equal to or greater than the `date_checkpoint` are deleted. This ensures that if GA4 has updated any past data, it gets removed and replaced by fresh data.

delete from `cst-gcp-projects.superform_transformations.stg_ga4_events`
where event_date >= date_checkpoint;

3. **Filtering New Data:**
- The pipeline processes only the new GA4 events by using `_table_suffix` to fetch data from BigQuery tables (`events_*`) where the `event_date` (derived from `_table_suffix`) is greater than or equal to the `date_checkpoint`.
- This prevents reprocessing old event data.

and parse_date('%Y%m%d', regexp_extract(_table_suffix, '[0-9]+')) >= date_checkpoint;

4. **Filtering out Intraday Events:**
- Intraday data, which might still be incomplete or subject to change, is excluded from the query using this condition:

and contains_substr(_table_suffix, 'intraday') is false;

5. **Finalization Logic:**
- The field `is_final` is computed in the process to determine whether the data is final (older than 3 days). This is used to manage the checkpoint logic, ensuring incremental processing only on data that is finalized.

date_diff(current_date(), cast(event_date as date format 'YYYYMMDD'), day) > 3 as is_final;

6. **Comprehensive Data Transformation:**
- The code performs data transformations on new GA4 event data, such as sanitizing fields, unpacking nested structures (like `event_params`), and repacking `ecommerce` data.
- The final step creates an `event_id` using a hash of key event fields to ensure uniqueness.

Summary of Incremental Loading:
- **Identify New Data:** By setting `date_checkpoint`, the pipeline only processes events that are newer than the last processed date.
- **Data Deletion for Updates:** It deletes any existing data for the same `event_date` to accommodate updated records from GA4.
- **Efficient Processing:** Only new and final events are processed, improving the efficiency of data loading.
- **Finalization Logic:** The `is_final` flag ensures that only finalized events are used in the checkpoint, avoiding partial or incomplete records from intraday tables.

This approach ensures an efficient and consistent update of the GA4 events data while minimizing unnecessary reprocessing.

##### Partitioning & Clustering
##### Fix session breakage on midnight
##### Default channel grouping
##### Timestamps in local time zone
##### Last non-direct click attribution model (session-based)
###### GA4 Sessions - Processing Steps

GA4 session table could provide following information: Source / Medium / Campaign at least for three standart attributions: Last click Last non direct click (with particular lookback window - 90 days by default) First click For each attribution Default Channel Groups - by the same rules as in Google Analytics 4 Landing page, landing page referrer and exit page, it could also be a struct with prepared host name, page path and query parameters Sessions properties like: is_direct_session, is_engaged_session, is_debug_session, is_cross_domain Unique session_id Session duration, engagement time Information about geo / device / app_info User information: user_id, last_user_id, user_pseudo_id

These columns are often needed to build reporting and simplify data pipelines based on session data.

What is common session processing pipeline: Extract all needed columns from raw GA4 data - to flat event tables Clean and prepare events Group events into sessions using unique session_id Fix google’s default source / medium rules, add channel grouping Add last non direct attribution

Sources to calculate source / medium collected_traffic_source column Source and medium from event_params Utm parameters from page_location click_ids from event_params or page_location, for example: gbraid, wbraid, gclid, dclid, srsltid and so on

After all sources combined together we need to apply additional logic to build a fixed source / medium on top of them. For example: if we have gclid, gbraid, wbraid source / medium should be google / cpc. Or if the referrer is %android-app://com.google% when google / organic and so on. Special rules for click ids, for social platforms, for aps.

For channel grouping Google provides a list of sources with more than 1100 rules to define groups for known domains.

And on top of these steps we could calculate last non direct attribution and compare with GA UI and numbers in session_traffic_source_last_click. For some cases source / medium fixes could provide 15-20% less direct traffic - it means improving paid campaigns attribution.

And also there are a lot of special cases and small challenges, for example: Schema are changing so be careful when you are processing historical data Transaction value could be int or double or float you need to coalesce all possible numbers Collected_traffic_source could be null for events, even if it exists for the first session’s hit Don’t forget to exclude synthetic_bundle events For event_id use batch_page_id, batch_ordering_id, batch_event_index if they exists Be very careful with fbclid parameter Have a fun processing item_params (arrays plus nested plus arrays are better together) Decide what to do with events with the same event_id Count page_number for hits during the session

##### Easy fix for Paid Search misattribution when gclid,gbraid or wbraid are available
##### Event ID
Creating unique event ID based on event_name, event_timestamp_micros, user_pseudo_id, ga_session_id, batch_page_id, batch_ordering_id, batch_event_index, engagement_time_msec.

##### Default Filtering
Session with null session_id and user_pseudo_id null are filtered from final input (in the stg_ga4_sessions model)
Duplicated hit are removed 

##### Basic data quality checks (see Assertions section)
##### Looker Studio report templates (see Looker Studio report templates section)
##### Event filters, custom parameters, custom channels etc… (see Custom Configuration section)

### Peripheral features
#### Time struct 
Struct containing event_date_YYYYMMDD, event_timestamp_micros, event_timestamp_utc, user_first_touch_timestamp, user_first_touch_timestamp_utc
#### synthetic_bundle
Synthetic event are filtered out in the stg_ga4_events.sqlx model
#### Engaged session
#### Is direct session
#### Debug session
#### Param gtm_debug
#### With cross domain
Url_params._gl
#### has_source


### Custom Configuration
#### Custom Google Analytics 4 parameters (CUSTOM_PARAMS_ARRAY)
#### Adding description here
#### Event filters
#### CLICK_IDS_ARRAY
#### URL_PARAMS_ARRAY
#### LAST_NON_DIRECT_LOOKBACK_DAYS
#### EVENTS_TO_EXLUDE

### Data Quality
Filtering
Null user_pseudo_id and session_id in stg_ga4_sessions.sqlx model
Transformation
Change '(not set)' translation id to null 
Deduping duplicates event_id in int_ga4_events.sqlx (deduped CTE)
Meta Info
Checking for measurement_protocol_hit 

### Assertions
#### Assertions logic overview 
Each assertion execution is logged in a dedicated BigQuery table easily accessible (`assertion_logs`). Failed or passed assertions result are log. Assertions log table contains:
- Execution date of assertions
- Name of the assertion
- Model on which the assertion has been run
- A sample of flawed values if any anomalies has been detected (i.e list of duplicated event id)
- The status of the assertion, failed or passed. 
- A detailed error message. 

Assertions can be independently deactivated in the custom_config.js configuration file. 

All Assertions are tagged with the string “assertions”

We have 5 main categories of assertions:

**Uniqueness**: Checking if the column we are testing contains duplicates values 

**Validity**: Checking if the column or table we are testing is “valid” from a business point of view. I.e session duration should never be negative. 

**Timeliness**: Checking if tables we are testing are “on time”. I.e we expect that the max(date) of the event table to be the same as the max(date) of the session table.

**Freshness**: We expect tables to be up to date. Freshness is an expectation that needs to be set by the user depending on their own context. 

**Completeness**: Check if the column we are testing is complete and that we are not missing any values. 


This folder contains assertion files:


| Assertion                                  | Description                                                                                                             |
|--------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| **assertion_logs**                         | Building an incremental table to log results of all the assertions.                                                     |
| **assertions_event_id_uniqueness**         | Check if the event ID is unique. Returns sample of duplicate event IDs if the assertion fails.                          |
| **assertions_session_duration_validity**   | Check if session duration is not negative.                                                                              |
| **assertions_session_id_uniqueness**       | Check if session ID is unique. Returns sample of session IDs if the assertion fails.                                     |
| **assertions_sessions_validity**           | Check the validation of sessions using multiple criteria: `landing_page_location`, `user_pseudo_id`, `session_id`, `session_date`, `device.category`, and `session_start_timestamp_utc` should not be null. |
| **assertions_tables_timeliness**           | Check if session and events tables across different layers (staging, intermediate, etc.) are always synchronized.       |
| **assertions_transaction_id_completeness** | Check for null or “not set” transaction IDs.                                                                             |
| **assertions_user_pseudo_id_completeness** | Check for null `user_pseudo_id`.                                                                                         |

Includes
This folder contains .js files with functions that are used in the .sqlx files.

| JavaScript File            | Description                                                                                          |
|----------------------------|------------------------------------------------------------------------------------------------------|
| **core_params.js**         | Contains all GA4 event parameters and their data type                                                |
| **custom_config.js**       | Contains static variables that can be reused throughout the whole repository (e.g., `GA4_START_DATE` or lookback window) |
| **helpers.js**             | Contains utility JavaScript functions that help generate SQL strings that would otherwise be tedious to read or write |


Package files
This folder contains files that are needed for the Dataform package to work properly.

| File                   | Description                                                                                      |
|------------------------|--------------------------------------------------------------------------------------------------|
| **dataform.json**      | Contains configuration settings for the Dataform project, including dependencies and environment setup |
| **package.json**       | Specifies the project's dependencies and scripts, and includes metadata such as the project name and version |
| **package-lock.json**  | Automatically generated file that locks the exact versions of the dependencies for reproducibility |
| **.gitignore**         | Specifies files and directories that should be ignored by Git, preventing them from being tracked in version control |



Looker Studio report templates
Website diagnostics
1 Looker Studio template (daily sessions)
Troubleshooting

Support & contact
Support
Users of the open-source and the Core variant of GA4Dataform are not eligible for support.
Contact
If you have any other questions, feel free to contact us at: hello@ga4dataform.com.
