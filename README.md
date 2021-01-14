# Sealing the Cracks

## Overview

This project uses machine learning techniques to build a model that will predict whether a student is likely to dropout at the high school level. I want to explore ways to predict early whether a student will struggle at the high school level, and by determining the features that contribute to those struggles better address them so that students can have more positive educational experiences and have more fulfilling lives. 

## Data Source

Data is sourced from the Harvard Strategic Data Project's [OpenSDP](https://sdp.cepr.harvard.edu/opensdp). Specifically, I will be utilizing the following [data](https://github.com/OpenSDP/predicting_dropouts/tree/master/data) and [guides](https://hwpi.harvard.edu/files/sdp/files/sdp-toolkit-cg-data-linking-guide.pdf) from the SDP toolkit.

## Approach

After initial exploratory data analysis, I will determine the most relevant features included in the data set. I will then build a binary classification model using scikit-learn's random forest classifier to predict the target of dropout/non-dropout. I will then test the accuracy of these models and explore options for tuning.

## Exploratory Data Analysis

I first examined my targets -- Dropout vs Graduating Students --  and discovered that students who dropped out accounted for about 19% of the data.

![](https://github.com/smileyfresh/dropout_predicting/blob/main/data/images/DropoutRate.png)

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

![](https://github.com/smileyfresh/dropout_predicting/blob/main/data/images/GPA%20across%20Dropouts%20and%20Grads.png)

The GPAs for students who dropped out tended to be lower than those of students who went on to graduate. The average GPA of students who dropped out was 1.6, while the average for those who went on to graduate was 2.7.

Standardized testing scores were also lower for students who dropped out as seen in the histograms below for both the 8th grade and 11th grade level.

![] (https://github.com/smileyfresh/dropout_predicting/blob/main/data/images/Math8Scores.png) ![](https://github.com/smileyfresh/dropout_predicting/blob/main/data/images/Read8Scores.png)
