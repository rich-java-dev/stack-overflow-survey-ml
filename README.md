# 51-white-mlproj-stackoverflow


## Background

The Stack Overflow Developer Survey (https://insights.stackoverflow.com/survey/2021) is an annual Questionaire which seeks to best understand the users of the popular Q&A board/site. The survey gathers demographics on developers including age, region, years experience, education, salary, favorite/used technologies. I have been participating in this survey for around the last 6 or 7 years as both a professional software developer and ethusiast. I like to keep up to date on what the latest technology trends are and this survey has been one of many sources reviewed.

Survey questions have changed overtime as a reflection of of tracking different trends, but some key questions are consistent. This project consists of analyzing response results from years 2011-2021.

https://www.kaggle.com/datasets/satoshidatamoto/stack-overflow-developer-survey-findings-and-mete

## Project Description

The goal of this project is to build a predictor for technology trends over time as identified by the questionaire. This will involve analyzing similar questions and responses over the different years. An additional goal is identifying relationships between question responses. There are all sorts of Bayesian and conditional probability questions which can be asked such as "If a developer Loves Rust are they more likely to know/use React or Angular as a front-end framework?" or "If  a PhD., were you more likely to have started coding at a younger age?"

In other words, given some arbitrary responses to some questions on the survey, how well can you predict responses to other questions, and which questions.

To summarize, the aim is to identify different patterns in responses both over time, and to find correlations between repsonses to build predictive models by determining which questions inform others.


## Performance Metric

Below are Confusion Matricies associated with 3 Features of the data-set we will test to analyze the resulting model/classifiers' accuracy.

1) Classify/Predict which technologies people would like to work with:
<!--- What is the output/what are the values that would populate this matrix? --->

| | Predicted: WantToWorkWith    |  Predicted: !WantToWorkWith|
| --| -- |---| 
|Actual: WantToWorkWith|  |  |
|Actual: !WantToWorkWith|  |  | 



| | Predict: Javascript Yes | Predict: Python Yes | Predict: HTML/CSS Yes | Predict: TypeScript Yes | Predict: SQL Yes | Predict: Java Yes | Predict: Rust Yes | Predict: Go Yes | Predict: Python No | Predict: HTML/CSS No | Predict: TypeScript No | Predict: SQL No | Predict: Java No | Predict: Rust No | Predict: Go No |
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
| Actual Javascript Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Python Yes: | 37 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual HTML/CSS Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual TypeScript Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual SQL Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Java Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Rust Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Go Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Javascript No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Python No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual HTML/CSS No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual TypeScript No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual SQL No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Java No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Rust No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Go No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |


2) Classify/Predict which technologies people are likely to have already worked with:

| | Predicted: HaveWorkWith    |  Predicted: !HaveWorkWith|
| --| -- |---| 
|Actual: HaveWorkWith|  |  |
|Actual: !HaveWorkWith|  |  | 

More Detailed Break down:

| | Predict: Javascript Yes | Predict: Python Yes | Predict: HTML/CSS Yes | Predict: TypeScript Yes | Predict: SQL Yes | Predict: Java Yes | Predict: Rust Yes | Predict: Go Yes | Predict: Python No | Predict: HTML/CSS No | Predict: TypeScript No | Predict: SQL No | Predict: Java No | Predict: Rust No | Predict: Go No |
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
| Actual Javascript Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Python Yes: | 37 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual HTML/CSS Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual TypeScript Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual SQL Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Java Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Rust Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Go Yes: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Javascript No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Python No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual HTML/CSS No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual TypeScript No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual SQL No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Java No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Rust No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |
| Actual Go No: | 37008 | 2 | 3 | 4 | 5 |6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 |

3) Classify/Predict yrs experience: 
<!--- What are we predicting yrs of experience based on? Is this what you were talking about above, with "If a PhD., were you more likely to have started coding at a younger age?" or is this related to professional years of experience? If so, what are we trying to find based on yrs of professional experience? --->

| | Predicted: yrsExp    |  Predicted:  < yrsExp |
| --| -- |---| 
|Actual: yrsExp|  |  |
|Actual: < yrsExp|  |  | 
