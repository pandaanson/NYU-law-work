Repurpose dir\
This is the sucessor of https://github.com/pandaanson/data-download\
Mapping creater done,note this code is not design to read in other input
The mapping creater also are the one generate all the graph
EIA exam, check the EIA dataset

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

8. Subregion level data
https://github.com/truggles/EIA_Cleaned_Hourly_Electricity_Demand_Code/blob/master/step1_get_eia_demand_data.ipynb

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


Subregion

Mar 3
[X] Play with demand data
Note, some ba are GENERATION-ONLY BAS

Mar 4
[]Create the mapping between BA , and the 'rb'
Note county with sub region:Unique Balancing Authority values in SUBREGION:
['CISO' 'ERCO' 'ISNE' 'MISO' 'NYIS' 'PJM' 'PNM' 'SWPP']

And from the date source
California Independent System Operator (CISO)
CISO does not have subregion map provided
Electric Reliability Council of Texas, Inc. (ERCO)
It use the weather mapping as subregion , we do not have this piece of demad provided and the mapping and the region is not that clear
Midcontinent Independent System Operator, Inc. (MISO)
Local Resource Zone		Local Balancing Authority
 
1				DPC, GRE MDU, MP, NSP, OTP, SMP
 
2				ALTE, MGE, MIUP, UPPC, WEC, WPS
 
3				ALTW, MEC, MPW
 
4				AMIL, CWPLP, GLH, SIPC
 
5				AMMO, CWLD
 
6				BREC, CIN, HE, HMPL, IPL, NIPS, SIGE 
 
7				CONS, DECO
 
8				EAI
 
9				CLEC, EES, LAFA, LAGN, LEPA
 
10				EES, SME


New England ISO (ISNE)
This is perfect
![plot](./photo/ISONewEngland.jpg)

New York Independent System Operator (NYIS)

PJM Interconnection, LLC (PJM)
mid

Public Service Company of New Mexico (PNM)
This one the rb does not serperate at all 

Southwest Power Pool (SWPP)


Problematic:
GCPD p4
WAUM p20
SPA p84
TEPC p27
TPWR p1
DOPD p3
JEA p3
![plot](./Missing_BA_Code_JEA.png)
Two small piece

FMPP p102
CHPD p1
![plot](./Missing_BA_Code_CHPD.png)
CHPD cross p1 and p3
{
    "GCPD": "p4",
    "WAUM": "p20",
    "SPA": "p84",
    "TEPC": "p27",
    "TPWR": "p1",
    "DOPD": "p3",
    "JEA": "p3",
    "FMPP": "p102",
    "CHPD": "p1"
}


BA rb
LDWP p10
![plot](./Missing_BA_Code_LDWP.png)
Too small to capture
GCPD  p109
LGEE p109
![plot](./Missing_BA_Code_LGEE.png)
Need attention
PGE p5
SRP p28
TEC p101
OVEC p112
TAL p101
BANC p9
![plot](./Missing_BA_Code_BANC.png)
For BANC it is too small to capture by the existing code
PSEI p1
SCI p1
NBSO p34
FPC p101
NSB p101
HST p102
SEPA p94
SCEG p96
GVL p101
IID p10
TIDC p9

{
    "LDWP": "p10",
    "GCPD": "p109",
    "LGEE": "p109",
    "PGE": "p5",
    "SRP": "p28",
    "TEC": "p101",
    "OVEC": "p112",
    "TAL": "p101",
    "BANC": "p9",
    "PSEI": "p1",
    "SCI": "p1",
    "NBSO": "p34",
    "FPC": "p101",
    "NSB": "p101",
    "HST": "p102",
    "SEPA": "p94",
    "SCEG": "p96",
    "GVL": "p101",
    "IID": "p10",
    "TIDC": "p9"
}






