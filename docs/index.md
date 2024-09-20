GA4Dataform docs
Introduction
Overview
Versions
About us
License
Getting started
Requirements
Installation guide
Using GA4Dataform after installation
Product features
Core
Premium
Premium+
Premium+ Agency
Output tables
Base tables
Aggregated tables
Looker Studio report templates
Assertions
Troubleshooting
Files (.sqlx, .js & .json)
definitions
includes
package files
Support & contact
Support
Contact
Introduction
Overview
GA4Dataform is your one-click solution to harness the full power of GA4 data in BigQuery, without the hassle. Transform your raw GA4 event data into actionable insights with industry-leading, enterprise-level efficiency and precision. Designed for digital analysts, technical marketers, data teams, and developers.
Versions
Open-source version
The open-source version of GA4Dataform is available as a public repository on Github. This version contains the Dataform models without the ‘one-click’ installer app. The open-source version contains the same .sqlx and .js files as the ‘Core’ variant of GA4Dataform.
Installer version
The installer version of GA4Dataform is a ‘one-click’ app that handles the complete installation of the package. This version is available in the Superform Labs store.
About us
GA4Dataform is a product by Superform Labs OÜ. Our company is settled in Estonia (EU), but we work remotely from different countries across the world. Together we have decades of experience in web and marketing analytics.

Jules Stuifbergen | Data Analyst | LinkedIn
Krisztián Korpa | Analytics Engineer | LinkedIn
Artem Korneev | Analytics Developer | LinkedIn
Simon Breton | Analytics Engineer | LinkedIn
Johan van de Werken | Data Analyst | LinkedIn
License
GNU General Public License. This file is part of "GA4 Dataform Package". Copyright (C) 2023-2024 Superform Labs <hello@ga4dataform.com> Artem Korneev, Jules Stuifbergen, Johan van de Werken, Krisztián Korpa, Simon Breton. "GA4 Dataform Package" is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>.

Getting started
Requirements
To use GA4Dataform you need:
An active GA4 property linked to a Google Cloud project with billing enabled. If the link is configured in the right way you’ll see a data set analytics_<property_id> in BigQuery.
A license key. You’ll receive the license key in the receipt email after ordering the product in the Superform Labs store. The license key is linked to the email address used in the store. License keys are valid for a limited time (dependent on the product plan) and can be used as often as you want, unless there is a reason to disable your license key.
Installation guide
New installation 
Follow the instructions from our app. To be completed

Update
To be completed
Dataform Repository
Structure overview
The structure used in the repository is inspired by Dataform's best practices with a few additions on our part.


definitions
├── 01_sources
│   ├── declarations.js
│   ├── stg_ga4_events.sqlx
│   ├── stg_ga4_sessions.sqlx
├── 02_intermediate
│   ├── int_ga4_events.sqlx
│   ├── int_ga4_sessions.sqlx
├── 03_outputs
│   ├── aggregated
│   │   ├── demo_daily_sessions_report.sqlx
│   │   ├── demo_diagnostics.sqlx
│   ├── base
│   │   ├── ga4_events.sqlx
│   │   ├── ga4_sessions.sqlx
├── assertions
│   ├──assertion_logs.sqlx
│   ├──assertions_event_id_uniqueness.sqlx
│   ├──assertions_session_duration_validity.sqlx
│   ├──assertions_session_id_uniqueness.sqlx
│   ├──assertions_sessions_validity.sqlx
│   ├──assertions_tables_timeliness.sqlx
│   ├──assertions_transaction_id_completeness.sqlx
│   ├──assertions_user_pseudo_id_completeness.sqlx
├── extra
│   ├── ga4
│   │   ├── source_categories.js
├── unit_testing
│   ├── unit_test.sqlx
├── includes
│   ├── core_params.js
│   ├── custom_config.js
│   ├── helpers.js
.gitignore
dataform.json
package-lock.json
package.json
Directories description

directory
description
01_sources
Contains declarations and staging models
02_intermediate
Contains intermediate models
03_outputs
Contains output models
03_outputs/aggregated
Contains different aggregated tables that can be directly connected to Looker Studio or other visualization tool
03_outputs/base
Contains output tables that should be used for aggregations
assertions
Contains all the assertions that check the data quality of our model
extra
Is it needed?
unit_testing
Contains models related to unit testing
includes
Contains all JS files with reusable variables and functions that help manage the repository


Models
model
description
Partition
Cluster
stg_ga4_events
GA4 staging events table that incrementally queries the raw GA4 export and applies partitioning, clustering, cleaning and several fixes




stg_ga4_sessions
GA4 staging sessions table that incrementally queries stg_ga4_events table and creates session-level dimensions and metrics




int_ga4_events
GA4 intermediate events table that widens the staging table with useful dimensions




int_ga4_sessions
GA4 intermediate sessions table that widens the staging table with useful dimensions




ga4_events
GA4 output events table that can be used for further transformations or aggregations




ga4_sessions
GA4 output sessions table that fixes sessions broken by midnight, adds last non-direct click attribution and can be used for further transformations or aggregations




