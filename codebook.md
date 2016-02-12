##  Script Name: run_analysis.R
##  Author: Craig Sclater
##  Date: 02/11/2016
##  Purpose: Combine test and training telemetry data gathered from wearable devices, and prepare a tidy data set from it on the average mean and standard deviation measurements that can be used for later analysis.
##  Data set : Human Activity Recognition Using Smartphones Data Set, compiled by the Center for Machine Learning and Intelligent Systems at The University of California, Irvine.  This Human Activity Recognition database was built from the recordings of 30 subjects performing activities of daily living while carrying a waist-mounted smartphone with embedded inertial sensors.

## The following transformations were made on the data set:
## Step 1 : Merge the test and training data into one data set. 
#
### 1.a Read and combine the test and training activity data.
### 1.b Read and combine the test and training subject data.
### 1.c Read and combine the test and training feature data.
#
## Step 2: Appropriately label the data set with descriptive variable names. 
#
### 2.a Read the feature labels.
### 2.b Clean up feature names.
### 2.c Assign feature names to the features data set.
#
##  Step 3 : Extract only the measurements on the mean and standard deviation for each measurement. 
#
##  Step 4 : Combine the subject, activity, and features data. 
#
##  Step 5 : Use descriptive activity names to name the activities in the data set. 
#
# 5.a Read the activity labels.
# 5.b Merge activity labels into the combined data set.
##  Step 6 : Prepare a tidy data set with the average of each variable for each activity and subject. 

### 6.a Factorize activity.name and subject.id.

### 6.b Aggregate tidy data.

### 6.c Write tidy data to csv file.