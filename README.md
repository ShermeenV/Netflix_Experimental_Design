# Netflix Experimental Design

## Phase 1 - Factor Screening

The objective of this phase is to determine whether all 3 factors i.e Tile Size, Preview Size and Preview Length are important in reducing the *Average Browsing Time* of the user. If there is any factor not significant to the response variable it can be removed from further analysis. 

After running a linear regression model, we observed that Tile Size did not have an effect on our response variable which can be seen in the factor screening plots below. Therefore, we can omit that factor and only use Preview Size and Length to reach the optimal value.

<img src="Plots/FactorScreeningPlots.png">


## Phase 2 - Gradient Descent

This phase determines if we are currently in the presence of quadratic curvature. If not, we would have to move towards that curvature in order to get closer to our optimum. For this we would start at our centre and take steps until we find the turning point. This would be the point at which our response variable starts to increase again indicating we were at the optimum point and have moved away.

In this case, the center point was at a Preview Length of 60 and we took increments of 10. It is important to be careful of the step size as very small steps would require more data and hence more resources but large sizes might cause us to move away from the optimum too quick

<img src="Plots/Steps - Gradient Descent.png" width = 500> 

The image below shows us the plot of steps taken and we can see that the optimum lies somewhere between steps 2 and 4

<img src="Plots/Steps Plot.png" width = 500> 

Taking the new high and low points we generate data and check if we are now in the quadratic curvature through linear regression. Our results give a pvalue less than the 5% significance level therefore we reject the null hypothesis and state that we are now in the presence of the quadratic curvature. The next step would be to fit a second order model and use Response Surface Methodology to find the optimum point
