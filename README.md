# UNH_PS1PS2_SM_deployment_J25

This project contains the data collected by the University of New Hampshire (UNH) Coastal Processes Lab for a field experiment in January 2025. The data was collected at Wallis Sands Beach in Rye, NH. The main instruments utilized were the Pressure Sticks (PS), which are fully autonomous pressure-profiling instruments. There were two PS's deployed; one PS version 1 (PS1) and one PS version 2a (PS2 or PSv2a). The PS1 contains eight micro-controlled, time-synced TE Connectivity MS5837 Bar02 pressure and temperature sensors distributed along a 70 cm distance to measure pressure throughout the water column and into the sediment bed. The PS2 contains twelve micro-controlled, time-synced TE Connectivity MS5837 Bar02 pressure and temperature sensors distributed along a 85 cm distance to measure pressure throughout the water column and into the sediment bed. For more information about the Pressure Stick please see [Marry & Foster (2024)](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2023JC019891). For this experiment the PS's were deployed at the same alongshore position and were separated 1.96 meters in the cross-shore direction. To measure the location of the sediment-water interface, a SediMeter (SM) from [Lindorm Inc.](https://lindorm.com/) was also deployed. The SediMeter is a vertical array of optical backscatter detectors. The SediMeter was separated from the PS's by 0.88 meters in the alongshore direction. The SM was 2.10 meters from PS2 in the cross-shore direction and 4.06 meters from PS1 in the cross-shore direction. The PS1 is the most offshore instrument and the SediMeter is the most onshore instrument. Global Positioning System (GPS) surveys of the beach profile were also completed daily during the experiment, and the survey data is also included in this project. Data of the offshore wave conditions as measured by the [Jeffrey's Ledge waverider buoy (station 44098) from the National Data Buoy Center (NDBC)](https://www.ndbc.noaa.gov/station_page.php?station=44098) is given here as well.

This dataset is presented in the doctoral dissertation, "Resolving the Role of Wave-Induced Pressure Gradients on the Movement of Sediments in Nearshore Environments" [(M. Marry, University of New Hampshire, 2025)](https://www.proquest.com/docview/3254540596?pq-origsite=gscholar&fromopenview=true&sourcetype=Dissertations%20&%20Theses) and the manuscript, "Vertical Propagation of Wave-Induced Pressure Within Nearshore Sediment Beds: Field Observations and a Numerical Solution" (Marry & Foster, XXXX) which has been submitted to the Journal of Geophysical Research: Oceans in 2026. 

## Dataset files
A description of each data file is given below:

### Pressure Stick Data
1. UNH_PSYdata_Jan25_Raw_TCX.csv (Raw data files for the Pressure Sticks divided by tidal cycle for each Pressure Stick instrument and in compressed files)

    These files contain the raw data from the Pressure Sticks for the full deployment time (January 18th 2025 8:43:00 – January 20th 2025 10:37:00). The data is divided up by Pressure Stick (Pressure Stick 1 or Pressure Stick version 2a) and by tidal cycle. In the file name above, the ‘Y’ indicates the Pressure Stick and will be ‘1’ (Pressure Stick 1) or ‘2’ (Pressure Stick version 2a). The ‘X’ indicates the tidal cycle and will be either ‘0’, ‘1’, ‘2’, or ‘3’, where the increasing tidal cycle number indicates further along in time. Note due to large file sizes, the ‘.csv’ files are compressed. 

    - dt = datetime values, listed as ‘date/month/year hour:minute:second’
    - dn = datenum values
    - P_raw = the raw pressure recorded by the pressure sensors, in mbar. There should be 8 columns for Pressure Stick 1 and 12 columns for Pressure Stick version 2a, for the different number of sensors in each instrument. This pressure has not been corrected for changes in atmospheric pressure over the course of the experiment or for any general offsets in individual pressure sensors. 
    - T = temperature recorded by the pressure sensors, in degree Celsius. There should be 8 columns for Pressure Stick 1 and 12 columns for Pressure Stick version 2a, for the different number of sensors in each instrument. 
    - Pd = pressure head (in meters), or pressure converted to meters, for each pressure sensor. There should be 8 columns for Pressure Stick 1 and 12 columns for Pressure Stick version 2a, for the different number of sensors in each instrument. This pressure has been corrected for changes in atmospheric pressure over the course of the experiment and for general offsets in individual pressure sensors. 
    - z_0 = the initial pressure sensor elevations as recorded during installation (at the beginning of tidal cycle 0 (TC0)), in cm. There should be 8 columns for Pressure Stick 1 and 12 columns for Pressure Stick version 2a, for the different number of sensors in each instrument. Positive values indicate the pressure sensor is above the sediment-water interface (i.e, in the water/air) and negative values indicate the pressure sensor is below the sediment-water interface (in the sediment) at the initial installation. 

### SediMeter Data    
1. UNH_SediMeter_Jan25_raw.txt

    This file contains the raw data from the SediMeter for the full deployment time (January 18th 2025 14:09:00 – January 20th 2025 18:28:00). Note: FTU = Formazin Turbidity Units, signifies that the instrument has been calibrated using Formazin, regardless of measurement method.

    - DateTime = datetime values, in UTC 
    - Level (app.) = Bed level from the SediMeter software calculations (application/apparent). The bed level is relative to the SediMeter’s sensing area where the first optical backscatter detector in the vertical array is #1 and then the last detector is #36 and each sensor is spaced 1 cm apart. (cm)
    - Level (instr.) = Bed level from the SediMeter internal calculations (instrument). The bed level is relative to the SediMeter’s sensing area where the first optical backscatter detector in the vertical array is #1 and then the last detector is #36 and each sensor is spaced 1 cm apart. (cm)
    - Temp = temperature (deg C)
    - Batt = battery power (V)
    - Light = light level (lux)
    - ISO Turbidity = turbidity level relative to ISO (FNU, Formazin Nephelometric Units, as FTU but measured according to the ISO 7027 method of near infrared (NIR) light scattered at a 90 degree angle. The wavelength should be centered around 850 nm.)
    - EPA Turbidity = turbidity level relative to EPA (NTU, Nephelometric Turbidity Units, as FTU but measured according to the EPA method, i.e., white light scattered at a 90 degree angle.)
    - Fluoresc 90deg = Fluorescence level from 90 degrees (NFU, NFU = Nephelometric Fluorescence Units, this unit is used for measurements where UVA light (365 nm) is measured as 90 degree scattered visible (white) light and calibrated using Formazin. The UVA LED emits some visible light above 400 nm, and the photodetector is somewhat sensitive to wavelengths shorter than 400 nm, why the NFU value may be larger than zero even in the total absence of fluorescence. This value should be evaluated in conjunction with the NTU value (which is measured coaxially and using the same photodetector) and BFU (see below).)
    - Fluoresc 180deg = Fluorescence level from 180 degrees (BFU, Backscatter Fluorescence Units, this unit is used for measurements where UVA light (365 nm) is measured as 180º backscattered visible (white) light and calibrated using Formazin. The UVA LED emits some visible light above 400 nm, and the photodetector is somewhat sensitive to wavelengths shorter than 400 nm, why the BFU value may be larger than zero even in the total absence of fluorescence. This value is measured using the same photodetector as the NFU value (see above) but a different UV LED.)
    - NIR light = Background near infrared light (bits)
    - Tilt = tilt of the SediMeter. 0 degrees is when the instrument is perpendicular to the bed surface along its long axis and 90 degrees is when the instrument is parallel to the bed surface along its long axis (deg)
    - Vibration = Vibration of the SediMeter (mG)
    - User = User number, can be changed if you have multiple SediMeters (not applicable here)

### GPS Data
1. UNH_GPS_J25_20250118.txt

    This file contains data from a GPS survey taken on January 18th 2025 as the pre-deployment survey. Used to plot Figure 5 in (Marry & Foster, XXXX). 
    - GPST = time stamp of the survey sample 
    - latitude = latitude in degrees
    - longitude = longitude in degrees
    - height = elevation height, relative to WGS84/ellipsoidal in meters
    - Q = quality of the data point. Q = 1 is a 'good' data point, Q = 2 is an 'okay' data point, and Q > 2 are 'bad' data points. 
    - ns = Number of satellites
    
2. UNH_GPS_J25_20250119.txt

    This file contains data from a GPS survey taken on January 19th 2025 as the mid-deployment survey. Used to plot Figure 5 in (Marry & Foster, XXXX). 
    - GPST = time stamp of the survey sample 
    - latitude = latitude in degrees
    - longitude = longitude in degrees
    - height = elevation height, relative to WGS84/ellipsoidal in meters
    - Q = quality of the data point. Q = 1 is a 'good' data point, Q = 2 is an 'okay' data point, and Q > 2 are 'bad' data points. 
    - ns = Number of satellites

3. UNH_GPS_J25_20250120.txt

    This file contains data from a GPS survey taken on January 20th 2025 as the post-deployment survey. Used to plot Figure 5 in (Marry & Foster, XXXX). 
    - GPST = time stamp of the survey sample 
    - latitude = latitude in degrees
    - longitude = longitude in degrees
    - height = elevation height, relative to WGS84/ellipsoidal in meters
    - Q = quality of the data point. Q = 1 is a 'good' data point, Q = 2 is an 'okay' data point, and Q > 2 are 'bad' data points. 
    - ns = Number of satellites

### Waverider Buoy (NDBC station 44098) Data
1. NDBC_44098_JeffreysLedgeBuoy_J25.txt

    This file contains offshore wave data from [Jeffrey's Ledge waverider buoy (station 44098) from the National Data Buoy Center (NDBC)](https://www.ndbc.noaa.gov/station_page.php?station=44098) throughout the full deployment time (January 18th, 2025 05:26:00 - January 20th, 2025 21:56:00). Used in (Marry & Foster, XXXX). Please see [Description of Measurements](https://www.ndbc.noaa.gov/measdes.shtml) for a discussion of each of the variables in this file.
