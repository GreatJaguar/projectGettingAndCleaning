projectGettingAndCleaning,
steps for creating run_analysis.R, to collect, work on, and clean a data set.

==================1====================== 

  *download the zip with files UCI HAR DATASET


==================2======================
 
  *Then we create our objects
  
  features <- features.txt : 561 rows, 2 columns
  gyroscope signals raw 3-axial tAcc-XYZ and tGyro-XYZ signals.
  
  activities <- activity_labels.txt : 6 rows, 2 columns
  the lists of metrics made at the time
    
  subject_test <- test/subject_test.txt : 2947 rows, 1 column
  test subject data 30/9
  
  x_test <- test/X_test.txt : 2947 rows, 561 columns
  contains recorded features test data
    
  y_test <- test/y_test.txt : 2947 rows, 1 columns
  activity tag code
    
  subject_train <- test/subject_train.txt : 7352 rows, 1 column
  contains train data of 21/30 volunteer 
    
  x_train <- test/X_train.txt : 7352 rows, 561 columns
  contains recorded features train data
  
  y_train <- test/y_train.txt : 7352 rows, 1 columns
  contains train data of activities’code labels


==================3======================
#data analysis

DATA1: (10299 rows, 561 columns) is created by merging x_train and x_test using rbind() function

DATA2 : (10299 rows, 1 column) is created by merging y_train and y_test using rbind() function

Subject : (10299 rows, 1 column) is created by merging subject_train and subject_test using rbind()

Merged_Data :(10299 rows, 563 column) is created by merging Subject, Y and X using cbind() function


==================4======================
extracts standard deviation and the mean of each measure

TidyData: (10299 rows, 88 columns) is created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement





==================5======================
name set activities

Entire numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable



==================6======================
properly label the data

code column in TidyData renamed into activities
All Acc in column’s name replaced by Accelerometer
All Gyro in column’s name replaced by Gyroscope
All BodyBody in column’s name replaced by Body
All Mag in column’s name replaced by Magnitude
All start with character f in column’s name replaced by Frequency
All start with character t in column’s name replaced by Time


==================7======================
create a new independent data set from step 4

FinalData:  (180 rows, 88 columns) 



