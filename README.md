My first neural network! [This notebook](/index.ipynb) is the result of my following along with [Build your first Neural Network to predict house prices with Keras](https://medium.com/intuitive-deep-learning/build-your-first-neural-network-to-predict-house-prices-with-keras-eb5db60232c) by Joseph Lee Wei En. In it, I used a home value dataset adapted from [a Zillow competition](https://www.kaggle.com/c/zillow-prize-1/data) to build three different models to predict whether a house price is above or below median value.

I started processing the data by splitting the dataset between input features, `X` (of which there were 10), and the feature I wanted to predict, `Y` (a binary 0 or 1 indicating if the house price was above the median). I then scaled the input features so each ranged between 0 and 1, and finally split my resulting `X` and `Y` into a training set (70% of the data), a validation set (15% of the data), and a test set (15% of the data).

My first model used a neural network with two hidden layers of 32 neurons each. I trained it over 100 epochs and optimized it with stochastic gradient descent. Plotting the model loss and accuracy for both the training and validation sets afterward, I could see that the metrics for both sets stayed fairly in sync over the course of the training, indicating that overfitting wasn't too big a concern. Model loss settled around 30% and accuracy around 85–90% by the end.

The second model's network had four hidden layers of 1,000 neurons each and used Adam optimization. I trained it over 100 epochs again, but this time, the validation set's results varied wildly from the training set's, meaning the model was badly overfit.

To introduce regularization, the third model was identical to the second except for the addition of L2 regularization to each layer and dropout to each hidden layer. This reduced overfit substantially, with model loss settling around 40–45% and accuracy around 85–90%.

The question most on my mind now: is there a rule of thumb for determining what size of neural network, length of training, and optimization method are most appropriate based on the size and shape of one's data? Or does it still take a lot of trial and error? The much simpler structure of my first model brought loss down to 30% without discernable overfit, but the far more complex third model, after correcting overfit with regularization, couldn't bring loss below 40%. Also, should I be more concerned about reducing loss or increasing accuracy?

Onward to more learning! ✊🏼
