# ProgrammingAssignmentCourse3
Programming Assignment for Course 3 of Data Scientist on Coursera
##Getting and Cleaning Data Course Project

##The purpose of this project is to demonstrate your ability to collect, work with, and clean a data set.
##The goal is to prepare tidy data that can be used for later analysis. 
##You will be required to submit: 
##1) a tidy data set as described below, 
##2) a link to a Github repository with your script for performing the analysis, and 
##3) a code book that describes the variables, the data, and any transformations or work that you performed to clean up the data called CodeBook.md. 
##You should also include a README.md in the repo with your scripts. This repo explains how all of the scripts work and how they are connected.

##You should create one R script called run_analysis.R that does the following:

##	Merges the training and the test sets to create one data set.
##	Extracts only the measurements on the mean and standard deviation for each measurement.
##	Uses descriptive activity names to name the activities in the data set
##	Appropriately labels the data set with descriptive variable names.
##	From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.



##EXECUTION

##0.1. Download file
	##Downmoad zipfile from "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip" and unzip in working directory. A subdirectory "UCI HAR Dataset" with files and more subdirs is created in the working directory. I assume the working directory was already correctly set (in the settings of R).

	fileurl <- "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"
	download.file(fileurl,"UCI HAR Dataset.zip", mode = "wb")
	unzip("UCI HAR Dataset.zip", exdir = getwd())



##0.2. Read Data
	##Read data and save in data.frames called "training" and "test".

	##features	

		features <- read.csv("./UCI HAR Dataset/features.txt", header = FALSE, sep = " ")
		features <- as.character(features[,2])

	##training

		training_X <- read.table("./UCI HAR Dataset/train/X_train.txt")
		training_activity <- read.table("./UCI HAR Dataset/train/y_train.txt", header = FALSE, sep = " ")
		training_subject <- read.table("./UCI HAR Dataset/train/subject_train.txt",header = FALSE, sep = " ")

		training <-  data.frame(training_subject, training_activity, training_X)
		names(training) <- c(c("subject", "activity"), features)

	##test

		test_X <- read.table("./UCI HAR Dataset/test/X_test.txt")
		test_activity <- read.table("./UCI HAR Dataset/test/y_test.txt", header = FALSE, sep = " ")
		test_subject <- read.table("./UCI HAR Dataset/test/subject_test.txt", header = FALSE, sep = " ")

		test <-  data.frame(test_subject, test_activity, test_X)
		names(test) <- names(training)



##1. Merges the training and the test sets to create one data set

	merged_training_testing <- rbind(training, test)



##2. Extracts only the measurements on the mean and standard deviation for each measurement

	mean_std.dev <- grep("mean|std", features)
	data_result <- merged_training_testing[,c(1,2,mean_std.dev + 2)]



##3. Uses descriptive activity names to name the activities in the data set
	##for "descriptive activity names" use file "activity_labels.txt"

	activity_names <- read.table("./UCI HAR Dataset/activity_labels.txt", header = FALSE)
	activity_names <- as.character(activity_names[,2])
	data_result$activity <- activity_names[data_result$activity]



##4. Appropriately labels the data set with descriptive variable names.
	##prefix "t" is replaced by "Time"
	##"Acc" is replaced by "Accelerometer"
	##"Gyro" is replaced by "Gyroscope"
	##prefix "f" is replaced by "Frequency"
	##"Mag" is replaced by "Magnitude"
	##"BodyBody" is replaced by "Body"

	names(data_result) <- gsub("^t", "time", names(data_result))
	names(data_result) <- gsub("^f", "frequency", names(data_result))
	names(data_result) <- gsub("Acc", "Accelerometer", names(data_result))
	names(data_result) <- gsub("Gyro", "Gyroscope", names(data_result))
	names(data_result) <- gsub("Mag", "Magnitude", names(data_result))
	names(data_result) <- gsub("BodyBody", "Body", names(data_result))



##5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
	
	tidy_data <- aggregate(data_result[,3:ncol(data_result)], by = list(activity = data_result$activity, subject = data_result$subject),FUN = mean)
		
	write.table(tidy_data, file = "tidy_data.txt", row.name=FALSE)


