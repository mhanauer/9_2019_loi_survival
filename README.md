---
title: "SurvivalPower"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
Try the smcure model.  Including the probabiltiy of not dying, which is relatively common for those who are at risk of suicide.  This is not a fatal disease.  
```{r}
install.packages("NPHMC")
library(NPHMC)
test = NPHMC(power = .8, alpha = .05/3, accrualtime = 1, followuptime = 1, p = .5, accrualdist = "uniform", hazardratio = .3, oddsratio = .1, pi0 = .9, survdist = "exp", lambda0 = .5)
test
round(test$nsize*1.25,0)
round(test$nsize*1.25,0)/3

```

