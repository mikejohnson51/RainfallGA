`Runoff-Infiltration-Model`
================
Model to test variable rainfall rates on the coupled infiltration runoff patterns on a hill slope. Based on 2017 paper by Johnson and Loaiciga which can be found in the 'publications' directory and an paper in prepration for the Journal of Hydrology.

## Input Requirements
The model requires user-input  regarding:
 1) **Hill shape**: Vertical and horizontal length and depth
 2) **Soil**: Roughness, conductivity, soil water tension, porosity, and volumetric content
 3) **Rainfall**: For this the user has three option:
    1. Constant: Rainfall rate derived from total depth, time and time step
    2. Triangular: Rainfall rate derived from total depth, time and time step
    3. Input file: Given as a .csv or .xlsx describing rainfall depth at a given time increment
    4. A distance step and time step for the model to run on
    
## Installation

To install the  package, you must install from GitHub using the `devtools` packages:

```r
library(devtools)
install_github("mikejohnson51/rainfall_infiltration_hillslope")
```

## Model Workflow

1) Parameterize your scenario with the **param()** function. If this is your first time creating a scenario file fill out all pertainent information and click 'submit'. If errors are encountered reference the functions help file using ?param. *To facilitate sesitivity testing, or multiple scenarios, old scenarios can be modified by entering the files name in the 'Use previos run' heading, clicking 'Use Old Run', modifing as you wish, and clicking resubmitting.*

```r
scene1 = param()
```
     
![param_example](https://github.com/mikejohnson51/Rainfall_Infiltration_hillslope/blob/master/imgs/param_ex.png)

2) Execute the model using your scenario file as input using the **exe()** function

```r
mod_1 = exe(scene1)
```

![model_run](https://github.com/mikejohnson51/Rainfall_Infiltration_hillslope/blob/master/imgs/model_run.png)


3) Process your results for defined time slices with the option of genrating graphs and an excel workbook using the **process()** function

```
output = process(mod_1, hrs = c(5,10,15,20,24), plots= TRUE, excel = TRUE)
```


