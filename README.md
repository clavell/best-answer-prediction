# Question and Answer Forum Best Answer Prediction

On question and answer forums there is often the feature for askers to choose a best answer for their question. This information can be used in classification tasks for predicting which answer will be chosen as the best. Alternatively, it could provide suggestions for best answer for threads where one wasn't chosen or even for all threads in entire forums that do not provide the "best answer" feature.
According to a survey of literature, often good characteristics of good answers are:
- More varied vocabulary
- Answers referenced by other answers
- More comments from other users
- Earlier posted answers are likely to be better
- Answer most different from the rest
- Answer length

This work begins with some of the simpler suggested features mentioned above. 
- Answer length, obtained by counting words in raw answer
- relative time of posting, obtained by comparing date information from answer and question 
- comment count 

Using Neural Network with Tensorflow and random search hyperparameter tuning with cross validation the following outcome was attained:
Best model: 
- 94 neurons per layer, 2 hidden layers
- Training accuracy: 0.756
- Validation accuracy: 0.753
- Classification report for test data:

<img width="500" alt="Classification report" src="https://user-images.githubusercontent.com/12875280/163461568-aeae3b3d-cccf-49a6-8d9b-a15c058bec1a.png">

Next steps:
- change the data preprocessing functions into custom scikit-learn pipeline transformers to allow for generalization to other data
- include other features to improve accuracy

Data obtained from stack exchange diy (home improvement) forum data dump: https://archive.org/download/stackexchange/diy.stackexchange.com.7z
