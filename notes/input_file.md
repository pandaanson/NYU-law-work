## Data Sources

1. **TELL Data**: Calibration and evaluation notebook from the TELL project.
   - [TELL MLP Calibration Evaluation Notebook](https://github.com/IMMM-SFA/tell/blob/main/notebooks/tell_mlp_calibration_evaluation.ipynb)
```python
   import tell
   current_dir = os.path.join(os.path.dirname(os.getcwd()))
   tell_data_dir = os.path.join(current_dir, 'tell_data')
   tell.install_tell_raw_data(data_dir=tell_data_dir)
   tell.install_quickstarter_data(data_dir=tell_data_dir)
   tell.install_sample_forcing_data(data_dir=tell_data_dir)

```
    Population come from here
    - county_populations_2000_to_2020.csv

2. **County Shape File:** `cb_2018_us_county_500k.zip` [11 MB]  
   [US Census Bureau Cartographic Boundary Files](https://www.census.gov/geographies/mapping-files/time-series/geo/carto-boundary-file.html)
   - store as cb_2018_us_county_500k folder
   population prediction
   - store in Electric_Retail_Service_Territories folder
   mapping BA to county
   - service_area folder

3. **County Base Weather Data:**  
   [OSTI.GOV Weather Data](https://www.osti.gov/biblio/1960548)


4. **Detailed Weather Data:**  
   [OSTI.GOV Detailed Weather Data](https://www.osti.gov/biblio/1885756)  
   This is used as a reference grid.

5. **RB Shape File:**  
   [NREL ReEDS 2.0](https://github.com/NREL/ReEDS-2.0)
   - store in US_CAN_MEX_PCA_polygons
   also load data 
   - ReEDS load data folder

6. **EIA Demand Data:**  
   [U.S. EIA Grid Monitor](https://www.eia.gov/electricity/gridmonitor/about)
   -store in folder EIA 930

7. **Control Area Shape File:**  
   [HIFLD Control Areas](https://hifld-geoplatform.hub.arcgis.com/datasets/geoplatform::control-areas/explore?location=33.336357%2C-112.615515%2C3.65)

8. **Subregion Level Data:**  
   [EIA Cleaned Hourly Electricity Demand Code](https://github.com/truggles/EIA_Cleaned_Hourly_Electricity_Demand_Code/blob/master/step1_get_eia_demand_data.ipynb)
