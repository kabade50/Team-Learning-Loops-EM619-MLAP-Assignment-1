# Team-Learning-Loops-EM619-MLAP-Assignment-1
#Task 1 : Exploratory Data Analysis (EDA) [6 marks]
Question_1:Plot the waveform for one sample data from each activity class. Are you able to see any difference/similarities between the activities? You can plot a subplot having 6 columns to show differences/similarities between the activities. Do you think the model will be able to classify the activities based on the data?
Answer:Observations: Differences & Similarities

Differences

WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS: Show higher acceleration variations in all three axes.More peaks and fluctuations, indicating movement.
SITTING, STANDING, LAYING: Show low or almost no variation in acceleration.Flat signals → Minimal movement.

Similarities

STANDING and SITTING: Almost identical low acceleration changes.Hard to distinguish using acceleration alone.
WALKING_UPSTAIRS vs. WALKING_DOWNSTAIRS: Both have similar fluctuations, but DOWNSTAIRS shows higher peaks (stronger force due to gravity).

→Can a Model Classify These Activities?

Yes, but with some challenges!
The data clearly differentiates dynamic (WALKING) and static (SITTING) activities.However, some activities overlap (e.g., STANDING vs. SITTING).
A good classification model (e.g., Random Forest, LSTM) would need:
More features (e.g., gyroscope readings, FFT transformations).
Feature engineering (e.g., computing jerk, energy levels).
A sequence model (LSTM/RNN) to capture time dependencies

