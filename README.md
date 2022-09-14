# MechaCar Statistical Analysis

## Linear Regression to Predict MPG

Linear Regression was applied to the dataset using RStudio and the dplyr library to produce the following coefficients:

<img src="https://github.com/bradleywb426/MechaCar-Statistical-Analysis/blob/main/images/D1_lm.png">

-----

A summary of the linear regression was then calculated to produce the following coefficients, which will be reference throught this section:

<img src="https://github.com/bradleywb426/MechaCar-Statistical-Analysis/blob/main/images/D1_summary.png">

- Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?

  - A non-random amount of variance corresponds to a p-value < 0.5, and the only variables that acheive such a p-value is vehicle_length (with a p-value of 2.6E-12) and ground_clearance (with a p-vlaue of 5.21E-8).

- Is the slope of the linear model considered to be zero? Why or why not?

  - The slope of the line is non-zero because the p-value for the summary statistics is 5.35E-11, which is less than the alpha value of 0.05. This means there is non-random variance in the data.

- Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?

  - Using the R-Squared value of 0.7149, we know the mpg of MechaCar prototypes can be semi-strongly predicted using this model. If we were to use the Adjusted R-Squared value of 0.6825, our ability to predict the mpg of MechaCar prototypes diminishes slightly though it is still very close to predictions using the unadjusted value.

-----
  
## Summary Statistics on Suspension Coils

The summary statistics for the suspension coils from all lots are as follows:

<img src="https://github.com/bradleywb426/MechaCar-Statistical-Analysis/blob/main/images/D2_total.png">

-----

The summary statistics for the suspension coils separated by lots is as follows:

<img src="https://github.com/bradleywb426/MechaCar-Statistical-Analysis/blob/main/images/D2_lot.png">

- The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?

  - In total, the current manufacturing data shows the variance for all lots is 62.29356 PSI which is below the 100 PSI limit. However when looking at each lot individually, lot 3 is around 170.28612 PSI which exceeds the 100 PSI limit. For comparison, lot 1 has a variance of 0.97959 PSI and lot 2 has a variance of 7.46938 PSI, both of which are below the 100 PSI limit.
  
-----
  
## T-Tests on Suspension Coils

### T-Test of All Manufacturing Lots

A T-Test was performed to look if the manufacturing lots as a whole are statistically different from the population mean of 1500 PSI. The results were the following:

<img src="https://github.com/bradleywb426/MechaCar-Statistical-Analysis/blob/main/images/D3_tottest.png">

For the t-test above, the p-value of 0.06028 is greater than the alpha of 0.05 meaning that the manufacturing lots as a whole are not significantly different enough from the population.

-----

### T-Test of Each Manufacturing Lots

T-Tests were then performed on each manufacturing lot to look for the aforementioned statistical differences. The results are in the following order below; Lot 1 on the left, Lot 2 in the middle, and Lot 3 on the right:

<img src="https://github.com/bradleywb426/MechaCar-Statistical-Analysis/blob/main/images/D3_lot1.png" width="325"> <img src="https://github.com/bradleywb426/MechaCar-Statistical-Analysis/blob/main/images/D3_lot2.png" width="325"> <img src="https://github.com/bradleywb426/MechaCar-Statistical-Analysis/blob/main/images/D3_lot3.png" width="325">

- For Lot 1:

  - According to the t-test for lot 1, there is no statistical difference between lot 1 and the population because the p-value is not only greater than 0.05, but is exactly 1.
  
- For Lot 2:

  - According to the t-test for lot 2, this lot's p-value is 0.6072, which is greater than the alpha of 0.05, and therefore is not statistically different from the population.

- For Lot 3:

  - According to the t-test for lot 3, the p-value is 0.04168, which is both less than the alpha of 0.05 and means this lot is statistically different from the population.
  
-----

## Study Design: MechaCar vs Competition

Further studies can be performed to determine MechaCar's standing against its competition, including fuel efficiency in three main environments: highway, suburbs, and cities. For our purposes, these will be defined as areas of average speed of 60 mph, 30 mph, and 15 mph respectfully.

- Metrics to be tested:

  - Fuel efficiency at 60,30, and 15 mph: Dependent Variable
  
  - Vehicle Weight: Independent Variable
  
  - AWD: Independent Variable
  
  - MPG: Independent Variable
  
- Null and Alternative Hypothesis

  - Null Hypothesis: Fuel efficiency is the same on Highways, Suburbs, and Cities.
  
  - Alternative Hypothesis: Fuel efficiency is not the same on Highways, Suburbs, and Cities.
  
- Statistical Test to be Used

  - A multiple linear regression will be used given the presence of one continuous, dependent variable, and several continuous independent variables.

- Data Needed:

  - Beyond the data for Vehicle Weight, AWD, and MPG that is already obtained, we would need the corresponding fuel efficiency at the three listed speeds for the Mecha Cars, and then we would need to obtain the equivalent data from cars produced by competing companies.
