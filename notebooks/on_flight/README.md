# Flight updates package for ORCESTRA

### Purpose

This small package plots various satelite and forecast products that might be useful for the flight crew during a flight. It will plot the most recent data available, so can be updated as the flight proceeds.

### Acknowledgements

The script makes liberal use of the "goes.py" set of functions that I shamelessly stole from the weather_briefing_package written by Lukas, Tobi, Henning, and Divya (maybe others). A modified version of these functions are included with this package.


### Usage

0) Copy the file HALO-flightID.ipynb to another file, replacing "flightID" with the actual flight ID.

1) Set the flight takeoff time and forecast initialisation time in the second code block of the iphython notebook.

2) Download the flight plan from https://orcestra-campaign.org/operation/halo.html. Copy the first code cell (between the definition of "radius" to the defintion of "path" 

3) Running the iPython notebook will download various data and save figures to directories detailed below

4) To send a figure to the flight crew, open it in preview (Mac) and export it to jpeg with the quality set such that the size is smaller than 200 kB.

5) Run as needed during the flight. If an error occurs or the figure is blank, it is most likely that the satellite data could not be found. Try again. If the error persists, try changing the time you request to earlier using "timedelta" (see code block 2).


### Figures created

All figures plotted with the flight plan on top

- Forecast column water vapour for the time closest to now 	(parent/Figures/TCW_forecast)
- Latest GOES East visible satelite image 			(parent/Figures/VIS)
- Latest GOES East TPW 						(parent/Figures/VIS_and_TPW)
- Latest GOES East visible with Goes TPW estimate overlayed 	(parent/Figures/VIS_and_TPW)
- Latest GOES East visible with ASMRU estimate of TPW from last night (parent/Figures/VIS_and_TPW)
- Latest multisatellite MIMIC of TPW (parent/Figures/VIS_and_TPW)
- Latest GOES East Clean IR channel				(parent/Figures/IR)
- Latest GOES East estimate of Aerosol optical depth		(parent/Figures/AOD)
- Latest GOES East "water vapor" image 				(parent/Figures/WV)

The last figure takes about 10 minutes to download the data for. All other figures should be created in about 1-2 minutes.

### Directory structure


```
    | --- on_flight	
          |			
          | --- flight_HALO-flightID.ipnb	
          | --- goes.py 						
          | --- Figures			
    	        |
                | --- HALO-flightID			
                      | --- AOD			
                      | --- IR			
                      | --- TCWV_forecast	
                      | --- TPW			
                      | --- VIS			
                      | --- VIS_and_TPW		
                      | --- WV			

```

### Requirements


The script requires the orcestra package:

https://pypi.org/project/orcestra/


All of the rest are standard packages also installable by pip

- datetime		
- intake		
- os	 		
- goes2go			
- matplotlib		
- cartopy		
- xarray		
- pandas		
- numpy			
- seaborn		
- requests	
- rioxarray	
- urllib2
- PIL
- requests
- io



