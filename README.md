# **GSoc TRIP Test**

## Introduction

The TRIP test is a code for analyzing driving behavior based on 1) A .dat file with raw simulator data; and 2) An MP4 file with video synchronized with the .dat file. 

The folder contains 

1. shape_predictor_68_face_landmarks.dat, used for training to analyze facial movements; 
2.  Experimenter_9110002_53.mp4;
3.  Experimenter_9110002_53.dat; 
4. TRIP.ipynb, which is a notebook for analyzing driving behavior.
5. A folder containing some pictures, in which information worthy of the driver's attention in the driving environment has been annotated.



The following are evaluation tasks to be addressed:

1. How risky the driver is;
2. How risky the simulated driving environment is;
3. How attentive the driver is;
4. How drowsy the driver is.
5. outline or annotate all objects in the simulated driving environment that may pose a safety risk to the driver and/or warrant the driver’s attention.


This notebook runs through Colab.

## Methodology

Considering that in the first two tasks, the driver's behavior and driving environment are constantly changing, and the risk implied by the data recorded in each frame is also changing, summarizing all the data would miss information within certain periods. Therefore, it is necessary to conduct a risk assessment for the data of each frame separately.

For the third and fourth tasks, since the driver's condition remains largely unchanged, this solution will summarize the data from all data frames to obtain a final result.

For the first and second tasks, since the .dat file does not have labels for training, if a machine learning approach were to be used, it would be considered an unsupervised learning problem. However, I believe that clustering cannot accurately represent the level of risk, so I plan to use a rule-based analysis method. This involves scoring the level of risk based on the data in the .dat file, utilizing formulas and driving knowledge. For the third and fourth tasks, I plan to use computer vision algorithms to analyze the driver's facial features to obtain results.



## Future work

In addition to the features I used in the notebook, I noticed behaviors in the .mp4 file, such as the driver holding the steering wheel with one hand and scratching their head, which can also increase risk. Furthermore, I observed noteworthy objects in the simulated driving environment, such as sudden obstacles and traffic lights, whose states can affect the final results. Therefore, future work involves researching more precise computer vision algorithms to analyze these behaviors and objects to increase the accuracy of predictions.
