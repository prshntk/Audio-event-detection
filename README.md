# Audio-event-detection
AUDIO EVENT CLASSIFICATION                                                           
Task – To classify a given audio file among the 10 given classes of sound
> We have been given an audio file in .wav format. From each of the given audio file we extract a spectrogram and do 0 padding to make our Feature matrix of dimension 513x401. 
> For response y we build them in form of one-hot vectors for each corresponding .wav file
Approach -  
1.	We build CNN approach using Keras , The model uses Conv2D,Maxpooling,BatchNormalization,Dense,Dropout and Flatten layers. 
2.	Then we compile it using Adam optimizer and loss is Categorical CrossEntropy loss.
3.	We run the model for 16 epochs and take the mini-batch size to be 64.
Image
Inference – 
1.	The Model starts to over fit after a certain no. of epochs So we use RandomForest classifiers which are very prone to overfitting.
RANDOMFOREST CLASSIFIER – 
1.	The no. of estimators is taken to be 100 and maximum tree height is limited to 20.
We obtain the following Confusion matrix on My Test data using RandomForest classifier.






Confusion matrix -

Image

 AUDIO EVENT DETECTION AND CLASSIFICATION                                                       
Task – To detect and classify a given audio file among the 10 given classes of sound which may have more than one sounds
> We have randomly picked up a no. to denote how many files to concatenate and the randomly chosen that many files to concatenate. Finally this give a 513x2001 feature matrix for each input feature.
> The response matrix is a 5x10 matrix where each row denote if there is a sound and what kind of sound is that
Approach -  
1.	We build CRNN approach using Keras , The model first encodes the spectrogram using a CNN and then we attach a RNN layer to make it efficient for containing temporal information.
2.	After that we have attached a Time Distributed Dense layer to create the output vector of 5x10.
3.	Then we compile it using Adam optimizer and loss is Categorical Cross Entropy loss.
4.	We train it for 20 epochs with a batch size of 8.
