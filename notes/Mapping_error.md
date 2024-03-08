  ### BA replated
  **Note:** Unique Balancing Authority values in SUBREGION include 'CISO', 'ERCO', 'ISNE', 'MISO', 'NYIS', 'PJM', 'PNM', 'SWPP'.  

  And from the data source:  
  - **California Independent System Operator (CISO):** No subregion map provided.  
  - **Electric Reliability Council of Texas, Inc. (ERCO):** Uses weather mapping as subregion; demand piece and clear mapping/region not provided.  
  - **Midcontinent Independent System Operator, Inc. (MISO):** Local Resource Zones mapped to Local Balancing Authorities as follows:
    - 1: DPC, GRE, MDU, MP, NSP, OTP, SMP
    - 2: ALTE, MGE, MIUP, UPPC, WEC, WPS
    - 3: ALTW, MEC, MPW
    - 4: AMIL, CWPLP, GLH, SIPC
    - 5: AMMO, CWLD
    - 6: BREC, CIN, HE, HMPL, IPL, NIPS, SIGE 
    - 7: CONS, DECO
    - 8: EAI
    - 9: CLEC, EES, LAFA, LAGN, LEPA
    - 10: EES, SME

  - **New England ISO (ISNE):** This is perfect  
    ![ISNE New England](./photo/ISONewEngland.jpg)



  - **New York Independent System Operator (NYIS):**

  - **PJM Interconnection, LLC (PJM):**wasnot perfect seeming like the subregion is smaller then rb

  - **Public Service Company of New Mexico (PNM):**This one the rb does not serperate at all 

  - **Southwest Power Pool (SWPP):**


### Problematic BA and rb Mapping

- **GCPD p4:**  
  ![GCPD p4](../photo/Missing_BA_Code_GCPD.png)
- **WAUM p20:**  
  ![WAUM p20](../photo/Missing_BA_Code_WAUW.png)
- **SPA p84:** Overlap multiple rb  
  ![SPA p84](../photo/Missing_BA_Code_SPA.png)

- **TEPC p27:**
  ![plot](../photo/Missing_BA_Code_TEPC.png)

- **TPWR p1:**
  ![plot](../photo/Missing_BA_Code_BANC.png)

- **DOPD p3:**
  ![plot](../photo/Missing_BA_Code_TPWR.png)

- **JEA p3:**
  ![plot](../photo/Missing_BA_Code_JEA.png)
Two small piece

- **FMPP p102:**
![plot](../photo/Missing_BA_Code_FMPP.png)

- **CHPD p1:**CHPD cross p1 and p3
![plot](../photo/Missing_BA_Code_CHPD.png)


```python
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
```


### BA to rb Specific Cases

- **LDWP p10:** Too small to capture  
  ![LDWP p10](../photo/Missing_BA_Code_LDWP.png)

- **LGEE p108,p109:** Overlap with other major BAs  
  ![LGEE](../photo/Missing_BA_Code_LGEE.png)

- **LDWPPGE p5:** 
![plot](../photo/Missing_BA_Code_PGE.png)
too small ti detect

- **LDWP- **LDWPSRP p28:** 
![plot](../photo/Missing_BA_Code_SRP.png)

- **TEC p101:** 
![plot](../photo/Missing_BA_Code_TEC.png)

- **OVEC p112v
![plot](../photo/Missing_BA_Code_OVEC.png)
Too small

- **TAL p101:** 
![plot](../photo/Missing_BA_Code_TAL.png)
Too small

- **BANC p9:** 
![plot](../photo/Missing_BA_Code_BANC.png)
For BANC it is too small to capture by the existing code

- **PSEI p1:** 
![plot](../photo/Missing_BA_Code_PSEI.png)
too fregmented

- **SCL p1:** 
![plot](../photo/Missing_BA_Code_SCL.png)
Too small to capture by the original code

- **NBSO p34:** 
![plot](../photo/Missing_BA_Code_NBSE.png)
compete within a rb just too small

- **FPC p101:** slighly too big
![plot](../photo/Missing_BA_Code_FPC.png)

- **NSB p101:** Extend to the sea
![plot](../photo/Missing_BA_Code_NSB.png)

- **HST p102:** island
![plot](../photo/Missing_BA_Code_HST.png)

- **SEPA p94:** too small
![plot](../photo/Missing_BA_Code_SEPA.png)

- **SCEG p96:** Slightly larger than than rb
![plot](../photo/Missing_BA_Code_SCEG.png)

