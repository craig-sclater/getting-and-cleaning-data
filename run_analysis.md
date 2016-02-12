# **********************************************************************************************
#  Script Name: run_analysis.R
#  Author: Craig Sclater
#  Date: 02/11/2016
#  Purpose: Combine test and training telemetry data gathered from wearable devices
#           and prepare a tidy data set from it on the average mean and standard deviation 
#           measurements that can be used for later analysis.
# **********************************************************************************************
#
#  **** Step 1 : Merge the test and training data into one data set. ****
#
# 1.a >> read and combine the test and training activity data
activity <- read.table(file.path(getwd(),"UCI HAR Dataset","test","y_test.txt"), header=FALSE, col.names="activity.id")
activity <- rbind(activity, read.table(file.path(getwd(),"UCI HAR Dataset","train","y_train.txt"), header=FALSE, col.names="activity.id"))

# 1.b >> read and combine the test and training subject data
subjects <- read.table(file.path(getwd(),"UCI HAR Dataset","test","subject_test.txt"), header=FALSE, col.names="subject.id")
subjects <- rbind(subjects, read.table(file.path(getwd(),"UCI HAR Dataset","train","subject_train.txt"), header=FALSE, col.names="subject.id"))

# 1.c >> read and combine the test and training feature data
features <- read.table(file.path(getwd(), "UCI HAR Dataset","test","X_test.txt"), header=FALSE)
features <- rbind(features, read.table(file.path(getwd(), "UCI HAR Dataset","train","X_train.txt"), header=FALSE))

#
#  **** Step 2: Appropriately label the data set with descriptive variable names. ****
#
# 2.a >> read the feature labels
feature_labels <- read.table(file.path(getwd(),"UCI HAR Dataset","features.txt"), header=FALSE, col.names=c("feature.id","feature.name"))

# 2.b >> clean up feature names
feature_labels$feature.name <- gsub("^t", "time", feature_labels$feature.name)
feature_labels$feature.name <- gsub("^f", "frequency", feature_labels$feature.name)
feature_labels$feature.name <- gsub("Acc", "Accelerometer", feature_labels$feature.name)
feature_labels$feature.name <- gsub("Gyro", "Gyroscope", feature_labels$feature.name)
feature_labels$feature.name <- gsub("Mag", "Magnitude", feature_labels$feature.name)
feature_labels$feature.name <- gsub("BodyBody", "Body", feature_labels$feature.name)

# 2.c >> assign feature names to the features data set
names(features) <- feature_labels$feature.name

# **** Step 3 : Extract only the measurements on the mean and standard deviation for each measurement. ****
#
features <- features[,grepl("mean\\(\\)|std\\(\\)",feature_labels$feature.name)]

# **** Step 4 : Combine the subject, activity, and features data. ****
#
combined_data <- cbind(subjects, activity, features)

# **** Step 5 : Use descriptive activity names to name the activities in the data set. ****
#
# 5.a >> read the activity labels
activity_labels <- read.table(file.path(getwd(),"UCI HAR Dataset","activity_labels.txt"), header=FALSE, col.names=c("activity.id","activity.name"))

# 5.b >> merge activity labels into the combined data set
combined_data <- merge(activity_labels, combined_data, by.x="activity.id", by.y="activity.id", all=TRUE)

# **** Step 6 : Prepare a tidy data set with the average of each variable for each activity and subject. ****
#
# 6.a >> factorize activity.name and subject.id
combined_data$activity.name <- as.factor(combined_data$activity.name)
combined_data$subject.id <- as.factor(combined_data$subject.id)

# 6.b >> aggregate tidy data
tidy_data <- aggregate(x=combined_data[,4:69], by=list(subject=combined_data$subject.id,activity=combined_data$activity.name), FUN=mean)

# 6.c >> write file
write.table(tidy_data, , file="tidy.csv", sep=",", col.names=TRUE, row.names=FALSE)




