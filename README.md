# Simulation of a vertical bifacial PV system compared to measured values

This repository includes the important scripts creating in Jupyter notebook while working with the master's thesis "Simulation of a vertical bifacial PV system compared to measured values". This master's thesis represent the completion of the master’s degree in Environmental Physics and Renewable Energy at the Norwegian University of Life Sciences (NMBU), and has been written in collaboration with the Institute
for Energy Technology (IFE).

© Amalie Elisabeth Robsahm

# Repository overview
All the scripts in this repository are site-spesific for the test site located at IFE studied in this master's thesis, but a few generalizations have been done. The presented scripts have been modified to retrieve all the results presented in the master's thesis.


### Weather file
This file incorporates the script developed to create the weather files with the columns of a TMY file from measured data for GHI, DHI, DNI, and albedo. The files are created in the UTC timezone and are implemented in bifacial\_radiance by using right-labeled data, i.e. with a shift of -30 minutes, iand instantaneous values based on a 5-minute interval to represent the data for an hour. 

### Uncertainty analysis
This file incorporates the script to estimate the measurement uncertainty in the data measured by the pyranometers and pyrheliometer on the test site. These functions were developed as a part of the work in a master's thesis written in the spring of 2021 and can be found on the GitHub repository [Performance-modeling-of-Bifacial-PV-Power-Plants-in-a-Nordic-Climate](https://github.com/Dina-CM/Performance-modeling-of-Bifacial-PV-Power-Plants-in-a-Nordic-Climate). These functions are using parameters defined in the calibration certificates and the data sheet of the pyranometer and pyrheliometer together with JCGM 100:2008 GUM Evaluation of measurement data.

### 3D model and simulating the irradiance
This file incorporates both the 3D model developed and how the irradiance was simulated using the 3D model. After the sky was generated, the 3D model was created before the sensor positions were defined to simulate the irradiance for the front and the rear side of the reference cells. The script shows an example of one of the time periods simulated, modified versions of the script were used to simulate other time periods. 

The sky was generated with two approaches from the imported weather data, one where the sky represents one timestamp and the other one a cumulative sky to represent the sky for a longer period of time. The example in the script illustrates the case where the sky represents one timestamp to simulate the irradiance for one day with an hourly interval.   

The 3D model is set up with objects corresponding to the dimensions, angles, and positions of the objects on the test site. Still, the model was simplified to only include the PV system and the rails along the roof. Hence, surrounding objects were neglected.

### Angle of incidence (AOI)
This file incorporates angle of incidence (AOI) calculations using specific parameters from the test site to retrieve the irradiance where losses due to AOI have been taken into account.

### Power simulation
This file incorporates the script created to simulate the DC and AC power on the test site using the average irradiance and temperature. This was done for both simulated and measured irradiance. Modifications of this script were used to retrieve results for all time periods and for the case of the cumulative sky. For the case of cumulative sky, the DC energy was simulated but the AC energy was omitted.

### Materials.txt
This file incorporates all the RADIANCE default materials included in bifacial\_radiance software. The materials used to create the 3D model in this thesis were \textit{stock glass}, \textit{Metal\_Grey}, and \textit{black}.

### README.md
This file incorporates a short description of the files included in the repository as given above.

# Prerequisites
Using the scripts in this repository requires installation of the software bifacial_radiance, RADIANCE and python including Jupyter notebook and pvlib.

