### South Park Classification

In the series South Park, there are many different characters, and you want to find out if it is possible to identify which character is speaking based on the text. Since there are many characters in South Park, you decide to focus on Kyle and Cartman.

### Task

1. **Read the first 10,000 lines of the file `SouthPark.csv`.**
2. **Filter the table so that only the lines from Kyle and Cartman remain.**
3. **Use the column `Line` and add another column `Character`, which is 1 if the text is from Cartman and 0 if it is from Kyle.**
4. **Split the data into training and test datasets (optionally also validation data).**
5. **Calculate a one-hot encoding for all words in the respective lines.**
6. **Remember to remove punctuation beforehand.**
7. **Perform a classification with a CNN and the one-hot encoded lines. Limit the sentences to a maximum length of 20 words and pad the shorter sentences by filling the remaining entries with 0.**
8. **Visualize accuracy and loss per epoch.**
9. **Visualize the model's predictions in a confusion matrix.**
10. **Find out which words are the most important in the first kernel (index 0) or cause the greatest activation.**

   **Tip:** To access the kernels in PyTorch, you can use `kernels=model.conv1.weight.detach().clone()`, where `model` is your model and `conv1` is the first convolution layer. To access the activations of the conv layer with Keras in your CNN, you can define a function with `keras.backend.function([model.input], [model.layers[0].output])`, where `model` is your CNN. Pass your training data to this function and access the output of the first training example with index 0.

Use the following parameters for your CNN:

- Number of kernels: 128
- Kernel size (window size): 5
- Batch size: 10
- Epochs: 10
