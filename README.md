Repurpose dir\
This is the sucessor of https://github.com/pandaanson/data-download\
Mapping creater done,note this code is not design to read in other input\

Data source:
1. From tell
https://github.com/IMMM-SFA/tell/blob/main/notebooks/tell_mlp_calibration_evaluation.ipynb
```
import tell
current_dir =  os.path.join(os.path.dirname(os.getcwd()))
tell_data_dir = os.path.join(current_dir, r'tell_data')
tell.install_tell_raw_data(data_dir = tell_data_dir)
tell.install_quickstarter_data(data_dir = tell_data_dir)
tell.install_sample_forcing_data(data_dir = tell_data_dir)
```
Population come from here

2. County shape file cb_2018_us_county_500k.zip [11 MB]
https://www.census.gov/geographies/mapping-files/time-series/geo/carto-boundary-file.html

3. County base weather data
https://www.osti.gov/biblio/1960548

4. Detail weather data:
https://www.osti.gov/biblio/1885756
This is use a reference grid

5. rb shape file
https://github.com/NREL/ReEDS-2.0

6. EIA demand data 
https://www.eia.gov/electricity/gridmonitor/about

7. Contral area shape file
https://hifld-geoplatform.hub.arcgis.com/datasets/geoplatform::control-areas/explore?location=33.336357%2C-112.615515%2C3.65

Roadmap:
Mapping(mapping creater)
county weather===Mapping===>subregion weather(data generation for tell)



Feb 26 Task\
[X]Create Repo\
[X]Fix emty and keep only continental USA\
[X]Create mapping for subregion to region\

Feb 27 Task\
[X]Create Code to autmate generate historical and future data

Note:
For generate file
Historical:
File Name:1984_01_01_02_UTC_County_Mean_Meteorology.csv
column:FIPS	T2	Q2	U10	V10	SWDOWN	GLW
Furture:
File name:2049_01_01_02_UTC_County_Mean_Meteorology.csv
column:FIPS	T2	Q2	U10	V10	SWDOWN	GLW


Target file:
Historical:
File name:AEC_WRF_Hourly_Mean_Meteorology_2015.csv
Column:Time_UTC	T2	Q2	SWDOWN	GLW	WSPD
Future:
File name:AEC_WRF_Hourly_Mean_Meteorology_2020.csv
Column:Time_UTC	T2	Q2	SWDOWN	GLW	WSPD


Feb 29
[]Prepare data for tell training

Note for tell:
Tell file require


    # Rename the columns to add the units to each variable:
    df.rename(columns={"DF": "Forecast_Demand_MWh",
                       "Adjusted D": "Adjusted_Demand_MWh",
                       "Adjusted NG": "Adjusted_Generation_MWh",
                       "Adjusted TI": "Adjusted_Interchange_MWh"}, inplace=True)
train:Year	Month	Day	Hour	Forecast_Demand_MWh	Adjusted_Demand_MWh	Adjusted_Generation_MWh	Adjusted_Interchange_MWh	Total_Population	T2	Q2	SWDOWN	GLW	WSPD


