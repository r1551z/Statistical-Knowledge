
# Intro
This is a summary of using other methods, including random forest and neural network and deep learning methods to analyze survival data
with censoring existing.

# Background
Traditional methods of dealing with censored survival data include AFT (accelerated failure time model) and Cox PH (proportional hazard)
method. While they use reasonable method to resolve the censoring issue, they are limited by the form of linear regression. With today's
increasing usage of enormous data, we would like to see how the nn / dl method can be combined with traditional survival analysis.

Below are some methods we are interested in.

# Randome survival forest
https://arxiv.org/pdf/0811.1645.pdf (randome survival forest 2008)
Python implementation can be found here https://pypi.org/project/random-survival-forest/.

Notice that the prediction is the author defined motality.


# DeepSurv 
https://arxiv.org/abs/1606.00931 (2017)
This is a combination of Cox PH model and deep learning. The implementation can be found https://github.com/jaredleekatzman/DeepSurv (with Theano),  https://github.com/alexhallam/TensorFlow-Survival-Analysis/blob/master/deepsurv_tf.py and https://github.com/liupei101/TFDeepSurv (with tensorflow).

This method according to the author, focus more on the risk score and effectiveness for patients recommendation systems.

# RNN & AFT
http://mucmd.org/CameraReadySubmissions/37%5CCameraReadySubmission%5CPFS_TTRNN_AFT_CameraReady.pdf (Modeling Progression Free Survival in Breast Cancer with Tensorized Recurrent Neural Networks and Accelerated Failure Time Models , 2017)
An rnn is built to deal with the high dimensionl & sparse sequential clinical data and to extract a latent representation from the entire patient history. An AFT model is then built on top on it to predict the survival time. 

In the paper, the target is time t, the 

An idea: we can also combine the deepsurv result with the AFT model to resolve the issue of too much feature processing time required by
traditional linear regression.

# RNN surve
http://medianetlab.ee.ucla.edu/papers/RNN_SURV.pdf(RNN-SURV: a Deep Recurrent Model for
Survival Analysis 2018)
"At each time step, the network takes as input the features characterizing the patient
and the identifier of the time step, creates an embedding, and outputs
the value of the survival function in that time step".
