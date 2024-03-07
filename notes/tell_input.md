To feed in to the tell model 

```python



```

### the input

- create an array contain all p-zone

- the complied_historica

#### the data file are formate as follow

title:

```python
file_name = f'{p-zone}_historical_data.csv'
```

- one file should include all the demand for that p-zone

columns (on your left is the column name and the right hand side is what they mean):
- **Hour**
- **Month**
- **Adjusted_Demand_Mwh:** Total demand of that p-zone
- **Total_Population:** Total population of the p-zone
- **T2:** weighted average of that Temperature for 2 meter
- **SWDOWN:** Weighted avergae short wave radiation
- **GLW:**weighed average long wave radiation
- **WSPD:** wind speed
- **Q2:** humidity


For prediction, less the dmand and popoulation and same format


