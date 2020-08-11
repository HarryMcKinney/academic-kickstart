---
title: Imputing Null Values
author: Matt Mitchell
date: '2020-08-11'
slug: imputing-null-values
categories: []
tags: []
---

#Test Blogdown Page

#Load the package
library(zoo)

#fill by last observed value full documentation: https://www.rdocumentation.org/packages/zoo/versions/1.8-8/topics/na.locf
#na.rm option specifies whether leading null values should be removed
na.locf(object, na.rm = TRUE, …)

#Use next date rather than last date (by default fromLast=False)

na.locf(object, na.rm = TRUE, fromLast=True,…)

#fill using mean
#aggregate(series_to_agg, by, FUN)
#by - index vector of the same length asindex(x)which defines aggregation groups and the new index to be associated with each group.
#If by is a function, then it is applied to index(x)to obtain the aggregation groups
aggregate(x, as.Date(as.yearmon(time(x))), mean)

#fill using median; also use aggregate as above, replacing mean with median
aggregate(x, as.Date(as.yearmon(time(x))), median)