- **GVL p101:** too small
![plot](../photo/Missing_BA_Code_GVL.png)

- **IID p10:** too small
![plot](../photo/Missing_BA_Code_IID.png)

- **TIDC p9:** too small
![plot](../photo/Missing_BA_Code_TIDC.png)


```python
{
    "LDWP": "p10",
    "GCPD": "p109",
    "LGEE": ["p109","p108"],
    "PGE": "p5",
    "SRP": "p28",
    "TEC": "p101",
    "OVEC": "p112",
    "TAL": "p101",
    "BANC": "p9",
    "PSEI": "p1",
    "SCL": "p1",
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
```

### Generation-Only BAs
consist of a power plant or group of power plants and do not directly serve retail customers. Therefore, they only report net generation and interchange and do not report demand or demand forecasts.

Entities like Avangrid Renewables, LLC (AVRN) and others are generation-only, not serving retail customers directly.

- **Avangrid Renewables, LLC (AVRN)**
- **Arlington Valley, LLC – AVBA (DEAA)**
- **GridLiance (GLHB)**
- **Gridforce Energy Management, LLC (GRID)**
- **Griffith Energy, LLC (GRIF)**
- **Gila River Power, LLC (GRMA)**
- **NaturEner Power Watch, LLC (GWA)**
- **New Harquahala Generating Company, LLC – HGBA (HGMA)**
- **Southeastern Power Administration (SEPA)**
- **NaturEner Wind Watch, LLC (WWA)**
- **Alcoa Power Generating, Inc. – Yadkin Division (YAD)**

```python
{'AVRN',
 'DEAA',
 'GLHB',
 'GRID',
 'GRIF',
 'GRMA',
 'GWA',
 'HGMA',
 'WWA',
 'YAD'}
```
### RETIRED BALANCING AUTHORITIES

Entities occasionally stop performing the BA role because their electric system is incorporated into another BA's system or they have made other arrangements. Five BAs retired after July 1, 2015, the first date of EIA-930 data availability:


- **Gila River Power, LLC (GRMA)** – Retired May 3, 2018
- **Ohio Valley Electric Corporation (OVEC)** – Retired December 1, 2018
- **Utilities Commission of New Smyrna Beach (NSB)** – retired January 8, 2020
- **Electric Energy, Inc. (EEI)** – retired February 29, 2020
- **PowerSouth Energy Cooperatives (AEC)** – retired September 1, 2021

## Rare but Problematic

- **DEAA-Arlington Valley**: Appears to be a production facility.
  
- **CPLW**: Located in p56.
  
- **EEI - Edison Electric Institute**: No specific issues listed, implies general problems.
  
- **WAUW**: [Balancing Authorities as of January 2017](https://www.wecc.org/Administrative/Balancing_Authorities_JAN17.pdf). Errors due to not matching shape; assigned to p18.
  
- **WAUE**: Possibly Western Area Power Administration—Upper Great Plains East. No specific issues listed, implies general problems.

Entities with issues include:
```json
{
 "CPLW": "Located in p56",
 "DEAA": "Production facility",
 "EEI": "General issues",
 "WAUE": "Possibly Western Area Power Administration—Upper Great Plains East",
 "WAUW": "Errors due to not matching shape; assigned to p18"
}
```

For CPLW, I cound not really find where it should be, p56 is base on google and guess



## After the join in dmeand mapping, there is a issue with the following county


========================================================================
Unique FIPS that did not find a match in county_map_df:
['11000' '46113']
Unique FIPS that did not find a match in demand_data_df,this idencate they does not ahve diemand:
['09110' '09120' '09130' '09140' '09150' '09160' '09170' '09180' '09190'
 '11001' '32017' '46102' '48103' '48157' '48227' '48301' '48475' '48495']


DC does not have one but 110001 is not emty, we consider two of them the same

46113, may be no longer exist

09 series are newly created:
https://www.federalregister.gov/documents/2022/06/06/2022-12063/change-to-county-equivalents-in-the-state-of-connecticut
Fine to be ignore, overlap any way
32017
Problem,populated

46102
https://www.ddorn.net/data/FIPS_County_Code_Changes.pdf

48103
Crane County, TX
by https://hifld-geoplatform.hub.arcgis.com/datasets/geoplatform::control-areas/explore?location=31.771481%2C-103.201139%2C8.92
all texus are in the ERCO region
