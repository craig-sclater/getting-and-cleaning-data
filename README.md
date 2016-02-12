## getting-and-cleaning-data
 
###The purpose of this project is to collect, work with, and clean a data set.  The source data used is the Human Activity Recognition Using Smartphones Data Set, compiled by the Center for Machine Learning and Intelligent Systems at The University of California, Irvine.  This Human Activity Recognition database was built from the recordings of 30 subjects performing activities of daily living while carrying a waist-mounted smartphone with embedded inertial sensors.

###The run_analysis.R code file in this repository collects the test and training data sets, and combines them with labels for the activities recorded and the measurements made.  It then gathers a subset of the data that includes all subjects and activities, but only those measurements reporting a mean or standard deviation.  The final output of the script is a file named tidy.csv, which is an aggregation of the mean and standard deviation data set, recording the average values for each measurement.

### The following transformations were made on the data set.
### Step 1 : Merge the test and training data into one data set. 
* 1.a Read and combine the test and training activity data.
* 1.b Read and combine the test and training subject data.
* 1.c Read and combine the test and training feature data.

### Step 2: Appropriately label the data set with descriptive variable names. 
* 2.a Read the feature labels.
* 2.b Clean up feature names.
* 2.c Assign feature names to the features data set.

### Step 3 : Extract only the measurements on the mean and standard deviation for each measurement. 

### Step 4 : Combine the subject, activity, and features data. 

### Step 5 : Use descriptive activity names to name the activities in the data set. 
* 5.a Read the activity labels.
* 5.b Merge activity labels into the combined data set.

### Step 6 : Prepare a tidy data set with the average of each variable for each activity and subject. 
* 6.a Factorize activity.name and subject.id.
* 6.b Aggregate tidy data.
* 6.c Write tidy data to csv file.

### The final data set has the following variables.
* subject
* activity
* timeBodyAccelerometer-mean()-X
* timeBodyAccelerometer-mean()-Y
* timeBodyAccelerometer-mean()-Z
* timeBodyAccelerometer-std()-X
* timeBodyAccelerometer-std()-Y
* timeBodyAccelerometer-std()-Z
* timeGravityAccelerometer-mean()-X
* timeGravityAccelerometer-mean()-Y
* timeGravityAccelerometer-mean()-Z
* timeGravityAccelerometer-std()-X
* timeGravityAccelerometer-std()-Y
* timeGravityAccelerometer-std()-Z
* timeBodyAccelerometerJerk-mean()-X
* timeBodyAccelerometerJerk-mean()-Y
* timeBodyAccelerometerJerk-mean()-Z
* timeBodyAccelerometerJerk-std()-X
* timeBodyAccelerometerJerk-std()-Y
* timeBodyAccelerometerJerk-std()-Z
* timeBodyGyroscope-mean()-X
* timeBodyGyroscope-mean()-Y
* timeBodyGyroscope-mean()-Z
* timeBodyGyroscope-std()-X
* timeBodyGyroscope-std()-Y
* timeBodyGyroscope-std()-Z
* timeBodyGyroscopeJerk-mean()-X
* timeBodyGyroscopeJerk-mean()-Y
* timeBodyGyroscopeJerk-mean()-Z
* timeBodyGyroscopeJerk-std()-X
* timeBodyGyroscopeJerk-std()-Y
* timeBodyGyroscopeJerk-std()-Z
* timeBodyAccelerometerMagnitude-mean()
* timeBodyAccelerometerMagnitude-std()
* timeGravityAccelerometerMagnitude-mean()
* timeGravityAccelerometerMagnitude-std()
* timeBodyAccelerometerJerkMagnitude-mean()
* timeBodyAccelerometerJerkMagnitude-std()
* timeBodyGyroscopeMagnitude-mean()
* timeBodyGyroscopeMagnitude-std()
* timeBodyGyroscopeJerkMagnitude-mean()
* timeBodyGyroscopeJerkMagnitude-std()
* frequencyBodyAccelerometer-mean()-X
* frequencyBodyAccelerometer-mean()-Y
* frequencyBodyAccelerometer-mean()-Z
* frequencyBodyAccelerometer-std()-X
* frequencyBodyAccelerometer-std()-Y
* frequencyBodyAccelerometer-std()-Z
* frequencyBodyAccelerometerJerk-mean()-X
* frequencyBodyAccelerometerJerk-mean()-Y
* frequencyBodyAccelerometerJerk-mean()-Z
* frequencyBodyAccelerometerJerk-std()-X
* frequencyBodyAccelerometerJerk-std()-Y
* frequencyBodyAccelerometerJerk-std()-Z
* frequencyBodyGyroscope-mean()-X
* frequencyBodyGyroscope-mean()-Y
* frequencyBodyGyroscope-mean()-Z
* frequencyBodyGyroscope-std()-X
* frequencyBodyGyroscope-std()-Y
* frequencyBodyGyroscope-std()-Z
* frequencyBodyAccelerometerMagnitude-mean()
* frequencyBodyAccelerometerMagnitude-std()
* frequencyBodyAccelerometerJerkMagnitude-mean()
* frequencyBodyAccelerometerJerkMagnitude-std()
* frequencyBodyGyroscopeMagnitude-mean()
* frequencyBodyGyroscopeMagnitude-std()
* frequencyBodyGyroscopeJerkMagnitude-mean()
* frequencyBodyGyroscopeJerkMagnitude-std()
