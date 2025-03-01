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

