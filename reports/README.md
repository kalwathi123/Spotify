# Project Overview
This project involves analyzing Spotify streaming history data from 2020 to 2025. The goal is to preprocess the data, generate insights, and visualize the results using Tableau.

## Folder Structure

```
project-root/
├── data/
│   ├── raw/ your_data_.json
├── notebooks/
│   └── Data-Preprocessing.ipynb
├── reports/
│   └── README.md
├── visualizations/
│   └── tableau/
│       └── *.png
└── README.md
```
## Libraries and Modules

The following libraries and modules are used in this project:

- `pandas`: For data manipulation and analysis.
- `tabulate`: For displaying data in tabular format.
- `pytz`: For timezone conversions.
- `datetime`: For date and time operations.

## Data Preprocessing

## Data Preprocessing

1. **Load Data**: Read the JSON file containing streaming history data.
2. **Convert Time**: Convert `ms_played` to minutes and round to one decimal place.
3. **Rename Columns**: Rename `ms_played` to `minutes_played`.
4. **Reorder Columns**: Reorder columns to make `minutes_played` the fourth column.
5. **Convert Timezones**: Convert `utc_time_zone_ts` to local time zones based on the country.
6. **Calculate Start Time**: Calculate the start time by subtracting `minutes_played` from `utc_time_zone_ts`.
7. **Drop Unnecessary Columns**: Drop columns that are not needed for analysis (`ms_played`)(`offline_timestamp`), (`ip_addr`),(`incognito_mode`).
8. **Standardize Column Names**: Standardize column names for consistency:
   - `platform` standardization:(Refer the dummy devices name for integrity purpose)
     - 'Linux [x86-64 0]' -> 'LINUX'
     - 'Android OS 10 API 29 (samsung, SM-M307F)' -> 'ANDROID'
     - 'Windows 10 (0.0.0; x64; AppX)' -> 'WINDOWS'
     - 'Windows 10 (0.0.0; x64; AppX)' -> 'WINDOWS'
     - 'Windows 10 (0.0.0; x64)' -> 'WINDOWS'
     - 'Windows 10 (0.0.0; x64)' -> 'WINDOWS'
     - 'Partner android_tv Droidlogic;SMART_TV;756a522d9fxxxxxxxxxxxxxxxxxxxx;;tpapi' -> 'SMART_TV'
     - 'android' -> 'ANDROID'
     - 'windows' -> 'WINDOWS'
     - 'ios' -> 'IOS'
     - 'playstation' -> 'OTHERS'
     - 'not_applicable' -> 'OTHERS'
   - `reason_end` standardization:
     - 'trackdone' -> 'TRACKDONE'
     - 'logout' -> 'LOGOUT'
     - 'endplay' -> 'ENDPLAY'
     - 'unexpected-exit-while-paused' -> 'EXIT'
     - 'fwdbtn' -> 'FWDBTN'
     - 'unknown' -> 'UNKNOWN'
     - 'remote' -> 'REMOTE'
     - 'backbtn' -> 'BACKBTN'
     - 'trackerror' -> 'TRACKERROR'
     - 'unexpected-exit' -> 'EXIT'
   - `conn_country` standardization:
     - 'IN' -> 'INDIA'
     - 'US' -> 'UNITED STATES'
     - 'DE' -> 'GERMANY'
     - 'GB' -> 'UNITED KINGDOM'
     - 'PR' -> 'PUERTO RICO'
   - `reason_start` standardization:
     - 'clickrow' -> 'CLICKROW'
     - 'trackdone' -> 'TRACKDONE'
     - 'appload' -> 'APPLOAD'
     - 'playbtn' -> 'PLAYBTN'
     - 'fwdbtn' -> 'FWDBTN'
     - 'trackerror' -> 'TRACKERROR'
     - 'remote' -> 'REMOTE'
     - 'backbtn' -> 'BACKBTN'
     - 'unknown' -> 'UNKNOWN'
9. **Save Processed Data**: Save the processed data to a CSV file.

## Data Exploration

1. **Top Platforms**: Identify the platform with the highest listening count.
2. **Top Artists**: Identify the top artist for each quarter from 2020 to 2025.
3. **Peak Listening Hours**: Determine the peak listening hours in the format of intervals (e.g., "6:00 AM to 12:00 PM").
4. **Listening Distribution by Year**: Analyze the distribution of listening intervals for each year.
5. **Genre Analysis**: Analyze the distribution of genres over the years.
6. **Country Analysis**: Determine the top countries with the highest listening counts.

## Visualization

1. **Tableau**: Load the processed data into Tableau.
2. **Generate Insights**: Create visualizations to generate insights from the data.

## Next Steps

1. **Update Data in Tableau**: Load the processed data into Tableau and generate insights.
2. **Generate Reports**: Create reports based on the insights generated in Tableau.

## Authors

- [Mohammed Abdul Rahman Kalwathi](https://github.com/kalwathi123/Spotify)