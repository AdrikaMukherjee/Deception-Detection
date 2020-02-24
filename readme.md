# Multimodal Deception Detection

Deception Detetion seemed to be a neglected problem. The reasons are mainly unavailibility of data. In this project, new data was curated and also existing datasets[1] dealing with
this problem was combined to prepare a master dataset. Deep Learning Approach was used to tackle the problem. Finally Machine Learning Techniques was employed to compare results from both Approach.
Different Modalities was explored to tackle the problem. Audio, Gaze and Micro-Expression Features was extracted using OpenSource Toolkits: OpenFace(https://cmusatyalab.github.io/openface) and OpenSmile(https://www.audeering.com/opensmile/). These modalities were combined for detecting deception. 
Initially the Deep Learning Approach was tried using the Audio Features, since maximum number of data points was available for this Modality. Finally Meta_Learning Approach was used to handle individual modalities due to scarcity of data. 
Different Modality Integration methods was adopted for both Deep Learning and Machine Learning Approaches



## Description of Folders and files

### Feature Extraction: Audio_FeatureExtraction.ipynb, Gaze_Microexpression_FeatureExtraction.ipynb

Audio_FeatureExtraction.ipynb file contains code used to extract Audio Features(mfcc, prosodic features using emobase.conf) using OpenSmile
Gaze_Microexpression_FeatureExtraction.ipynb file contains code used to extract Static Gaze and Facial Action(Micro-Expression) Features using OpenFace

### Multimodal_DL: Multimodal_deception_detection_DL.ipynb

Multimodal_deception_detection_DL.ipynb file combines different modalities (Audio+Gaze; Audio+Micro-Expression; Gaze+Micro-Expression, Audio+Micro-Expression+Gaze) using Deep Learning Approach

### Multimodal_ML: Multimodal_deception_detection_ML.ipynb

Multimodal_deception_detection_ML.ipynb file combines different modalities (Audio+Gaze; Audio+Micro-Expression; Gaze+Micro-Expression, Audio+Micro-Expression+Gaze) using Latefusion. Both Manual hyper-parameter tuning and Voting Classifier is used for combining the modalities.

### Unimodal_DL: Meta_Learning_Model-Audio.ipynb, Meta_Learning_Model-Gaze.ipynb, Meta_Learning_Model-Mexp.ipynb, Unimodal_Audio.ipynb

There was over 8000 datapoints for Audio, owing to the CSC Deceptive Speech dataset. Unimodal_Audio.ipynb handles the audio modality using Deep Learning. In order to compensate for the Lack of Data, Siamese network was used to make the model learn to differentiate between Deceptive and Truthful datapoints. Meta_Learning_Model-Audio, Meta_Learning_Model-Gaze.ipynb, Meta_Learning_Model-Mexp.ipynb, files contains code that handles Audio, Gaze and Mexp[2] Data individually

### Unimodal_ML: ML_models.ipynb

ML_models.ipynb file use Classical Machine Learning to tackle datapoints from individual modality

### Analysis: Analysis.ipynb

Analysis.ipynb file contains code that analyse the performance of initial and final model that contains only Audio Modality. best_model_new.h5 and best_model_old.h5 are used in the Analysis. best_model_new.h5, best_model_old.h5 are the models saved from Unimodal_Audio.ipynb file.
The individual performance of model from each Dataset is Analyzed. 
Distribution of Cosine Similarity in Deceptive and Truthful Data is plotted.


** [1] Datasets used are: 
Real Life Trial Dataset: https://web.eecs.umich.edu/~mihalcea/downloads.html#RealLifeDeception
Youtube: This dataset is created from The Tonight show starring Jimmy Fallon(https://www.nbc.com/the-tonight-show) and Odd Man out(https://www.youtube.com/watch?v=D6Nt0JFM3_A&list=PLBVNJo7nhINSmMs1NvedljBKMSutatOta)
CSC Deceptive Speech: This dataset contains only Speech data and hence could only be used in unimodal Analysis. https://catalog.ldc.upenn.edu/LDC2013S09 
Bag of Lies: http://openaccess.thecvf.com/content_CVPRW_2019/papers/CV-COPS/Gupta_Bag-Of-Lies_A_Multimodal_Dataset_for_Deception_Detection_CVPRW_2019_paper.pdf

Two Datasets(CSC and Bag of Lies) used in this Projects are not available publicly and can only be used in Academic Research.

** [2] Mexp stands for Micro-Expression



