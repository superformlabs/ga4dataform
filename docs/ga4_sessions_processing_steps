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


