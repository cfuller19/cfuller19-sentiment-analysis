# Sentiment Analysis of Amazon, ImDB, and Yelp Reviews

<b> In this project, I used 3000 reviews from Amazon, ImDB, and Yelp to build a neural network model using natural language processing techniques. This model could predict a customer's opinion as either positive or negative.</b></br>

<b> Data Preparation Process</b><br>
1. Each dataset was concatenated together into one pandas dataframe.
2. Data were examined for the presence of null values.
3. Data were examined to ensure there were approximately equal numbers of positive and negative sentiments for training the model.
4. Non-alpha characters were identified and removed.
5. The data were cleaned to convert all letters to lowercase, remove stop words, and lemmatize text.
6. Data were explored to identify the vocabulary length, embedding length, and maximum review length.
7. Data were split into training (75%) and testing (25%) sets.
8. The training and testing sets were prepared for sentiment analysis: training sentences were tokenized, training and testing sentences were converted to sequences, sequences were padded to the maximum review length, training and testing sets were converted to numpy arrays, and training and testing sets were one_hot encoded.
<br>
<b> Network Architecture of Final Model</b><br>
<img width="600" alt="image" src="https://github.com/cfuller19/cfuller19-sentiment-analysis/assets/101231073/ca33d828-9b55-40c4-9427-92d63f06fe0d"><br>
A description of each layer is given below:<br>
- 1st layer: Embedding; turns positive indexes into dense, fixed size vectors.
- 2nd layer: GlobalAveragePooling1D; pooling layer for temporal data.
- 3rd layer: Dense; contains the connected "neurons" in the neural network. Each neuron (node) takes input from the previous layer.
- 4th layer: Dropout; randomly sets inputs to 0 to help prevent overfitting.
- 5th layer: Dense; contains the connected "neurons" in the neural network. Each neuron (node) takes input from the previous layer.

<br>
An explanation of the hyperparameters used in this model is given below. <br>
<img width="800" alt="image" src="https://github.com/cfuller19/cfuller19-sentiment-analysis/assets/101231073/3acd6d60-ecbb-4e0e-8202-faa895e90000"><br>

<b> Model Evaluation </b><br>
The final model had a predictive accuracy of ~80%.<br>
A plot of accuracy vs epoch for the training and validation data is shown below.<br>
<img width="500" alt="image" src="https://github.com/cfuller19/cfuller19-sentiment-analysis/assets/101231073/8271e694-cfd6-455b-8939-89cee886b7a7"><br>
As seen in the plot, accuracy on the training and validation data sets stopped improving around epoch 35. The training accuracy and validation accuracy are relatively close, at ~85% and ~80%, respectively.<br>
A plot of loss vs epoch for the training and validation data is shown below.<br>
<img width="500" alt="image" src="https://github.com/cfuller19/cfuller19-sentiment-analysis/assets/101231073/6a0e43ca-3cb8-471c-9cc3-c45c9349d578"><br>
As seen in the plot, loss decreased through the 35 epochs, with the validation loss leveling out. The validation loss is greater than the training loss, indicating the model has potential overfitting issues.




