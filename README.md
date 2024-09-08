#Assignment 1 ML
# Problem 1 - Preprocessing the Data
### 1a)
We start by loading the SpotifyFeatures.csv file using the Pandas library. From this, we extract the relevant features and the corresponding data. The total number of samples and features in the dataset are determined by the size of the resulting arrays.

### 1b)
Next, we filter the dataset to only include songs that belong to either the "Pop" or "Classical" genres. These filtered songs are stored in filtered_data, and we assign labels: 1 for Pop and 0 for Classical. To determine how many songs belong to each genre, we simply count the number of rows where the label is 1 (Pop) and 0 (Classical).

### 1c)
For the classification task, we will focus on two features: liveness and loudness. These features are extracted into a matrix X, where each row represents a song, and the columns represent the respective feature values. The target labels (y) will contain the corresponding genre classifications. To divide the dataset, we use an 80% training and 20% test split, ensuring that the class distribution remains consistent across both sets. Additionally, we shuffle the data to ensure that songs are presented in a random order during training.

### 1d)
[Bonus]
We can create a scatter plot where songs are plotted based on their liveness and loudness values, with different colors representing Pop and Classical songs. Upon visual inspection, we can see that there is some overlap between the genres, especially in regions of high loudness and low liveness, which may pose challenges for classification.

# Problem 2 - Logistic Regression Model
### 2a)
Logistic regression relies on the sigmoid function, which outputs a value between 0 and 1, with 0.5 acting as the threshold between the two classes. To implement logistic regression, we begin by initializing the weights and bias to zero. Using stochastic gradient descent, we iteratively update these parameters to minimize the error. The update rules for the weights and bias are:

w = w - α * dw

b = b - α * db

Here, α is the learning rate, and the gradients dw and db are computed based on the prediction error (ŷ - y). During training, we monitor the error using the cross-entropy loss function and update the model parameters over several epochs.

To find the best learning rate, we experiment with different values and evaluate the accuracy on the training data. After comparing the results, we find that a learning rate of 0.005 yields the highest accuracy, around 92.56%. This optimal learning rate allows us to effectively train the logistic regression model and produce reliable predictions.

### 2b)
Once the model is trained, we test it on the remaining 20% of the data (the test set) to evaluate its accuracy in predicting the genre of new songs.

### 2c) 
[Bonus] (Did not manage to make it work)
Using the learned parameters, we can visualize the classification boundary between Pop and Classical songs on the liveness vs loudness plot, helping us understand how well the model distinguishes between the two genres.

# Problem 3 
### 3a)
To further evaluate the model’s performance, we use the test set results to generate a confusion matrix. This matrix provides a detailed breakdown of how many songs were correctly and incorrectly classified for each genre.

### 3c)
[Bonus]
A Classical song that a Pop fan might enjoy could be one that was misclassified by the model as Pop. This suggests that the song shares characteristics with Pop music, even though it technically belongs to the Classical genre.
