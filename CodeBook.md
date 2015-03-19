##Introduction

The script run_analysis.R performs the 5 steps described in the course project's definition:

	1. Merges the training and the test sets to create one data set.
	2. Extracts only the measurements on the mean and standard deviation for each measurement. 
	3. Uses descriptive activity names to name the activities in the data set
	4. Appropriately labels the data set with descriptive variable names. 
	5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

#Code

The code held in run_analysis.R  performs this task as follows:

1.  All the similar data is merged using the rbind() function (files having the same number of columns and referring to the same entities)
2.  Only those columns with the mean and standard deviation measures are taken from the whole dataset.
3.  Columns, they are given the correct names, taken from features.txt.
4.  Activity names and IDs are taken from activity_labels.txt and are substituted in the dataset
5.  Those columns with vague column names are corrected.
6.  A new dataset is generated with all the average measures for each subject and activity type

#Output

Output from the code can be found in averages_data.txt.  This consists of 30 subjects * 6 activities = 180 rows

#Variables


x_train - data from train/x_train.txt 
y_train - data from train/y_train.txt 
x_test - data from test/x_test.txt 
y_test - data from test/y_test.txt  
subject_train - data from train/subject_train.txt  
subject_test - data from train/subject_test.txt
x_data - merged data from x_train and x_test
y_data - merged data from y_train and y_test 
subject_datamerged - merged data from subject_train and subject_test
mean_and_std_features - a numeric vector used to extract the desired data
	A similar approach is taken with activity names through the activities variable.
all_data - merges x_data, y_data and subject_data in a big dataset.
averages_data - contains the relevant averages which will be later stored in a .txt file. 

ddply() from the plyr package is used to apply colMeans() and ease the development.