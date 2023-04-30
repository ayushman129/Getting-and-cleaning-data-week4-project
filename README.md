## **Getting and Cleaning Data Course Project**

This repository contains the project submission of ayushman129 for week 4 of the Getting and Cleaning Data course [Getting-and-cleaning-data-week4-Project](https://github.com/ayushman129/Getting-and-cleaning-data-week4-project). The following instructions explain how to run an analysis on the Human Activity Recognition dataset.

### **Dataset**

The dataset used in this project is the [Human Activity Recognition Using Smartphones](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones).

### **Files**

The repository contains the following files:

-   `CodeBook.md`: This file is a code book that describes the variables, the data, and any transformations or work that was performed to clean up the data.

-   `run_analysis.R`: This script performs data preparation and follows the 5 steps required as described in the course project's definition:

    -   Merge the training and the test sets to create one data set.

    -   Extract only the measurements on the mean and standard deviation for each measurement.

    -   Use descriptive activity names to name the activities in the data set.

    -   Appropriately label the data set with descriptive variable names.

    -   Create a second, independent tidy data set with the average of each variable for each activity and each subject from the data set in step 4.

-   `FinalData.txt`: This file contains the exported final data after going through all the sequences described above.
