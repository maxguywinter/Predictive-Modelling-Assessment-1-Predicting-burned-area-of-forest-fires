# Predictive-Modelling-Assessment-1-Predicting-burned-area-of-forest-fires
Using linear regression model for predicting burned area of forest fires. (Grade 70%).

# Section 1.0 Data Summary

Numerical summary

Figure 1

<img width="483" alt="image" src="https://user-images.githubusercontent.com/97530878/153612157-9fae6047-36eb-4af3-8103-bae241b84545.png">

Graphical summary 

Figure 2a

<img width="586" alt="image" src="https://user-images.githubusercontent.com/97530878/153612244-a02c3fe0-928b-477f-8181-7c93e973dc86.png">

Figure 2b

<img width="517" alt="image" src="https://user-images.githubusercontent.com/97530878/153612326-e518c50c-1dee-4bb3-970a-3f80c1d217f8.png">

Being categorical, values month and day variables were removed from the matrix. Figures 2a and 2b above check for collinearity and multicollinearity. Both figures exhibit that the explanatory variables are not highly correlated or have a strong linear relationship with one another. None of the absolute values of the correlation is greater than 0.9. Therefore, multicollinearity is not an issue in this model. 

# Section 2.0 Model Selection

Model 1

<img width="201" alt="image" src="https://user-images.githubusercontent.com/97530878/153612415-921b2567-9ebd-448e-887d-504b9bbf2508.png">

Model 1 has a low R-Squared value of 0.04679, suggesting the model is not very accurate. Moreover, most variables appear insignificant, and the model has a high p-value of 0.6895. Thus, having a low R-squared and p-value means that model 1 does not explain much of variation of the data, and it is not significant. 

Figure 3. 

<img width="498" alt="image" src="https://user-images.githubusercontent.com/97530878/153612473-f9908642-263c-4c43-a7e3-64102cbf0632.png">

Figure 3 show clear departures from the assumptions of the linear regression model. Model 1 residuals are not equally spread around the y=0 line and show a pattern. The range of the residuals at each fitted value appears not to be roughly the same, so we can conclude there is evidence of heteroskedasticity. Thus, model 2 uses logarithms of all variables to address the heteroskedasticity.

Model 2 

<img width="175" alt="image" src="https://user-images.githubusercontent.com/97530878/153612544-74457cd1-22cd-457a-9d64-a7ede46b0faa.png">

Implementing logarithms for model 2 improved the R-Squared value to 0.06789, suggesting the model is more accurate than model 1. Additionally, most variables appear to be significant, and the model has a lower p-value of 0.1927. The summary indicates that month and day are not statistically variables and thus removed for model 3.

Model 3 

<img width="180" alt="image" src="https://user-images.githubusercontent.com/97530878/153612605-2baa2603-f769-4ea4-b409-1cb56ba32fca.png">

Model 3’s R-Squared value decreased to 0.02227, suggesting the model is less accurate than models 1 and 2. Moreover, model 2 is less significant than model 2 as it has a higher p-value of 0.2587. The variable log (rain+1) has the largest p-value, and so this variable is removed, and the model is re-fitted. 

VIF test on all models 

<img width="452" alt="image" src="https://user-images.githubusercontent.com/97530878/153612655-7d21f523-0b54-4682-923b-18eb6f80cfb4.png">

To double-check for collinear variables, a Variance Inflation Factors test was used for model 3. None of the variables needs to be removed as none of the VIFs are above 10.

Model 4 

<img width="203" alt="image" src="https://user-images.githubusercontent.com/97530878/153612710-c859cffa-9fa3-46f1-93ae-363ae510d458.png">

Model 4’s multiple R-Squared value is the same as model 3, but its adjusted R-squared is slightly higher, yet this difference is minimal (0.002223). Additionally, model 4 is more significant than model 3 as it has a lower p-value of 0.183. The variable log (DC) has the largest p-value, and so this variable is removed, and the model is re-fitted.

Model 5 

<img width="207" alt="image" src="https://user-images.githubusercontent.com/97530878/153612786-d3bacb4f-40df-481c-8804-83f9a6b03e35.png">

Model 5’s R-Squared value decreased to 0.02153, suggesting the model is less accurate. However, model 5 is more significant than model 4 as it has a lower p-value of 0.1345. The variable log (FFMC) has the largest p-value, and so this variable is removed, and the model is re-fitted.

Model 6

<img width="217" alt="image" src="https://user-images.githubusercontent.com/97530878/153612837-c566ec9e-32a3-4647-b14f-004dba214ea0.png">

Model 6’s R-Squared value decreased to 0.0201, suggesting the model is marginally less accurate than model 5. Though, model 6 is more significant than model 5 as it has a lower p-value of 0.1042. The variable log (ISI+1) has the largest p-value, and so this variable is removed, and the model is re-fitted.

