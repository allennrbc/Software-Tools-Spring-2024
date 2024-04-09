# Haylee's Analysis for Check Point 1
Below are analysis items for identifying potential impacts of part-time employment. The first two analysis focus on wages while the third analysis uses a quality of life indicator  and a benefit of full-time work: access to health insurance. 

While the code is available in this document, results can be seen on RPubs here


## Wages
How much are part-time workers making compared to full-time workers?
- Need to build

## Comparing Wages to Purchasing Power
Compare wages (https://fred.stlouisfed.org/series/CES4200000003) to CPI (https://fred.stlouisfed.org/series/CPIAUCSL) and calculate to get the real wage 
Real Wage in a year = (Nominal Wage in a Year/CPI in a Year)x100
Wage Purchasing Power in a chosen year = (Nominal wage in the base year/ CPI in the base year)(CPI in the selected year)

Doing this will tell us if wages are the problem: have wages paid to retail-workers kept up pace in terms of purchasing power?

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

Comparing health insurance coverage by type of coverage

First, the data is reviewed and the insurance type "Total" is eliminated as it is the total of all insurace types and always equals 1

```{r Health Insurance Data Cleanup}
HealthInsuranceCoverage<-read.csv("HealthInsuranceCoverage.csv", header=TRUE)

#view data
summary(HealthInsuranceCoverage)

#check for null values
sum(is.na(HealthInsuranceCoverage))


#Eliminate 'Total' as it will always be 1
HealthInsCoverageNew<- filter(HealthInsuranceCoverage, Typle != "Total")

#view data
summary(HealthInsCoverageNew)
```

Plot comparison graph of health insurance coverage by type

```{r Health Insurance Plot}
#plot
ggplot(HealthInsCoverageNew, aes(x=Year, y=Percentage, group = 1))+
  geom_line()+facet_wrap(~ Typle) 
```

## Costs to corporations - why would they want to hire PT

### Costs of Full-Time employees
https://money.usnews.com/money/personal-finance/articles/how-many-part-time-jobs-does-it-take-to-earn-a-full-time-income#:~:text=Median%20Earnings%20of%20U.S.%20Workers&text=That%20means%20the%20typical%20part,according%20to%202022%20BLS%20data.

### Using JOLTS data - Possibly Ran?
Can we identify trends in quiting rates?

