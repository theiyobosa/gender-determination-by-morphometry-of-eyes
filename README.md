<h1>Gender Determination by Morphometry of Eyes</h1>

<h2>Scope</h2>

This repository contains my solution to the <a href="https://dphi.tech/challenges/gender-determination-by-morphometry-of-eyes/144/overview/about">Gender Determination by Morphometry of Eyes</a> by <a href="https://dphi.tech">DPhi</a>. This challenge was part of Deep Learning Bootcamp. A deep learning model was required to determine gender by Morphometry of eyes.

<h2>Problem Statement</h2>

The anthropometric analysis of the human face is an essential study for performing craniofacial plastic and reconstructive surgeries. Facial anthropometrics are affected by various factors such as age, gender, ethnicity, socioeconomic status, environment, and region.  

Plastic surgeons who undertake the repair and reconstruction of facial deformities find the anatomical dimensions of the facial structures useful for their surgeries. These dimensions are a result of the Physical or Facial appearance of an individual. Along with factors like culture, personality, ethnic background, age; eye appearance and symmetry contributes majorly to the facial appearance or aesthetics. 

Our objective is to build a model to scan the image of an eye of a patient and find if the gender of the patient is male or female.

<h2>Data</h2>

The dataset contains eye pictures of males and females. The dataset can be downloaded from <a href="https://drive.google.com/file/d/1f7uslI-ZHidriQFZR966_aILjlkgDN76/view?usp=sharing">here</a>, although the dataset is already included in this repository as a zip file as <b>eye_gender_data</b>.

After the data is unzipped, it contains:

<b>train</b> - contains all the images that are to be used for training your model.

<b>Training_set.csv</b> - this csv file has contains the labels for the training images

<b>test</b> - contains 9000+ images. For these images you are required to make predictions

<b>Testing_set.csv</b> - this is the order of the predictions for each image that is to be submitted on the platform. Make sure the predictions you submit are with their image’s filename in the same order as given in this file.

<b>sample_submission.csv</b> - this is the sample submission file for the data sprint.

<h2>Modelling</h2>

The images were resized to have equal dimensions, data augmentation was performed on the image dataset. The image was then split in five folds, for a five fold cross validation before training. A deep neural network was used for training.

The model was trained in a Google Colab environment, with Tensorflow. Due to the limitation caused by the limited amount of RAM, the model had to be trained in a special way. I'll explain.

After each fold of the dataset was trained, the model had to be saved, and then the runtime had to be restarted. Then the model is loaded back into the environment, and then training is continued on the next data fold. This was repeated until the model was trained on all the folds.

<h2>Aftermath</h2>

After training, the model had a validation accuracy of <b>97 percent</b>. The test dataset with which the datathon was graded on, had an accuracy of <b>94 percent</b>. The test dataset prediction file that was submitted for grading is presented here as <b>submission_fold5.csv</b>. While the <b>model_kfold_fold5.h5</b> file is the trained Tensorflow model. 

The leaderboard for the challenge can be found <a href="https://dphi.tech/challenges/gender-determination-by-morphometry-of-eyes/144/leaderboard/datathon/">here</a>, my name there is "<b>theiyobosa</b>", same as my GitHub name.