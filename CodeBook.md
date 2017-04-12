##Getting and Cleaning Data Course Project

The raw data was provided by the University of California and can be downloaded from the following address: https://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The original dataset included the following files:

    “README.txt”
    “features_info.txt”: Shows information about the variables used on the feature vector.
    “features.txt”: List of all features.
    “activity_labels.txt”: Links the class labels with their activity name.
    “train/X_train.txt”: Training set.
    “train/y_train.txt”: Training labels.
    ”test/X_test.txt”: Test set.
    “test/y_test.txt”: Test labels.

The resulting tidy data set can be found in this repository ("tidy_data.txt").

Description of the "tidy_data.txt" file

The final tidy data file contains the following variables:

Identifiers

    subject --> ID of the test subject
    activity --> IDs of the type of activity that was performed by the subject during the experiment

Activity Labels

	LAYING
	SITTING
	STANDING
	WALKING
	WALKING_DOWNSTAIRS
	WALKING_UPSTAIRS


Measurments

	timeBodyAccelerometer-mean()-X
	timeBodyAccelerometer-mean()-Y
	timeBodyAccelerometer-mean()-Z
	timeBodyAccelerometer-std()-X
	timeBodyAccelerometer-std()-Y
	timeBodyAccelerometer-std()-Z
	timeGravityAccelerometer-mean()-X
	timeGravityAccelerometer-mean()-Y
	timeGravityAccelerometer-mean()-Z
	timeGravityAccelerometer-std()-X
	timeGravityAccelerometer-std()-Y
	timeGravityAccelerometer-std()-Z
	timeBodyAccelerometerJerk-mean()-X
	timeBodyAccelerometerJerk-mean()-Y
	timeBodyAccelerometerJerk-mean()-Z
	timeBodyAccelerometerJerk-std()-X
	timeBodyAccelerometerJerk-std()-Y
	timeBodyAccelerometerJerk-std()-Z
	timeBodyGyroscope-mean()-X
	timeBodyGyroscope-mean()-Y
	timeBodyGyroscope-mean()-Z
	timeBodyGyroscope-std()-X
	timeBodyGyroscope-std()-Y
	timeBodyGyroscope-std()-Z
	timeBodyGyroscopeJerk-mean()-X
	timeBodyGyroscopeJerk-mean()-Y
	timeBodyGyroscopeJerk-mean()-Z
	timeBodyGyroscopeJerk-std()-X
	timeBodyGyroscopeJerk-std()-Y
	timeBodyGyroscopeJerk-std()-Z
	timeBodyAccelerometerMagnitude-mean()
	timeBodyAccelerometerMagnitude-std()
	timeGravityAccelerometerMagnitude-mean()
	timeGravityAccelerometerMagnitude-std()
	timeBodyAccelerometerJerkMagnitude-mean()
	timeBodyAccelerometerJerkMagnitude-std()
	timeBodyGyroscopeMagnitude-mean()
	timeBodyGyroscopeMagnitude-std()
	timeBodyGyroscopeJerkMagnitude-mean()
	timeBodyGyroscopeJerkMagnitude-std()
	frequencyBodyAccelerometer-mean()-X
	frequencyBodyAccelerometer-mean()-Y
	frequencyBodyAccelerometer-mean()-Z
	frequencyBodyAccelerometer-std()-X
	frequencyBodyAccelerometer-std()-Y
	frequencyBodyAccelerometer-std()-Z
	frequencyBodyAccelerometer-meanFreq()-X
	frequencyBodyAccelerometer-meanFreq()-Y
	frequencyBodyAccelerometer-meanFreq()-Z
	frequencyBodyAccelerometerJerk-mean()-X
	frequencyBodyAccelerometerJerk-mean()-Y
	frequencyBodyAccelerometerJerk-mean()-Z
	frequencyBodyAccelerometerJerk-std()-X
	frequencyBodyAccelerometerJerk-std()-Y
	frequencyBodyAccelerometerJerk-std()-Z
	frequencyBodyAccelerometerJerk-meanFreq()-X
	frequencyBodyAccelerometerJerk-meanFreq()-Y
	frequencyBodyAccelerometerJerk-meanFreq()-Z
	frequencyBodyGyroscope-mean()-X
	frequencyBodyGyroscope-mean()-Y
	frequencyBodyGyroscope-mean()-Z
	frequencyBodyGyroscope-std()-X
	frequencyBodyGyroscope-std()-Y
	frequencyBodyGyroscope-std()-Z
	frequencyBodyGyroscope-meanFreq()-X
	frequencyBodyGyroscope-meanFreq()-Y
	frequencyBodyGyroscope-meanFreq()-Z
	frequencyBodyAccelerometerMagnitude-mean()
	frequencyBodyAccelerometerMagnitude-std()
	frequencyBodyAccelerometerMagnitude-meanFreq()
	frequencyBodyAccelerometerJerkMagnitude-mean()
	frequencyBodyAccelerometerJerkMagnitude-std()
	frequencyBodyAccelerometerJerkMagnitude-meanFreq()
	frequencyBodyGyroscopeMagnitude-mean()
	frequencyBodyGyroscopeMagnitude-std()
	frequencyBodyGyroscopeMagnitude-meanFreq()
	frequencyBodyGyroscopeJerkMagnitude-mean()
	frequencyBodyGyroscopeJerkMagnitude-std()
	frequencyBodyGyroscopeJerkMagnitude-meanFreq()

