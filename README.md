# Engie Wind Turbine Power Prediction

## Short description
Predict wind power production from wind turbine operational data. 

Video of the challenge's presentation at Collège de France is available at: https://www.college-de-france.fr/site/stephane-mallat/Challenge-2017-2018-Regression-de-la-production-d-energie-eolienne-par-Engie.htm

## Challenge context
Wind power has seen strong development for some years now both in France and abroad. Renewable, mature and competitive, this energy of the future has a major role to play in responding to the present and future climate challenges.

The development of onshore wind power is one of ENGIE priorities, which is now the largest wind power producer in France and Belgium and an international leader with 4,553 MW installed throughout the world.

In this context, the Group wants to optimize further the power produced by its wind turbines, thus to detect abnormal deviations between expected production and actual production. 
This challenge is open to non-ENGIE people only. 

## Challenge goals
The goal of this challenge is then to predict the active power produced by four wind turbines from several operational parameters; these parameters come from measurement sensors installed inside these turbines. While wind speed anemometers are customarily installed on the nacelle of each turbine, the related measurements are often considered to be of poor reliability for monitoring the operational performance; for that reason, the challenge focuses on predicting active power without considering wind speed data in the list of explanatory variables. 

## Data description
The file 'input_training.csv' contains the input variables or X variables. The first line of this file is the header and columns are separated by semicolons. Then each line is defined by a unique 'ID' and is related to a given wind turbine (defined by 'MAC_CODE') and a given 10 minute timestamp (defined by 'Date_time').

The first three columns correspond respectively to:
- the 'ID': identification number of the line, it is linked to the IDs provided in the file 'input_testing.csv';
- the 'MAC_CODE' or 'machine code': the identifier of each wind turbine, one of 'WT1', 'WT2', 'WT3', 'WT4';
- the 'Date_time': an integer for each 10 minutes timestamp.

The next columns correspond to:
- Temperatures of components inside the turbines in degrees Celsius: Gearbox_bearing_1_temperature, Gearbox_bearing_2_temperature, Gearbox_inlet_temperature, Gearbox_oil_sump_temperature, Generator_bearing_1_temperature, Generator_bearing_2_temperature, Generator_stator_temperature, Hub_temperature, Nacelle_temperature, Rotor_bearing_temperature
- Electrical information: Grid_frequency, Grid_voltage
- Rotational speed measurements: Generator_converter_speed, Generator_speed, Rotor_speed
- Orientations: Absolute_wind_direction, Absolute_wind_direction_c, Nacelle_angle, Nacelle_angle_c, Pitch_angle
- Meteorogical measurements: Outdoor_temperature

Most (not all, though) of the X variables mentioned above decline into four columns:
- one column for the average value over 10 minutes;
- one column for the maximum value over 10 minutes ('_max' suffix in the column name);
- one column for the minimum value over 10 minutes ('_min' suffix);
- one column for the standard deviation over 10 minutes ('_std' suffix).

The file 'output_training.csv' contains the target variable or Y variable for each 'ID', where the target is the active power of each of the four wind turbines at each 10 minutes timestamp. The first line of this file is the header and columns are separated by semicolons. The columns correspond respectively to the identification number of the line and the value of the actual active power for this specific line as shown in the following sample:

* ID;TARGET
* 1;0.1341
* 2;0.0461
* 3;0.1443
* 4;0.1301

Using the file 'input_testing.csv', the participants must provide a file 'output_testing.csv' in the same format as the file 'output_training.csv' (associating with each ID number, the predicted active power).

The metric used in this challenge to designate the winning participant is the mean absolute error (MAE), see https://en.wikipedia.org/wiki/Mean_absolute_error.

## Target Scores
Highest = 15.0735
Lowest =  101.683

## Github

Create a branch and open a pull request.