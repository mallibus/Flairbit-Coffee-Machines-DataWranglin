![DataScienceSeed Logo](http://www.datascienceseed.com/wp-content/uploads/2018/02/dsst.jpg)
## Dataset Hands-On Challenge 
Marcello's working notebook on the [Flairbit](http://www.flairb.it/) Challenge presented on the February 7 2019 event:

http://www.datascienceseed.com/2019/02/10/dataset-challenge-hands-on-1-flairbit-coffee-machines-rulex-churn-service/

Dataset details and download instructions are at the link above, in the Flairbit section of the event.

## The dataset
* Data related to professional coffe machines
* Dataset categories:
    * Counters
    * Cleanings
    * Faults
* One file per category per day
    *type_YYYYMMDDHHMMSS-an.csv (e.g., faults_20190103020001-an.csv)
* Common dataset feature
    * Machine serial number
    * Machine model
    * Timestamp (YYYY MM DD hh:mm:ss and week number)

**counters**

Serial | YYYY | MM | dd | hh:mm:ss | Week | Model | LabelCounter | AbsoluteCounter | RelativeCounter
-------|------|----|----|----------|------|-------|--------------|-----------------|----------------
1535632 | 2016 | 11 | 29 | 04:00:07 | 49 | model 31 | numcaffegenerale | 179112 | 0
1535632 | 2016 | 11 | 29 | 05:00:07 | 49 | model 31 | numcaffegenerale | 179120 | 8
1535632 | 2016 | 11 | 29 | 06:00:07 | 49 | model 31 | numcaffegenerale | 179158 | 38

**cleanings**

Serial | YYYY | MM | dd | hh:mm:ss | Week | Model | Errorcode 
-------|------|----|----|----------|------|-------|-----------
1535632 | 2016 | 11 | 29 | 04:00:07 | 49 | model 10 | 1
1535632 | 2016 | 11 | 29 | 05:00:07 | 49 | model 9 | 1 
1535632 | 2016 | 11 | 29 | 06:00:07 | 49 | model 31 |1 

**faults**

Serial | YYYY | MM | dd | hh:mm:ss | Week | Model | Errorcode | Critical 
-------|------|----|----|----------|------|-------|-----------|------------
1535632 | 2016 | 11 | 29 | 04:00:07 | 49 | model 62 | 185 | WARNING
1535632 | 2016 | 11 | 29 | 05:00:07 | 49 | model 20| 185 | WARNING
1535632 | 2016 | 11 | 29 | 06:00:07 | 49 | model 20 |185 | WARNING

## Warm up: Let’s query the CSV files
* How many connected machines?
* Counters types
* Faults distribution per model
* Cleanings misses distribution per model

## Challenges:

### Forecasting
* Predict faults occurrences based on counters patterns and cleaning misses

### Root cause analysis
* Find correlations between machine usage (counters and cleanings misses) and faults

## Credits

Thanks to [Flairbit](http://www.flairb.it/) for providing this dataset to the [DataScienceSeed](http://www.datascienceseed.com/) 
community! **This repository has no commercial purpose** it is provided for educational purposes alone.

![Flairbit](https://www.alleantia.com/wp-content/uploads/2013/11/FlairBit.png)
