# ECG HEARTBEAT CATEGORIZATION
ECG or ELECTROCARDIOGRAM is a test to record the activity of the heart via
electrical signals and can be reliably used to measure the imbalance in the CardioVascular  System.
The main problem with ECG analysis by a human is detecting and categorizing different waveforms and structures in the signal.
Manual Analysis is both extensive time consuming and prone to errors. It should also be kept in mind that Detection of Heart abnormality 
should be highly accurate and consistent because these consume a total of 1/3rd of total death in the world.  
The main focus of this report is in the categorizing five different arrhythmias in accordance with the AAMI EC57 standard by using deep learning  Architecture. 
I used  the  standardized  terminology to allow application of ECG diagnoses across many different hospital systems and countries.


## DATASET
The Dataset used to train the model for correctly classifying arrhythmia is the MIT-BIH Arrhythmia Dataset . 
The MIT-BIH dataset consists of ECG recordings from 47 different subjects recorded at the sampling rate of 125Hz.Each beat is annotated by at least two cardiologists. We use annotations in this dataset to create five different beat cate-gories in accordance with Association for the Advancementof Medical Instrumentation (AAMI) EC57 standard. 
After doing some visual Analysis of data we underlined a huge imbalance in data with Class 0 covering almost 90% of total Data.
I used resampling Technique to create a balance in the dataset and to make our predictor more generalized towards each class.
The Dataset contains around 100000 Samples of data verified from at least two cardiologists which is equally divided among the 5 classes to maintain balance .

## ARCHITECTURE
The design comprises a sequential CNN architecture with an input shape (187,1).
The first layer is a  Convolutional layer followed by BatchNormalization layer and MaxPooling Layer.
Same sequence of layer Arrangement is repeated thrice with different filter size. The main significance of these layers is Feature Extraction . 
The resulting shape  came out after these layer is (23,64). Then we flatten the data into a 1-d array and merge it with a DNN network having a hidden layer 
with 512 units. The output layer is activated with a softmax function with 5 units for 5 classes. 
The Output matrix gives the probability for each class and the class with highest probability is our prediction value.
## RESULTS
I evaluated the arrhythmia classifier on  20000 images that the Model hadn't seen before and got a satisfactory result
with an accuracy of 97.01  which is competitive to state of the art result.the confusion matrix when the test set is applied to the classifier
and we can clearly infer that the model is able to predict correctly and distinguish classes differently.The Accuracy vs Epochs graph also shows 
that the model runs smoothly without much zigzags thus showing that the learning rate and optimizer choosed is optimum .
There is no case of overfitting too as the train accuracy is very near to validation accuracy.
## CONCLUSIOIN
In this experiment  we have presented a method for ECG heartbeat classification ,specifically we have trained a deep convolutional neural network
for the arrhythmia classification task . According to the results we got , we can suggest that the model performs satisfactory and is comparable 
with the state-of-the-arts result. We have also seen visual representation of model performance and can suggest that the model can perform equally well 
with other Heart Diagnosis Problems such as Myocardial infarction .

