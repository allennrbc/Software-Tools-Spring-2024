# Haylee's Analysis for Check Point 1
## Recommendations for furthering analysis already completed
Using the data Dan analyzed on his RPubs page (https://rpubs.com/DanielCusick/1159736), can we compare those working PT for economic reasons vs those working PT for non-econimic reasons? Do we see similar, opposing, or random trends? Did specific events/policies occur during or right before these trends?

This idea comes from the descriptions of PT done for economic reasons vs non-economic reason found on the BLS site (https://www.bls.gov/cps/definitions.htm#pter)
Economic Reasons (also referred to as involuntary part-time workers): This category includes people who gave an economic reason when asked why they worked 1 to 34 hours during the reference week. Their usual hours of work may be either full or part time. Economic reasons include the following:
1. slack work
2. unfavorable business conditions
3. inability to find full-time work
4. seasonal declines in demand
People who usually work part time and were at work part time during the reference week must indicate that they want and are available for full-time work to be classified as part time for economic reasons.

Non-economic Reasons: This category includes only people who usually work part time. When asked why they worked 1 to 34 hours during the survey reference week, they gave a noneconomic reason such as the following:
1. illness or other health or medical limitations
2. childcare problems
3. family or personal obligations
4. in school or training
5. retirement or Social Security limits on earnings
6. having a job where full-time work is less than 35 hours
This category also includes a relatively small number of people who give an economic reason for working 1 to 34 hours but said they do not want to work full time or are unavailable for full-time work.

## Wages
How much are part-time workers making compared to full-time workers?


## Comparing Wages to Purchasing Power
Compare wages (https://fred.stlouisfed.org/series/CES4200000003) to CPI (https://fred.stlouisfed.org/series/CPIAUCSL) and calculate to get the real wage 
Real Wage in a year = (Nominal Wage in a Year/CPI in a Year)x100
Wage Purchasing Power in a chosen year = (Nominal wage in the base year/ CPI in the base year)(CPI in the selected year)

Doing this will tell us if wages are the problem: have wages kept up pace in terms of purchasing power?

---
title: "Project Checkpoint 1"
author: "Haylee Allen"
date: "4/7/2024"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## R Markdown

Comparing wages in retail to their real wage value and purchasing poser

```{r data setup}
rm(list = ls()) # Clear environment
gc()            # Clear memory
cat("/f")       # Clear console

#load libraries
library(fredr)
library(tidyverse)
library(ggplot2)
library(dplyr)

#Get Data
setwd("C:/Users/hrall/OneDrive/Documents/School/Spring 2024/Software Tools for Data Analysis/Final/Data") #set directory
RealWageData<-read.csv("RealWage.csv", header=TRUE)

#check for null values
sum(is.na(RealWageData))

#Data clean up
#create data to omit nulls
RealWageDataOmit<-na.omit(RealWageData)
#Change the header names
colnames(RealWageDataOmit)[2]<- "CPI"
colnames(RealWageDataOmit)[3]<- "NominalWage"

#View data
summary(RealWageDataOmit)
```


Calculating the real wage and purchasing power for each wage data point provided by FRED

```{r add new columns}
#Calculate purchasing power
#since the first row of data is 3/1/2006, this will be our base
#Determine the values for the base
NomWageBase<- RealWageDataOmit[1,3]
CPIBase<- RealWageDataOmit[1,2]

#Add in columns for purchasing power and real Wage
WageData<-RealWageDataOmit %>%
  mutate(
    PP = (NomWageBase/CPIBase)*CPI,
    RealWage = (NominalWage/CPI)*100)

WageData
summary(WageData)
```

Plot the data

```{r aplot}
#Plot real wage and purchasing power
ggplot(WageData, aes(x=DATE, y=RealWage, group = 1))+
  geom_line()+
  labs(title = "Real Wage", x = "Date", y = "Real Wage")
```

Note: I need to scale the x axis and am working on getting the plots to show in github

Similarly, when determining if trends in PT are voluntary or forced, we can look at other quality of life indicators

## Health Insurance Data
Data provided by https://www.kff.org/other/state-indicator/total-population
One of the main benefits of working full time is acccess to employer-paid benefits. The following plots show trends in how and if people held health insurance. This data can be compared to trends in full-time and part-time employment to identify any possible similar trends

- Coding is done, trying to get graphs to show

## Costs to corporations - why would they want to hire PT

# Using JOLTS data - Possibly Ran?
Can we identify trends in quiting rates?

## Decisions as a Policy Maker
If we are recommending policy, can we look at policies related to wage and hour requirements before, during, and after certain changes/trends in PT and FT 
