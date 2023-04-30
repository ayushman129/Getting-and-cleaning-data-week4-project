## CodeBook

The `run_analysis.R` script performs the following steps on a dataset:

1.  **Download the dataset**
    -   The dataset is downloaded and extracted under the folder called `UCI HAR Dataset`.
2.  **Assign each data to variables**
    -   The script assigns the following variables to the data:
        -   `features` from `features.txt`: 561 rows, 2 columns
        -   `activities` from `activity_labels.txt`: 6 rows, 2 columns
        -   `subject_test` from `test/subject_test.txt`: 2947 rows, 1 column
        -   `x_test` from `test/X_test.txt`: 2947 rows, 561 columns
        -   `y_test` from `test/y_test.txt`: 2947 rows, 1 column
        -   `subject_train` from `train/subject_train.txt`: 7352 rows, 1 column
        -   `x_train` from `train/X_train.txt`: 7352 rows, 561 columns
        -   `y_train` from `train/y_train.txt`: 7352 rows, 1 column
3.  **Merge the training and test sets to create one data set**
    -   The script merges the data into the following variables:
        -   `X` (10299 rows, 561 columns) by merging `x_train` and `x_test` using **rbind()** function
        -   `Y` (10299 rows, 1 column) by merging `y_train` and `y_test` using **rbind()** function
        -   `Subject` (10299 rows, 1 column) by merging `subject_train` and `subject_test` using **rbind()** function
        -   `Merged_Data` (10299 rows, 563 columns) by merging `Subject`, `Y`, and `X` using **cbind()** function
4.  **Extract only the measurements on the mean and standard deviation for each measurement**
    -   The script creates a new variable called `TidyData` (10299 rows, 88 columns) by subsetting `Merged_Data`, selecting only columns: `subject`, `code`, and the measurements on the mean and standard deviation (`std`) for each measurement.
5.  **Use descriptive activity names to name the activities in the data set**
    -   The script replaces entire numbers in the `code` column of the `TidyData` variable with corresponding activity taken from the second column of the `activities` variable.
6.  **Appropriately label the data set with descriptive variable names**
    -   The script renames the columns of the `TidyData` variable:
        -   Renames the `code` column into `activities`
        -   Replaces all `Acc` in column names with `Accelerometer`
        -   Replaces all `Gyro` in column names with `Gyroscope`
        -   Replaces all `BodyBody` in column names with `Body`
        -   Replaces all `Mag` in column names with `Magnitude`
        -   Replaces all start with character 'f' in column names with 'Frequency'
        -   Replaces all start with character 't' in column names with 'Time'
7.  **Create a second, independent tidy data set with the average of each variable for each activity and each subject**
    -   The script creates a new variable called `FinalData` (180 rows, 88 columns) by summarizing the `TidyData` variable, taking the means of each variable for each activity and each subject after grouped by subject and activity.
    -   Finally, it exports the `FinalData` variable into a file called `FinalData.txt`.
