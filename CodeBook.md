---
title: "Code Book"
author: "Avantika Deb"
date: "01/06/2020"
output: word_document
---

#run_analysis.R performs the data preparation and cleaning in accordance to the guidelines of the course project.

##1. Dataset downloaded and extracted under the folder called UCI HAR Dataset

##2. Assign each data to variables
#features <- features.txt : 561 rows, 2 columns
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
#activities <- activity_labels.txt : 6 rows, 2 columns
List of activities performed when the corresponding measurements were taken and its codes (labels)
#subject_test <- test/subject_test.txt : 2947 rows, 1 column
contains test data of 9/30 test subjects being observed
#x_test <- test/X_test.txt : 2947 rows, 561 columns
contains recorded features of test data
#y_test <- test/y_test.txt : 2947 rows, 1 columns
contains test data of activities’code labels
#subject_train <- test/subject_train.txt : 7352 rows, 1 column
contains train data of 21/30 subjects being observed
#x_train <- test/X_train.txt : 7352 rows, 561 columns
contains recorded features of train data
#y_train <- test/y_train.txt : 7352 rows, 1 columns
contains train data of activities’code labels

##Merging the training and the test sets
#X (10299 rows, 561 columns) is created by merging x_train and x_test using rbind() function
#Y (10299 rows, 1 column) is created by merging y_train and y_test using rbind() function
#Subject (10299 rows, 1 column) is created by merging subject_train and subject_test using rbind() function
#Merged_Data (10299 rows, 563 column) is created by merging Subject, Y and X using cbind() function

##Extract only the measurements on the mean and standard deviation thus forming TidyData(10299 rows, 88 columns) is created by subsetting Merged_Data, selecting only columns: subject, code
##Use descriptive activity names to name the activities in the data set by replacing numbers in the code column with corresponding activity taken from second column of the activities variable

##Appropriately label the data set with descriptive variable names
#code column in TidyData renamed into activities
#All Acc in column’s name replaced by Accelerometer
#All Gyro in column’s name replaced by Gyroscope
#All BodyBody in column’s name replaced by Body
#All Mag in column’s name replaced by Magnitude
#All start with character f in column’s name replaced by Frequency
#All start with character t in column’s name replaced by Time

##Create a second, independent tidy data set with the average of each variable for each activity and each subject thus creating FinalData and saving it as a text file.