Model 7 

<img width="213" alt="image" src="https://user-images.githubusercontent.com/97530878/153612943-920bcf49-ccd9-49cb-850f-a4769125f17c.png">

Model 7’s R-Squared value decreased to 0.01926, suggesting the model is less accurate than model 6. Nevertheless, model 7 is more significant than model 6 as it has a lower p-value of 0.06757. The variable log (wind) has the largest p-value, and so this variable is removed, and the model is re-fitted.

AIC test

<img width="255" alt="image" src="https://user-images.githubusercontent.com/97530878/153612964-4e7d2704-ab95-4777-a43d-806c7a8de017.png">

An AIC test was utilised to find the best model by taking or adding variables. The first AIC was the initial model akin to model 2 with an AIC of 341.77 and the best model with the lowest AIC of 321.67 and matched model 7 without the variable log (wind). Therefore, as model 7 and the AIC test suggested, the variable log (wind) will be removed for model 8.  

Model 8 

<img width="261" alt="image" src="https://user-images.githubusercontent.com/97530878/153612986-aa00b5b9-1a40-449c-8f09-f973f034e4e1.png">

Model 8’s R-Squared value decreased to 0.0175, suggesting the least accurate model. However, model 8 is the most significant as it has the lowest p-value of 0.04695. Additionally, all the variables are statistically significant. Both DMC and RH variables show fairly strong evidence, while and temperature shows some evidence that the area burned depends on them. 

ANOVA test 

Model 8 is the most significant. However, it has the lowest R-squared value and thus potentially the least accurate model. Thus, an ANOVA test compares model 8 with model 2 with the highest R-Squared value. The ANOVA results show that the simplest model (model 8) produces more accurate fitted values than the more complex model (model 2) as the p-value was 0.03987. Model 8 is favoured as the p-value was not sufficiently low as it was greater than 0.05.

# Section 3.0 Model Validation

Residuals graphs 

<img width="246" alt="image" src="https://user-images.githubusercontent.com/97530878/153613084-993d06fb-228c-4add-a5a1-224dd11f2cc7.png">

Figure 4

<img width="435" alt="image" src="https://user-images.githubusercontent.com/97530878/153613108-12c196ab-6deb-4b6f-a204-33d9f3157892.png">

Figure 4 no longer shows a clear departure from the assumptions of the linear regression model. Model 8 residuals are equally spread around the y=0 line and show a pattern. The range of the residuals at each fitted value appears to be roughly the same, so we can conclude there is no evidence of heteroskedasticity. Thus, the use of logarithms of all variables addressed the issue of heteroskedasticity. For the Q-Q plot the observations lie well along the 45-degree line, so we may assume that normality holds here. Overall models 8 residuals are better fitting than models 1s.

The R-Squared for model 8 was 0.0175 and was the lowest of all the models. Model 8's R-Squared was near 0, thus suggesting that the regression model did not explain much of the variability in the outcome. Nevertheless, R-Squared will always increase when there are more variables, even if those variables are only weakly associated with the outcome. Moreover, model 8 was the most significant as it has the lowest p-value of 0.04695. Consequently, having a low R-Squared and p-value means that model 8 doesn't explain much of variation of the data, but it is significant.

# Section 4.0 Model Prediction

RMSE 

The root-mean-square error (RMSE) of each model can be calculated to compare the fits of the modes, with the model with the lowest RMSE being the best-fitted model.  Model 8 has the lowest RMSE of 1.290659, compared to model 2’s RMSE of 1.327091. Therefore, model 8 can be considered the better fitting model. 

Correlation tests of predicted vs actual

Correlation tests were conducted to illustrate the best fitting model using the test rather than the training subset. Scores closer to 1 are betting fitting. Model 8 had a correlation score of 0.02, whereas model 2 had a correlation score of 0.07, which means that model 8 would be considered the best fitting model. However, the scores are very close, and many not show significance.  

# Section 5.0 R Script

>library(corrplot) # for correlation matrix graph visualisation # Install packages 
>library(ggplot2) # for graph visualisations 
>library(car) # for VIF test
>library(caTools)
>library(dplyr) # to use the select function 
>library(MASS) # for AIC test

>setwd("~/Desktop/predicitve model assessment 1") # sets the file with the fire data as the working dictionary to important the dataset 
>fire_data <- read.csv("forestfires.csv", header = TRUE) # imports the data set. The header=True command tells RStudio to use the first row of the data file as the names of each variable/column. 
>attach(fire_data) # attaches the data to your environment so that you can directly refer to the variable by name
>View(fire_data) # shows the fire data in a table 
>names(fire_data) # shows the name of variables in the dataset
>head(fire_data)

