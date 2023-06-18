# Time Series Analysis : Zillow Home Value Forecast Model 

![image](https://github.com/Mugangasia/Time-Series-Analysis-Zillow-Home-Value-Forecast-Model/assets/98708792/a1330065-3a9c-47cd-a013-e751b0f6742b)

### Phase 4 Project - Data Science Nano Degree
### Moringa School

# Problem Statement 

# Project Objectives 

# Load the Data/Filtering for Chosen Zipcodes

# Data Preprocessing


```python
def get_datetimes(df):
    return pd.to_datetime(df.columns.values[1:], format='%Y-%m')
```

# Step 3: EDA and Visualization


```python
font = {'family' : 'normal',
        'weight' : 'bold',
        'size'   : 22}

matplotlib.rc('font', **font)

# NOTE: if you visualizations are too cluttered to read, try calling 'plt.gcf().autofmt_xdate()'!
```

# Step 4: Reshape from Wide to Long Format


```python
def melt_data(df):
    melted = pd.melt(df, id_vars=['RegionName', 'City', 'State', 'Metro', 'CountyName'], var_name='time')
    melted['time'] = pd.to_datetime(melted['time'], infer_datetime_format=True)
    melted = melted.dropna(subset=['value'])
    return melted.groupby('time').aggregate({'value':'mean'})
```

# Step 5: ARIMA Modeling

# Step 6: Interpreting Results
