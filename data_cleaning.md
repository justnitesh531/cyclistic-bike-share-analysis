
# Cyclistic Data Cleaning Documentation

## 1. Dataset Overview
- Study period: October 2025 to September 2026.
- Source: Divvy trip data.
- Number of monthly CSV files: 12.
- Original combined records: 6,171,785.

## 2. Data Preparation

### Duplicate Records
- Identified 35 duplicate ride records.
- All duplicate groups contained identical records.
- Removed duplicates using ride_id.
- Records after deduplication: 6,171,750.

### Missing Values
Missing values were identified in:
- start_station_name: 1,289,480
- end_station_name: 1,355,473
- end_lat: 5,445
- end_lng: 5,445

These records were retained because missing station information
does not prevent the main rider-type and ride-duration analyses.

### Ride Duration Filtering
Excluded records that did not meet these conditions:
- ended_at must be later than started_at.
- Ride duration must not exceed 24 hours.

Records after filtering: 6,166,404.

A total of 5,346 records were excluded by this filtering step.

## 3. Data Anomaly
The CSV supplied in the January 2026 download was named
202501-divvy-tripdata.csv, although its timestamps showed
January 2026 data. The file was renamed to
202601-divvy-tripdata.csv for consistency.

## 4. Final Analysis Dataset
The final analysis table was named analysis_trips.

Final records: 6,166,404.

The original all_trips table was preserved.
