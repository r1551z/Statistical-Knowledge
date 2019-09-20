
# Intro
This is a summary of using other methods, including random forest and neural network and deep learning methods to analyze survival data
with censoring existing.

# Background
Traditional methods of dealing with censored survival data include AFT (accelerated failure time model) and Cox PH (proportional hazard)
method. While they use reasonable method to resolve the censoring issue, they are limited by the form of linear regression. With today's
increasing usage of enormous data, we would like to see how the nn / dl method can be combined with traditional survival analysis.

Below are some methods we are interested in.

# Non dl related:

## logistic regressors
http://www.cs.cornell.edu/~cnyu/papers/nips11_survival.pdf
(Learning Patient-Specific Cancer Survival Distributions as a Sequence of Dependent Regressors 2011)
It proposed a multi-task logistic regression (MTLR) method to estimate p(T>t_j|X) at each given time point; the time point could be 1-60 month, 1-10 year, etc. Method force the logistic regressors to be dependent. It targets the accuracy of predicted time.

## Randome survival forest
https://arxiv.org/pdf/0811.1645.pdf 
(randome survival forest 2008)
Python implementation can be found here https://pypi.org/project/random-survival-forest/.

Notice that the prediction is the author defined motality.

## SVM
http://www.gatsby.ucl.ac.uk/~chuwei/paper/ccls-07-03.pdf
(A Support Vector Approach to Censored Targets,
2007)
This paper used a modified svm (SVCR) as the loss function instead of a tradtitional parametric likelihood function. The thing is that
it performs very well on the loss it is trained on, but not so on other losses.

## Adversarial time to event
http://people.ee.duke.edu/~lcarin/Ash_ICML18.pdf
(Adversarial Time-to-Event Modeling, 2018)
Deep learning approach leveraging adversarial learning (GAN, generative adversarial network); forcus more on the time to 
event distribution rather than ordering.

related tensorflow code can be found here in https://github.com/paidamoyo/adversarial_time_to_event
.


# DL related
## DeepSurv 
https://arxiv.org/abs/1606.00931 
(2017)
This is a combination of Cox PH model and deep learning. The implementation can be found https://github.com/jaredleekatzman/DeepSurv (with Theano),  https://github.com/alexhallam/TensorFlow-Survival-Analysis/blob/master/deepsurv_tf.py and https://github.com/liupei101/TFDeepSurv (with tensorflow).

This method according to the author, focus more on the risk score and effectiveness for patients recommendation systems.

## RNN & AFT
http://mucmd.org/CameraReadySubmissions/37%5CCameraReadySubmission%5CPFS_TTRNN_AFT_CameraReady.pdf
(Modeling Progression Free Survival in Breast Cancer with Tensorized Recurrent Neural Networks and Accelerated Failure Time Models , 2017)
An rnn is built to deal with the high dimensionl & sparse sequential clinical data and to extract a latent representation from the entire patient history. An AFT model is then built on top on it to predict the survival time. 

In the paper, both the rnn models and the aft models are trained with mean squared logarithmic eror and use mean absolute error for metrics. The last latent state of the rnn model (a vector) is chosen as an imput of the AFT model.

No censoring methodology is specifically mentioned in the paper.

An idea: we can also combine the deepsurv result with the AFT model to resolve the issue of too much feature processing time required by
traditional linear regression.

## RNN surv
http://medianetlab.ee.ucla.edu/papers/RNN_SURV.pdf
(RNN-SURV: a Deep Recurrent Model for
Survival Analysis 2018)
"At each time step, the network takes as input the features characterizing the patient
and the identifier of the time step, creates an embedding, and outputs
the value of the survival function in that time step".

The rnn structure is as follows: maximum observed time is sliced into K intervals; then at each enpoint, inputs are the patients'
characteristic features (meaning they are the same at each time point) and the time interval identifier k (1 - K). The inputs will be firstly put through embedding layers, to create more meaningful representation, then through 2 lstm to create \hat{y} at each time point.
Each \hat{y} at the previous time point will be used to calculate the next \hat{y} due to the structure of rnn. A final output risk
score is a weighted average of the k \hat{y}s.

## RNN weibull AFT
https://ragulpr.github.io/assets/draft_master_thesis_martinsson_egil_wtte_rnn_2016.pdf 
(WTTE-RNN : Weibull Time To Event, Recurrent Neural Network, 2016, a master thesis).
Corresponding implementation can be found here https://github.com/ragulpr/wtte-rnn
(a keras implementation) and here https://github.com/ragulpr/wtte-rnn 
(installation is here https://github.com/ragulpr/wtte-rnn/blob/master/python/README.md
).
A simpler illustration of the idea can be fund here https://github.com/daynebatten/keras-wtte-rnn

