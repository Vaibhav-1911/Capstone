# Capstone
## Detecting Emergency Situations Using Audio Data

### Dataset
#### Sources: The audio data samples for this project have been collected from online sources such as “Zapslat.com”, “Pixabay.com,” and “Directory. Audio”. 
#### Description: The dataset consists of 220 total samples equally divided between two classes namely, “Emergency Sounds” and “General Sounds”.
#### In addition we have also collected 14 total audio samples equally divided between the two classes for testing the model performance. These have been separately stored unseen by the model to prevent overfitting.

#### Link to Audio data used for this project:
https://drive.google.com/drive/folders/1mLddgEDZZs3u9CkbrwEUvf6X63UHo9pN?usp=sharing

### Business Problem
#### - Training a neural network model to identify instances of emergency using live audio.
##### - We aim to develop a system that can accurately detect emergency situations using audio data, with the goal of contributing to more effective early warning systems and improving emergency response times.

### EDA Findings

#### Identifying ways to differentiate between emergency and non-emergency audio signals

#### Zero Crossing Rate:

##### Looking at the zero crossing rate of audio samples brought us to the conclusion that it is not an ideal measure for differentiating between Emergency and Non-Emergency sounds. There is no pattern that identifies exclusive rates of sign change between emergency and non-emergency audio.

#### Mel Spectrograms:

##### By looking at the Mel Spectograms above we could see that there is a pattern in the color scale for most emergency audios and they always leave a fainting trail where the decibals (In our case the color scale we see) keep reducing over time. This is a great differentiating factor between Emergency and Non-Emergency audios as non-emergency audios produce either very low decibal sound or they don't leave a fainting trail. These images of mel spectrograms could be great for feeding into a deep learning model for differentiating emergency audios from non-emergency audios

### Results
#### Before Data Augmentation

##### Classification Report
![Classification Report Before Data Augmentation](https://github.com/Vaibhav-1911/Capstone/blob/main/Results/Images/Results_Before_DataAugmentation.png?raw=true)

##### Before data augmentation, from the above classification report, it may seem that we have a good recall score and the model is successful, but in reality the model ended up identifying each audio in the test set as an emergency audio, essentially leading to the above classification report with a recall score of 100%. It is the same as blindly classifying every passed audio file as emergency audio, which is undesirable.

#### After Data Augmentation

##### Classification Report
![Classification Report After Data Augmentation](https://github.com/Vaibhav-1911/Capstone/blob/main/Results/Images/Results_After_DataAugmentation.png?raw=true)

##### As we can see above, we achieved an accuracy score of 71% and recall scores of 71% for True Positive instances after data augmentation. Also we have much better accuracy and recall scores for general audio class.

##### Confusion Matrix
![Confusion Matrix After Data Augmentation](https://github.com/Vaibhav-1911/Capstone/blob/main/Results/Images/Results_After_DataAugmentation2.png?raw=true)

##### The confusion matrix above depicts the number of True Positive, True Negatives, False Positives, and False Negatives. Out of 7 audio samples for each class, we were able to correctly identify 5 samples.
