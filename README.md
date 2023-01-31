# This is a Monte Carlo version of the CARLIOS model, as used in the paper Krause et al. (in revision with Nature Geoscience)

This model is an adaptation of the CARMER model by Dal Corso et al. (2020), which is a box model of the Earth system, including a crust, 3 ocean boxes, and an atmosphere.
In CARLIOS the Hg cycle is removed, and Li, Os and Si cycles are included, as well as a few other changes. 

CARLIOS was created to investigate the Middle Eocene Climatic Optimum event (~40.5 - 40 Ma). There are a number of files included in this package:

CARLIOS.m  <- This file contains all of the forcings and equations

CARLIOS_frontend.m  <- This file contains the ODE solver, start states for the differential equations, various model constants, Monte Carlo information, and post model run processing of data from a 'working' state to an 'intermediate' state ready for statistical analysis in the montecarlo file

CARLIOS_montecarlo.m  <- The model must be run from this file - it contains information for the parallel loop, which enables MATLAB to utilise all of your computer cores for model runs. It contains the code for running statistics on the model runs to produce, for example, a mean value for all the runs combined. This file also contains code for plotting the 'Scenario' figures in the paper. Change n if you want to increase/decrease the number of model runs, n = 1 will perform 1 model run, n = 2 will do 2, etc.

site_data  <- This contains data from sites 1263 and U1333 for plotting

proxy_data  <- This contains some of the proxy data from other sources used for comparison in a few of the figures



!!!! To run this model you need to have the parallel computing toolbox from MATLAB installed !!!!



The three script files have pretty extensive comments about what each line of code is/does, but any questions can be sent to a.krause@ucl.ac.uk (until Dec 2023).

Also included in this bundle is an Excel file which contains Tables S1-6 from the paper, which includes the tiepoints for the new age model, geochemical data from this study, and the proxy data (CO2, temperature, pH) from Henehan et al. (2020) updated to the 2020 GTS.