demo_daily_sessions_report






demo_diagnostics






unit_test









BigQuery Project
GA4Dataform generates tables in BigQuery. Everything will be under the dataform-package project with the following structure: 

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
Using GA4Dataform after installation
First SQL workflow run
Change schedule
Git Connection
GA4Dataform is not (yet) linked to any git repository. If any changes and customisation are made to the project, changes should be committed to the default Dataform repository. Versioning is not available. 
Releases and Scheduling
The installer will automatically create a Release and a Workflow configuration using the dataform API. The release will be triggered at 9AM UTC+00:00 and the workflow will be triggered at 10AM UTC+00:00.

These values can be modified directly from the dataform UI without impacting the functionality of the project. 
Project Location
Location of the dataform project is set during the installation. It is based on the Location of the GA4 dataset
Product features
Core features
Basic features | No support & updates
Incremental loading

Partitioning & Clustering
Fix session breakage on midnight
Default channel grouping
Timestamps in local time zone
Last non-direct click attribution model (session-based)
Easy fix for Paid Search misattribution when gclid,gbraid or wbraid are available
Event ID
Creating unique event ID based on event_name, event_timestamp_micros, user_pseudo_id, ga_session_id, batch_page_id, batch_ordering_id, batch_event_index, engagement_time_msec.

Default Filtering
Session with null session_id and user_pseudo_id null are filtered from final input (in the stg_ga4_sessions model)
Duplicated hit are removed 

Basic data quality checks (see Assertions section)
Looker Studio report templates (see Looker Studio report templates section)
Event filters, custom parameters, custom channels etc… (see Custom Configuration section)
Peripheral features
Time struct 
Struct containing event_date_YYYYMMDD, event_timestamp_micros, event_timestamp_utc, user_first_touch_timestamp, user_first_touch_timestamp_utc
synthetic_bundle
Synthetic event are filtered out in the stg_ga4_events.sqlx model
Engaged session
Is direct session
Debug session
Param gtm_debug
With cross domain
Url_params._gl
has_source


Custom Configuration
Custom Google Analytics 4 parameters (CUSTOM_PARAMS_ARRAY)
Adding description here
Event filters
CLICK_IDS_ARRAY
URL_PARAMS_ARRAY
LAST_NON_DIRECT_LOOKBACK_DAYS
EVENTS_TO_EXLUDE

Data Quality
Filtering
Null user_pseudo_id and session_id in stg_ga4_sessions.sqlx model
Transformation
Change '(not set)' translation id to null 
Deduping duplicates event_id in int_ga4_events.sqlx (deduped CTE)
Meta Info
Checking for measurement_protocol_hit 


Assertions
Assertions logic overview 
Each assertion execution is logged in a dedicated BigQuery table easily accessible (assertion_logs). Failed or passed assertions result are log. Assertions log table contains:
Execution date of assertions
Name of the assertion
Model on which the assertion has been run
A sample of flawed values if any anomalies has been detected (i.e list of duplicated event id)
The status of the assertion, failed or passed. 
A detailed error message. 

Assertions can be independently deactivated in the custom_config.js configuration file. 

All Assertions are tagged with the string “assertions”

We have 5 main categories of assertions:

Uniqueness: Checking if the column we are testing contains duplicates values 

Validity: Checking if the column or table we are testing is “valid” from a business point of view. I.e session duration should never be negative. 

Timeliness: Checking if tables we are testing are “on time”. I.e we expect that the max(date) of the event table to be the same as the max(date) of the session table.

Freshness: We expect tables to be up to date. Freshness is an expectation that needs to be set by the user depending on their own context. 

Completeness: Check if the column we are testing is complete and that we are not missing any values. 


This folder contains assertion files:

assertion
description
assertion_logs
Building an incremental table to log results of all the assertions.
assertions_event_id_uniqueness
Check if the event id is unique. Return sample of duplicates event id if the assertion fails.
assertions_session_duration_validity
Check if session duration is not negative.
assertions_session_id_uniqueness
Check if session id is unique. Return sample of session id if the assertion fails. 
assertions_sessions_validity
Check the validation of sessions using multiple criterias: landing_page_location, user_pseudo_id, session_id, session_date, device.category, session_start_timestamp_utc should not be null.


assertions_tables_timeliness
Checking if session and events tables across different layers (staging, intermediate etc…) are always synchronized. 
assertions_transaction_id_completeness
Checking for null or “not set” transactions IDs
assertions_user_pseudo_id_completeness
Checking for null user_pseudo_id


Includes
This folder contains .js files with functions that are used in the .sqlx files.

JavaScript file
description
core_params.js
Contains all GA4 event parameters and their data type
custom_config.js
Contains static variables that can be reused in the whole repository (like GA4_START_DATE or lookback window)
helpers.js
Contains utility JavaScript functions that help generate SQL strings that would otherwise be tedious to read or write

Package files
This folder contains files that are needed for the Dataform package to work properly.

file
description
dataform.json


package.json


package-lock.json


.gitignore


