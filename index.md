---
title       : MPG Predictor Using Shiny 
subtitle    : 
author      : Neeraj Agrawal
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

- To predict MPG (Miles per gallon) of a car is not a easy task. To reduce the effort, here comes a MPG predictor app. 

- A shiny APP is made to predict the MPG of car, based on few paramter(no of cylinder, horsepower, weight, transmission), entered by user.

- For training the model, "mtcar" data has been used, which is already avaialbe in R.

---

## Regression Model

Linera Regression Model is used to predict the MPG.


```r
RegModel <- lm(mpg ~ factor(cyl) + disp + hp + wt +factor(am), data=mtcars)
RegModel$coefficients
```

```
##  (Intercept) factor(cyl)6 factor(cyl)8         disp           hp 
## 33.864276061 -3.136066556 -2.717781289  0.004087893 -0.032480178 
##           wt  factor(am)1 
## -2.738694608  1.806099494
```

---


## Regression Model Accuracy


```r
Predicted <- predict(RegModel)
plot(Predicted, mtcars$mpg, xlab = "Predicted", ylab = "Actual", col= "green", pch = 3)
```

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2-1.png) 

---

## Conclusion

In conclusion, the application uses the values to accurately compute the expected mpg required of that configuration. Accuracy of model is shown in graph over training data only.

With this user can predict MPG of its car, with certain certainity.
That will help user in maintenance of his car.




