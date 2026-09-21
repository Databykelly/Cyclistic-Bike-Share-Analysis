# Cyclist Bike Share Analysis 

Data analysis of Cyclistic bike share usage to understand how casual riders and annual members use the service differently during Q1 in 2019 and 2020

## Business Problem

Cyclistic wants to increase the number of annual memberships, but it does not yet have enough insight into how casual riders differ from annual members to design an effective strategy for converting casual riders into Annual members.

## Business Task 

The task this project looks to acccomplish is to analyze Cyclistic historical bike trip data to identify the behavioral differences between casual members and annual members so the marketing team can design a targeted, evidence based campaign to convert Casual riders into Annual members.

## Audience

**Primary:** Lily Moreno (Director of Marketing) and the marketing 
analytics team, the direct recipients of this analysis, who will 
use it to shape campaign strategy.

**Secondary:** Cyclistic executives, who must approve any resulting 
marketing recommendations. Because of this, findings need to be 
clear, visually compelling, and framed around business impact 
rather than analytical process.

## Possible Metrics

- tripduration / started_at to ended_at could produce **Total number of rides**
- trip_id / ride_id could produce **Total rides**
- start_time / started_at could produce **Number of rides by day of week** or **Number of rides by hour**
- to_station_name / end_station_name could produce **Number of rides originating from each station**
- usertype / member_casual **could be used as comparison variable**


## Prepare

### Data Source 

This analysis uses two quarters of Divvy trip data:
- **2019 Q1** (Jan–Mar 2019)
- **2020 Q1** (Jan–Mar 2020)

Data was downloaded from the official Divvy trip data repository, 
provided by Motivate International Inc. under license to the 
City of Chicago:  
https://divvy-tripdata.s3.amazonaws.com/index.html

This project analyzes only these two quarters, chosen to allow 
a direct year over year comparison for the same three month 
period (Q1), while keeping the dataset manageable in scope.

### Data Organization

Each quarter is a separate CSV file in long format.

### ROCCC Check

- **Reliable:** Raw ride-level data, not pre-aggregated or altered
- **Original:** Sourced directly from Motivate International Inc.
- **Comprehensive:** Contains the fields needed to answer the 
  business task, though trip duration must be derived for 2020
- **Current:** ⚠️ Data is from 2019–2020, several years old and usage patterns may have shifted since then
- **Cited:** Official source, publicly documented. (see Data Source)

### Licensing, Privacy, Security, Accessibility

- **Licensing:** Data is made publicly available by Divvy/Motivate 
  International Inc. under their public data license, which permits 
  use for analysis provided the source is credited (see Data Source).
- **Privacy:** No personally identifiable information (names, 
  addresses, payment details) is included. Ride-level data is 
  anonymized.
- **Security:** Files were downloaded directly from the official 
  public S3 bucket via HTTPS, requiring no login or credentials, 
  and stored locally for analysis.
- **Accessibility:** Data is freely and publicly available to 
  anyone via the link in Data Source.

### Data Integrity Verification


The following checks will be performed before analysis:

- Row counts per file, to confirm the data loaded completely
- Column headers, to confirm they match the expected schema
- Missing/null values in key fields such as start/end time and rider type
- Duplicate ride IDs
- Invalid or logically inconsistent timestamps
- Zero or unusually long ride durations
- Unexpected rider-type categories

### Known Problems with the Data

- Schema differs between 2019 Q1 and 2020 Q1 (see Data Organization), 
  requiring standardization before combined analysis
- `tripduration` is not provided in 2020 and must be calculated
- Data is several years old (2019–2020), so findings may not fully 
  reflect current ridership behavior