>summary (fire_data) # provides more information from fitting the model such as Residuals (Min      1Q  Median      3Q     Max), Coefficients (Estimate Std. Error t value Pr(>|t|)) , Signif. codes: (0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1), Residual standard error, Multiple R-squared, Adjusted R-squared, F-statistic, and the  p-value

>datacorrelation <- subset(fire_data [,5:13]) # subset data to remove x,y, month and day as they are factors 
>nums <- unlist(lapply(datacorrelation, is.numeric)) # used to create correlation plot from numeric values in fire data
>firecorr <- cor(datacorrelation[, nums])
>corrplot(firecorr, type = "upper", method = "number") # correlation matrix graph visualization 
>chart.Correlation(firecorr, histogram = TRUE, pch= 19) # scatter plot and hist graph visualization 
>pairs(datacorrelation)# graphical matrix visualization 

>fire_data$logarea <- log(fire_data$area+1)# transforming the data 
>fire_data$month <- factor(fire_data$month) # factor returns the original object of a class with the requested column specified as a factor rather than numeric.
>fire_data$day <- factor(fire_data$day)
>fire_data2 <- fire_data %>% select(area, month, day, FFMC, DMC, DC, ISI, temp, RH, wind, rain) # Removes X and Y variables as they are factors and not relevant to the model as don’t impact the burned area. 
>split = sample.split(fire_data2$area, SplitRatio = 0.75) # Sets up train and test populations for model validation and predication tests 
>train = subset(fire_data2, split == TRUE)
>test = subset(fire_data2, split == FALSE)

>model1 <- lm(area~month + day+ FFMC + DMC + DC + ISI + temp + RH + wind + rain, data = train) # Creating initial model (all variables)
>summary(model1)
>par(mfrow = c(2,2)) # partitions your graphical display if you want to produce multiple graphs on a single plot.
>plot(model1) # plots residual graphs for model 1 

>model2 <- lm(log(area+1)~month + day+ log(FFMC) + log(DMC) + log(DC) + log(ISI+1) + log(temp) + log(RH) + log(wind) + log(rain+1), data = train) # Model 2 (all variables and log)
>summary(model2)

>model3 <- lm(log(area+1)~ log(FFMC) + log(DMC) + log(DC) + log(ISI+1) + log(temp) + log(RH) + log(wind) + log(rain+1), data = train) # Model 3 (removed month and day)
>summary(model3)

>vif(model3) #vif test for collinear variables to remove (all fine as below all variables below 10) 

>model4 <- lm(log(area+1)~ log(FFMC) + log(DMC) + log(DC) + log(ISI+1) + log(temp) + log(RH) + log(wind), data = train) # Model 4 (removed rain from model 3)
>summary(model4)

>model5 <- lm(log(area+1)~ log(FFMC) + log(DMC) + log(ISI+1) + log(temp) + log(RH) + log(wind), data = train) # Model 5 (removed DC from model 4)
>summary(model5)

>model6 <- lm(log(area+1)~ log(DMC) + log(ISI+1) + log(temp) + log(RH) + log(wind), data = train) # Model 6 (reomved FFMC from model 5)
>summary(model6)

>model7 <- lm(log(area+1)~ log(DMC) + log(temp) + log(RH) + log(wind), data = train) # Model 7 (removed ISI from model 6)
>summary(model7)

>starting.model <- lm(log(area+1) ~ month + day+ log(FFMC) + log(DMC) + log(DC) + log(ISI+1) + log(temp) + log(RH) + log(wind) + log(rain+1), data = train) # AIC >best model (shows best model is DMC + temp + RH)
>simple.model <- lm(log(area+1)~ 1, data = train)
>stepAIC(starting.model, scope = list(upper = starting.model, lower = simple.model), direction = "both")

>model8 <- lm(log(area+1)~ log(DMC) + log(temp) + log(RH), data = train) # Model 8 (removed wind from model 7 and AIC test/ lowest AIC of all models)
>summary(model8)

>anova(model8, model2) #ANOVA test (model 8 vs model 2. Model 8 is more accurate fitting model as p-value is not sufficiently low (usually greater than 0.05), thus favour the simpler model). Model 8 will therefore be used for the prediction 

>coef(model8) # residual plot for model 8 
>par(mfrow = c(2,2))
>plot(model8)

>test$area
>predict(model8, test) # uses test rather than train subset of data 
>predict (model8, test[1:5,]) 
>RMSE <- function(predicted, true) mean ((predicted-true)^2)^.5
>RMSE (predict(model8, test), test$area)
>predict (model2, test[1:5,])
>RMSE (predict(model2, test), test$area)

>cor(test[,"area"],predict(model8, test)) # correlation of prediction vs test data 
>cor(test[,"area"],predict(model2, test))



























