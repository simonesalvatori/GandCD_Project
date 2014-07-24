# CodeBoook
The averages selected for this dataset come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (TimeBodyAccelerationXYZ and TimeGravityAccelerationXYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz.   
  
Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (TimeBodyAccelerationJerkXYZ and TimeBodyGyroscopicXYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (TimeBodyAccelerationMagnitude, TimeGravityAccelerationMagnitude, TimeBodyAccelerationJerkMagnitude, TimeBodyGyroscopicMagnitude, TimeBodyGyroscopicJerkMagnitude).  
  
Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing FreqBodyAccelerationXYZ, FreqBodyAccelerationJerkXYZ, FreqBodyGyroscopicXYZ, FreqBodyAccelerationJerkMagnitude, FreqBodyGyroscopicMagnitude, FreqBodyGyroscopicJerkMagnitude.  
  
These signals were used to estimate variables of the feature vector for each pattern:  
'XYZ' is used to denote 3-axial signals in the X, Y and Z directions.  
  
From the set of variables that were estimated from these signals we selected:  
 
Mean: Mean value  
StDev: Standard deviation  
  
TimeBodyAccelerationMeanX  
TimeBodyAccelerationMeanY  
TimeBodyAccelerationMeanZ  
TimeBodyAccelerationStDevX  
TimeBodyAccelerationStDevY  
TimeBodyAccelerationStDevZ  
TimeGravityAccelerationMeanX  
TimeGravityAccelerationMeanY  
TimeGravityAccelerationMeanZ  
TimeGravityAccelerationStDevX  
TimeGravityAccelerationStDevY  
TimeGravityAccelerationStDevZ  
TimeBodyAccelerationJerkMeanX  
TimeBodyAccelerationJerkMeanY  
TimeBodyAccelerationJerkMeanZ  
TimeBodyAccelerationJerkStDevX  
TimeBodyAccelerationJerkStDevY  
TimeBodyAccelerationJerkStDevZ  
TimeBodyGyroscopicMeanX  
TimeBodyGyroscopicMeanY  
TimeBodyGyroscopicMeanZ  
TimeBodyGyroscopicStDevX  
TimeBodyGyroscopicStDevY  
TimeBodyGyroscopicStDevZ  
TimeBodyGyroscopicJerkMeanX  
TimeBodyGyroscopicJerkMeanY  
TimeBodyGyroscopicJerkMeanZ  
TimeBodyGyroscopicJerkStDevX  
TimeBodyGyroscopicJerkStDevY  
TimeBodyGyroscopicJerkStDevZ  
TimeBodyAccelerationMagnitudeMean  
TimeBodyAccelerationMagnitudeStDev  
TimeGravityAccelerationMagnitudeMean  
TimeGravityAccelerationMagnitudeStDev  
TimeBodyAccelerationJerkMagnitudeMean  
TimeBodyAccelerationJerkMagnitudeStDev  
TimeBodyGyroscopicMagnitudeMean  
TimeBodyGyroscopicMagnitudeStDev  
TimeBodyGyroscopicJerkMagnitudeMean  
TimeBodyGyroscopicJerkMagnitudeStDev  
FreqBodyAccelerationMeanX  
FreqBodyAccelerationMeanY  
FreqBodyAccelerationMeanZ  
FreqBodyAccelerationStDevX  
FreqBodyAccelerationStDevY  
FreqBodyAccelerationStDevZ  
FreqBodyAccelerationJerkMeanX  
FreqBodyAccelerationJerkMeanY  
FreqBodyAccelerationJerkMeanZ   
FreqBodyAccelerationJerkStDevX  
FreqBodyAccelerationJerkStDevY  
FreqBodyAccelerationJerkStDevZ  
FreqBodyGyroscopicMeanX  
FreqBodyGyroscopicMeanY  
FreqBodyGyroscopicMeanZ  
FreqBodyGyroscopicStDevX  
FreqBodyGyroscopicStDevY  
FreqBodyGyroscopicStDevZ  
FreqBodyAccelerationMagnitudeMean  
FreqBodyAccelerationMagnitudeStDev  
FreqBodyAccelerationJerkMagnitudeMean  
FreqBodyAccelerationJerkMagnitudeStDev  
FreqBodyGyroscopicMagnitudeMean  
FreqBodyGyroscopicMagnitudeStDev  
FreqBodyGyroscopicJerkMagnitudeMean  
FreqBodyGyroscopicJerkMagnitudeStDev  
  


Then we created a tidy data set with the average of each variable for each activity and each subject.  
Activity  
Subject  
  
The activity names are the following:  
walking  
walkingupstairs  
walkingdownstairs  
sitting  
standing  
laying  
  
Subject's ID is a number between 1 and 30, for a total of 30 subjects.  
