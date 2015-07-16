# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

First, we read in the unzipped .csv file stored in our working directory.

```r
activity <- read.csv("./activity.csv", header=TRUE, sep=)
```

Now convert object from data frame to data table

```r
library(data.table)
activity <- data.table(activity)
```

## What is mean total number of steps taken per day?

1. First we plot a histogram of total steps for each day.

```r
sumSteps <- activity[, sum(steps, na.rm=T), by=date]
library(ggplot2)
plot1 <- ggplot(sumSteps, aes(date, V1)) + geom_histogram(stat='identity') + 
    ylab("Total steps taken each day")
print(plot1)
```

![](PA1_template_files/figure-html/unnamed-chunk-3-1.png) 

```r
head(sumSteps)
```

```
##          date    V1
## 1: 2012-10-01     0
## 2: 2012-10-02   126
## 3: 2012-10-03 11352
## 4: 2012-10-04 12116
## 5: 2012-10-05 13294
## 6: 2012-10-06 15420
```


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
