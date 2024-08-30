# TMY3 Solar Aggregations

## Description

This project executes an ETL procedure on TMY3 solar data.

### Data
__Source:__ [tmy3-solar](https://www.kaggle.com/datasets/us-doe/tmy3-solar/code)

__File:__ `tmy3.csv`  
* __Description:__ One Year of typical Hourly Solar & Weather Data for +1000 US Locations
* __Data points:__ 
    * Date (MM/DD/YYYY)
    * Time (HH:MM)
    * GHI (W/m^2)
    * DNI (W/m^2)
    * station_number

__File:__ `TMY3_StationsMeta.csv`  
* __Description:__ Metadata about weather stations
* __Data points:__ 
    * USAF
    * Site Name
    * Latitude
    * Longitude

__File:__ `43256.pdf`
* __Description:__ User Guide for TMY3 data


### Transformations
Hourly GHI and DNI values in `tmy3.csv` are aggregated into weekly mean values for each station.

### Outputs
This code outputs a .json file at a given filepath.

e.g.:

``` json
[   
    {  
        "id": 690150,  
        "site_name": "TWENTYNINE PALMS",  
        "coordinates": [  
            34.3,  
            -116.167  
        ],  
        "data": [  
            {  
                "timestamp": 839116800000,  
                "ghi": 337.5052631578947,  
                "dni": 433.2526315789474  
                ...
```

## Set up

### ⚠️ Kaggle config file
Downloading datasets from Kaggle requires an API access token.  You can download this token through your Kaggle account settings.

Save in "C:/user/<your_name>/.kaggle/kaggle.json"

### Running the script

* Run the ETL from the Jupyter notebook `etl_solar.ipynb`.
* Most code editors should be able to read notebooks.
* Use VS Code with the Jupyter extension if in doubt.

### Dependencies

Only standard packages are used in this ETL.  There are instructions to install dependencies if required under [Installing](#installing).

* Python 3
    * datetime
    * json

* pandas
* ipykernel
* opendatasets

* Conda (optional)

### Installing

The package dependencies are available in `environment.yml`.  Run the following command in the terminal to create an environment with the required packages if necessary.  Note you will need a Conda install.

```
conda env create -f environment.yml
```

This will create a Conda environment called 'solar' with the required packages installed.  This environment should be available as a kernel to run the Jupyter notebook (you may need to restart your script editor after installing).

## Help

Contact: alice.matthews@live.com.au

## Authors

Alice Matthews  
[@alissmat](https://github.com/alissmat)

