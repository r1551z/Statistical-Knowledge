
# Intro
This is a summary of using neural network and deep learning methods to analyze survival data with censoring existing.

# Background
Traditional methods of dealing with censored survival data include AFT (accelerated failure time model) and Cox PH (proportional hazard)
method. While they use reasonable method to resolve the censoring issue, they are limited by the form of linear regression. With today's
increasing usage of enormous data, we would like to see how the nn / dl method can be combined with traditional survival analysis.

Below are some methods we are interested in.

# DeepSurv 
https://arxiv.org/abs/1606.00931 (2017)
This is a combination of Cox PH model and deep learning. The implementation can be found https://github.com/jaredleekatzman/DeepSurv (with Theano),  https://github.com/alexhallam/TensorFlow-Survival-Analysis/blob/master/deepsurv_tf.py and https://github.com/liupei101/TFDeepSurv (with tensorflow).

This method according to the author, focus more on the risk score and effectiveness for patients recommendation systems.

# RNN & AFT
http://mucmd.org/CameraReadySubmissions/37%5CCameraReadySubmission%5CPFS_TTRNN_AFT_CameraReady.pdf (2017)
An rnn is built to deal with the high dimensionl & sparse sequential 

An idea: we can also combine the deepsurv result with the AFT model to resolve the issue of too much feature processing time required by
traditional linear regression.

