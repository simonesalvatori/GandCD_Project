# Getting and Cleaning Data - Course Project
The script called run_analysis.R does the following:  
1. Merges the training and the test sets to create one data set  
2. Extracts only the measurements on the mean and standard deviation for each measurement  
3. Uses descriptive activity names to name the activities in the data set  
4. Appropriately labels the data set with descriptive activity names, i.e.appropriately label the data set with tidy descriptive variable names  
5. Creates a second, independent tidy data set with the average of each variable f or each activity and each subject  
6. Saves the tidy data set in a text file, using tabs as separators  



### 1. Merges the training and the test sets to create one data set

#### 1.a reads the data sets, var names and activity labels

```r
x_test <-read.table('./UCI HAR Dataset/test/X_test.txt') # main dataset dim() 7352X561
y_test <-read.table('./UCI HAR Dataset/test/y_test.txt') # additional column dim() 7352X1 adding the activity-labels 1 to 6
subject_test <-read.table('./UCI HAR Dataset/test/subject_test.txt') # additional column dim() 7352X1 adding the subject 1 to 30


x_train <-read.table('./UCI HAR Dataset/train/X_train.txt')
y_train <-read.table('./UCI HAR Dataset/train/y_train.txt')
subject_train <-read.table('./UCI HAR Dataset/train/subject_train.txt')

activity_labels <- read.table("./UCI HAR Dataset/activity_labels.txt") # table mapping activity id to activity names

features <- read.table("./UCI HAR Dataset/features.txt") #list of colnames for the dataset
```

#### 1.b merges the two datasets and adds the column names

```r
x_data <- rbind(x_test, x_train)
colnames(x_data) <- features[,2]

y_data <- rbind(y_test, y_train)
colnames(y_data) <- 'Activity'

subject_data <- rbind(subject_test, subject_train)
colnames(subject_data) <- 'Subject'
```



### 2. Extracts only the measurements on the mean and standard deviation for each measurement

#### 2.a Selects the columns with '-mean()' or '-std()' in the variable's name, based on the description in 'features_info.txt'

```r
ms_cols <- grep("-mean\\(\\)|-std\\(\\)", features[, 2])
x_data_ms <- x_data[, ms_cols]
```

### 3. Uses descriptive activity names to name the activities in the data set

#### 3.a adds the two additional columns Activity and Subject to the data frame

```r
x_data_ms <- cbind(x_data_ms, subject_data, y_data)

### 3.b change the activity labels to lowercase and swap the numeric id in the data frame with the descriptive labels
activity_labels[,2] = gsub("_", "", tolower(as.character(activity_labels[, 2])))

### we can use activity_labels' row index instead of activity_labels$V1 because they concide
x_data_ms[,'Activity'] <- activity_labels[x_data_ms[,'Activity'], 2]
```

### 4. Appropriately labels the data set with descriptive activity names
i.e. appropriately labels the data set with descriptive variable names.  
we follow the tidy data guidelines, thus using descriptive names, no spaces, no dash etc. 

```r
vlabels <- colnames(x_data_ms)

# tidy labels
vlabels <- gsub('^t','Time',vlabels)
vlabels <- gsub('^f','Freq',vlabels)
vlabels <- gsub('Acc','Acceleration',vlabels)
vlabels <- gsub('Mag','Magnitude',vlabels)
vlabels <- gsub('Gyro','Gyroscopic',vlabels)
vlabels <- gsub('BodyBody','Body',vlabels)
vlabels <- gsub('\\(\\)','', vlabels)
vlabels <- gsub('-','', vlabels)
vlabels <- gsub('mean','Mean', vlabels)
vlabels <- gsub('std','StDev', vlabels)
colnames(x_data_ms) <- vlabels
```
### 5. Creates a second, independent tidy data set with the average of each variable f or each activity and each subject
The data set is saved in the working directory, in the 'tidy_data_set.txt' file.

```r
suppressWarnings(x_data_avg <- aggregate(x_data_ms, by = list(Activity = x_data_ms$Activity, Subject=x_data_ms$Subject), FUN = "mean"))
# drop last two columns
x_data_avg <- x_data_avg[,-ncol(x_data_avg)]
x_data_avg <- x_data_avg[,-ncol(x_data_avg)]

write.table(x_data_avg, 'tidy_data_set.txt', sep = "\t", row.names = FALSE)
```
End of README
