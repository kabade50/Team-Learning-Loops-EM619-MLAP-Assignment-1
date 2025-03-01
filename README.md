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

→Observing the Differences Between Static and Dynamic Activities

Static Activities (Laying, Sitting, Standing)

These activities involve very little to no movement.
Their acceleration values (acc²) remain nearly constant over time.
The acc² values are low, showing minimal variations.


Dynamic Activities (Walking, Walking Upstairs, Walking Downstairs)

These activities involve continuous motion.
The acceleration fluctuates significantly, creating noticeable peaks and variations.
The acc² values are much higher due to movement.


→Justification: Do We Need Machine Learning?

Case 1: Differentiating Static vs. Dynamic Activities (NO ML Needed)

If we only need to separate static from dynamic activities, we do not need ML.
A simple threshold on acc² can easily classify them:
If acc² is below a certain value, classify as static.
If acc² is above a certain value, classify as dynamic.
A basic rule-based approach (e.g., if acc² > threshold) would work.


Case 2: Differentiating Between Similar Activities (ML Needed)

Standing vs. Sitting vs. Laying → Difficult to separate with just acc² because their values are close.
Walking vs. Walking Upstairs vs. Walking Downstairs → These have similar fluctuations in acceleration.
Here, a machine learning model would be useful to learn subtle differences
