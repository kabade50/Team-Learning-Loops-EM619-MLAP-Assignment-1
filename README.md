# Team-Learning-Loops-EM619-MLAP-Assignment-1
#Task 1 : Exploratory Data Analysis (EDA)

Question_1:Plot the waveform for one sample data from each activity class. Are you able to see any difference/similarities between the activities? You can plot a subplot having 6 columns to show differences/similarities between the activities. Do you think the model will be able to classify the activities based on the data?

Answer:

-->Observations: Differences & Similarities

1.Differences

a)WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS: Show higher acceleration variations in all three axes.More peaks and fluctuations, indicating movement.

b)SITTING, STANDING, LAYING: Show low or almost no variation in acceleration.Flat signals → Minimal movement.

2.Similarities

a)STANDING and SITTING: Almost identical low acceleration changes.Hard to distinguish using acceleration alone.

b)WALKING_UPSTAIRS vs. WALKING_DOWNSTAIRS: Both have similar fluctuations, but DOWNSTAIRS shows higher peaks (stronger force due to gravity).

-->Can a Model Classify These Activities?

1.The data clearly differentiates dynamic (WALKING) and static (SITTING) activities.However, some activities overlap (e.g., STANDING vs. SITTING).


2.A good classification model (e.g., Random Forest, LSTM) would need:

a)More features (e.g., gyroscope readings, FFT transformations).

b)Feature engineering (e.g., computing jerk, energy levels).

c)A sequence model (LSTM/RNN) to capture time dependencies

Question_2:Do you think we need a machine learning model to differentiate between static activities (laying, sitting, standing) and dynamic activities(walking, walking_downstairs, walking_upstairs)? Look at the linear acceleration $(acc_x^2+acc_y^2+acc_z^2)$ for each activity and justify your answer.

Answer:

To determine whether we need a machine learning (ML) model to differentiate static and dynamic activities, let’s analyze the squared linear acceleration:

acc^2 = acc_x^2 + acc_y^2 + acc_z^2

-->Observing the Differences Between Static and Dynamic Activities

Static Activities (Laying, Sitting, Standing)

a)These activities involve very little to no movement.
b)Their acceleration values (acc²) remain nearly constant over time.
c)The acc² values are low, showing minimal variations.


-->Dynamic Activities (Walking, Walking Upstairs, Walking Downstairs)

a)These activities involve continuous motion.
b)The acceleration fluctuates significantly, creating noticeable peaks and variations.
c)The acc² values are much higher due to movement.


→Justification: Do We Need Machine Learning?

Case 1: Differentiating Static vs. Dynamic Activities (NO ML Needed)

a)If we only need to separate static from dynamic activities, we do not need ML.
b)A simple threshold on acc² can easily classify them:
c)If acc² is below a certain value, classify as static.
c)If acc² is above a certain value, classify as dynamic.
A basic rule-based approach (e.g., if acc² > threshold) would work.


Case 2: Differentiating Between Similar Activities (ML Needed)

a)Standing vs. Sitting vs. Laying → Difficult to separate with just acc² because their values are close.
b)Walking vs. Walking Upstairs vs. Walking Downstairs → These have similar fluctuations in acceleration.
c)Here, a machine learning model would be useful to learn subtle differences



*Question 3:*

1.Visualize the data using PCA. [2 marks]
Use PCA (Principal Component Analysis) on Total Acceleration $(acc_x^2+acc_y^2+acc_z^2)$ to compress the acceleration timeseries into two features and plot a scatter plot to visualize different class of activities.

2.Next, use TSFEL (a featurizer library) to create features (your choice which ones you feel are useful) and then perform PCA to obtain two features. Plot a scatter plot to visualize different class of activities.

3.Now use the features provided by the dataset and perform PCA to obtain two features. Plot a scatter plot to visualize different class of activities.

4.Compare the results of PCA on Total Acceleration, TSFEL and the dataset features. Which method do you think is better for visualizing the data?

Answer:
1.PCA on acc²:
The plot displays two distinct clusters: one corresponding to static activities (laying, sitting, standing) and another to dynamic activities (walking, walking_downstairs, walking_upstairs).

2.PCA on TSFEL Features:
TSFEL features capture nuanced patterns in the data, allowing for differentiation among all activities, including those with subtle differences like walking_upstairs vs. walking_downstairs.

3.PCA on the Entire Dataset:
Incorporating all features enhances the model's ability to distinguish between activities. The comprehensive feature set captures both the intensity and the unique characteristics of each activity, leading to clear separations in the PCA plot.

Conclusion: The distinct clustering in the PCA plots suggests that a machine learning model trained on these features would effectively classify the activities.

