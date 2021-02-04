![DataScienceSeed Logo](http://www.datascienceseed.com/wp-content/uploads/2018/02/dsst.jpg)
## Dataset Hands-On Challenge 
Marcello's working notebook on the [Flairbit](http://www.flairb.it/) Challenge presented on the February 7 2019 event:

http://www.datascienceseed.com/2019/02/10/dataset-challenge-hands-on-1-flairbit-coffee-machines-rulex-churn-service/

Dataset details and download instructions are at the link above, in the Flairbit section of the event.

Slides presented at the meetup on may 2019

http://www.datascienceseed.com/wp-content/uploads/2019/05/Flairbit-Challenge-Meetup-Slides.pdf

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

## Code
The code in the repo is in the format of three Jupyter Notebooks
* **Exploration.ipynb**  :  first file to look at, it includes data esploration of the dataset (please note that the dataset itslef is not in the repo! you have to look into the dataset presentation [here](http://www.datascienceseed.com/2019/02/10/dataset-challenge-hands-on-1-flairbit-coffee-machines-rulex-churn-service/) and find the slide with the link to a dropbox folder. The reason for this is to spread knowledge of the DataScienceSeed community and events. This notebook also takes care of generating intermediate dataset files (the .csv files in the repo) to be used for the forecast. 
* **LGBM Tabular 03_01_Fault_Clean_Count.ipynb** : failure forecast based on [LightGBM](https://lightgbm.readthedocs.io/en/latest/) algorithm. There is also some data rearranging to play with different time windows of data in the features side and in the target side. The results are fairly good: the models can predict with 85% of f1 score a failure of a machine in the next 5 days. There is also some feature interpretation based on [SHAP](https://shap.readthedocs.io/en/latest/).
* **Fastai Tabular Paperspace.ipynb** : failure forecast based on deep learning, using [Fast.ai tabular_learner](https://docs.fast.ai/tabular.data.html). I attempted to apply what is described in [Lessno4 of Fast.ai MOOC 2018 edition](https://course.fast.ai/videos/?lesson=4). The results are worst than LGBM, but this is just a dumb attempt!
## Credits

Thanks to [Flairbit](http://www.flairb.it/) for providing this dataset to the [DataScienceSeed](http://www.datascienceseed.com/) 
community! **This repository has no commercial purpose** it is provided for educational purposes alone.

![Flairbit](https://www.alleantia.com/wp-content/uploads/2013/11/FlairBit.png)
