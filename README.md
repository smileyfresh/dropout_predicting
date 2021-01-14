# Sealing the Cracks

## Overview

This project uses machine learning techniques to build a model that will predict whether a student is likely to dropout at the high school level. I want to explore ways to predict early whether a student will struggle at the high school level, and by determining the features that contribute to those struggles better address them so that students can have more positive educational experiences and have more fulfilling lives. 

## Data Source

Data is sourced from the Harvard Strategic Data Project's [OpenSDP](https://sdp.cepr.harvard.edu/opensdp). Specifically, I will be utilizing the following [data](https://github.com/OpenSDP/predicting_dropouts/tree/master/data) and [guides](https://hwpi.harvard.edu/files/sdp/files/sdp-toolkit-cg-data-linking-guide.pdf) from the SDP toolkit.

## Approach

After initial exploratory data analysis, I will determine the most relevant features included in the data set. I will then build a binary classification model using scikit-learn's random forest classifier to predict the target of dropout/non-dropout. I will then test the accuracy of these models and explore options for tuning.

## Exploratory Data Analysis

I first examined my targets -- Dropout vs Graduating Students --  and discovered that students who dropped out accounted for about 19% of the data.

<p align="center">
    <img src="https://github.com/smileyfresh/dropout_predicting/blob/main/data/images/DropoutRate.png" width="500">
</p>    

I then examined the distributions of the following features across both students who dropped out and those who graduated:

    - "dropout" - target variable, whether or not student dropped out,
    - "gpa" - student grade point average,
    - "pct_days_absent" - percent days absent,
    - "math_ss" - math standardized test score,
    - "read_ss" - reading standardized test score,
    - "gifted" - whether stu![]dent was ever enrolled in a gifted program,
    - "ever_alternative" - whether student was ever enrolled in a alternative program,
    - "iep" - whether student was ever assigned an individualized education plan,
    - "frpl" - whether student was ever in federal free or reduced price lunch program,
    - "ell" - whether student was ever enrolled in an english language learner(english as second language) program
    
### Grade Point Average

As seen in the histogram below, the distributions of GPA across those students who dropped out and those who did not differ. 

<p align="center">
    <img src="https://github.com/smileyfresh/dropout_predicting/blob/main/data/images/GPA%20across%20Dropouts%20and%20Grads.png" width="500">
</p>

The GPAs for students who dropped out tended to be lower than those of students who went on to graduate. The average GPA of students who dropped out was 1.6, while the average for those who went on to graduate was 2.7.

Standardized testing scores were also lower for students who dropped out as seen in the histograms below for both the 8th grade and 11th grade level.


<p align="center">
    <img src="https://github.com/smileyfresh/dropout_predicting/blob/main/data/images/Math8Scores.png" width="400">
    <img src="https://github.com/smileyfresh/dropout_predicting/blob/main/data/images/Read8Scores.png" width="400">
</p>

The mean scores for the rising 9th grade (8th grade exam) were 30.5 and 40.8 (on a 100 point scale) for math and reading for students who did not complete high school. The mean scores for students who graduated were 43.3 and 48.6 for math and reading, respectively. 

In the eleventh grade, the distributions of standardized testing scores(ACT scores) did still tend to be lower for dropouts than grads, with the mean scores of 17.1 and 17.5(on an 36 point scale) for students who did not complete, and 19.1 and 19.9 for students who graduated. However, the most suprising indicator here was not the scores of the test, but whether or not the student chose to sit for the exam, with 33% of dropouts choosing not to take the ACT, compared with 12% of those who graduated.

<img src="https://github.com/smileyfresh/dropout_predicting/blob/main/data/images/Math11Scores.png" width="100" height="100">
<img src="https://github.com/smileyfresh/dropout_predicting/blob/main/data/images/Read11Scores.png" width="100" height="100">

