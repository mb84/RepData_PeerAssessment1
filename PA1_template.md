# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data



```r
library(data.table)
```

```
## Warning: package 'data.table' was built under R version 3.1.2
```

```r
unzip(zipfile = "activity.zip")
adata <- read.csv(file = "activity.csv", header=TRUE)
adatadt <- data.table(adata)
```

## What is mean total number of steps taken per day?


```r
total_xday <- adatadt[,sum(steps), by = date]
setnames(total_xday,"V1","TotalSteps")
mean_totxday <- round(mean(total_xday$TotalSteps, na.rm = T),2)
hist(x=total_xday$TotalSteps)
```

![](./PA1_template_files/figure-html/question1-1.png) 

The mean total number of steps taken per day is 1.076619\times 10^{4} 

## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
