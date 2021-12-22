# Star Trek Episode Library Project

Primary data is kept in a sqlite database located at `episode_data.db`. Feel free to fork and use the project
as you need, please contribute back any changes or updates as you find them.

Episode numbers, titles, and broadcast dates obtained from IMDB.

## SQLite Data Structure

Table: `episode`

|**Field Name**|**Data Type**|**Notes About the Field**|
|:---|:---|:---|
|id|integer|This is an interval unique episode ID and not related to the production number|
|series_id|integer|Foreign Key for the `series` table|
|season|integer||
|episode|integer||
|broadcast_date|date||
|stardate|text||
|universe_id|integer|Foreign Key for the `universe` table|
|production_number|text||


Table: `series`

This table is not only used to distinguish episodes but also
to distinguish the movies from the tv shows.

|**Field Name**|**Data Type**|**Notes About the Field**|
|:---|:---|:---|
|id|integer||
|slug|text|Slugs currently are standardized to a 3 character,  uppercase value|
|title|text|Full text description of the series|


Table: `universe`

Currently used to distingish between prime, mirror, and kelvin universes.

|**Field Name**|**Data Type**|**Notes About the Field**|
|:---|:---|:---|
|id|integer||
|name|text||


Table: `episode_sort`

|**Field Name**|**Data Type**|**Notes About the Field**|
|:---|:---|:---|
|episode_id|integer|Foreign Key for the `episode_id` table|
|slug_name|text|Used to distingish between different sorting options i.e. Universe Chronological|
|sort_order|integer||