Looker Studio report templates
Website diagnostics
1 Looker Studio template (daily sessions)
Troubleshooting

Support & contact
Support
Users of the open-source and the Core variant of GA4Dataform are not eligible for support.
Contact
If you have any other questions, feel free to contact us at: hello@ga4dataform.com.



From Jules

So, I’ve installed ga4dataform.. now what?
Browse to the files
On the repository page, select the created repository you just created, and browse to the Development workspace


Browse to includes/custom_config.js and adjust the parameters to your needs

Add some customisations
Now, you can configure custom parameters you want in your events dataset. Let’s look at GA4 and just use those:

We see 7 custom dimensions, of which 6 are needed
clean_path is already in the model (as page.path)
6 are going to be configured
5 as string
1 as number (int)
I will rename the event param shop to become the column name shop_name
const CUSTOM_PARAMS_ARRAY = [
  // outside the core ones
  { name: "details", type: "string" },
  { name: "is_logged_in", type: "string" },
  { name: "items_in_cart", type: "int" },
  { name: "message", type: "string" },
  { name: "product_name", type: "string" },
  { name: "shop", type: "string", renameTo: "shop_name" },
];

This website uses q as search term url parameter, and some other URL parameters to indicate filters. Let’s add those:

Save your changes
When making changes, you have to test them (which we’re not going to do now, haha) and when it’s all working: push them into production.
First commit, then push
Commit

Push

You've pushed successfully when the workspace is up to date and the green checkmark shows
Run the model
Under “releases and scheduling”, you can find the preconfigured “production” configuration.

Click start execution, and fill in the popup

Click "Start Execution" now.
Check for success
Under “workflow execution logs” you can check if the model has ran succesfully

In this case, there is an error! Click “VIEW DETAILS”

If we scroll down to row 629 we see that”ae-prijsfilter” is an invalid column name. Oops! We should have tested..

Back to the source. Let’s rename the column to prijsfilter
       // custom
    { name: "q",cleaningMethod: lowerSQL },
    { name: "categorie",cleaningMethod: lowerSQL },
    { name: "ae-prijsfilter",cleaningMethod: lowerSQL, renameTo: 'prijsfilter' },
    { name: "kleur",cleaningMethod: lowerSQL },
    { name: "manufacturer",cleaningMethod: lowerSQL },

Remember
commit
push
Start new execution
Again
production
all tags
run with full refresh
Check for success - part 2
Go to the workflow execution logs, and click REFRESH until you’re tired
If all check marks are green, the model ran successfully!

Check Big Query
Go to Bigquery, and you should see the new tables.
Currently, the customisations are in the _outputs/ga4_events table in the schema under


Connect Looker Studio to the sessions table
Open Looker Studio
Add data source, choose Big Query
Browse to the demo_daily_sessions_report table
Use session_date as date range dimension

Click ADD
Now go wild!


From Artem

GA4 Sessions - Processing Steps

GA4 session table could provide following information:
Source / Medium / Campaign at least for three standart attributions:
Last click
Last non direct click (with particular lookback window - 90 days by default)
First click
For each attribution Default Channel Groups - by the same rules as in Google Analytics 4
Landing page, landing page referrer  and exit page, it could also be a struct with prepared host name, page path and query parameters
Sessions properties like: is_direct_session, is_engaged_session, is_debug_session, is_cross_domain
Unique session_id 
Session duration, engagement time 
Information about geo / device / app_info
User information: user_id, last_user_id, user_pseudo_id

These columns are often needed to build reporting and simplify data pipelines based on session data.

What is common session processing pipeline:
Extract all needed columns from raw GA4 data - to flat event tables
Clean and prepare events
Group events into sessions using unique session_id
Fix google’s default source / medium rules, add channel grouping
Add last non direct attribution

Sources to calculate source / medium
collected_traffic_source column
Source and medium from event_params
Utm parameters from page_location
click_ids from event_params or page_location, for example: gbraid, wbraid, gclid, dclid, srsltid and so on

After all sources combined together we need to apply additional logic to build a fixed source / medium on top of them. For example: if we have gclid, gbraid, wbraid source / medium should be google / cpc. Or if the referrer is %android-app://com.google% when google / organic and so on. Special rules for click ids, for social platforms, for aps.

For channel grouping Google provides a list of sources with more than 1100 rules to define groups for known domains. 

And on top of these steps we could calculate last non direct attribution and compare with GA UI and numbers in session_traffic_source_last_click. For some cases source / medium fixes could provide 15-20% less direct traffic - it means improving paid campaigns attribution.


And also there are a lot of special cases and small challenges, for example:
Schema are changing so be careful when you are processing historical data
Transaction value could be int or double or float you need to coalesce all possible numbers
Collected_traffic_source could be null for events, even if it exists for the first session’s hit 
Don’t forget to exclude synthetic_bundle events
For event_id use batch_page_id, batch_ordering_id, batch_event_index if they exists
Be very careful with fbclid parameter
Have a fun processing item_params (arrays plus nested plus arrays are better together)
Decide what to do with events with the same event_id
Count page_number for hits during the session






