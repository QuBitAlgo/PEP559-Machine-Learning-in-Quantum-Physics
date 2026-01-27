# Homework #1

### Question 1: Visualizing the Iris Dataset in 3D
- Modify the demo code to generate a 3D scatter plot of the Iris dataset using any three feature variables. Ensure that you properly label the axes to indicate the corresponding features. Use different colors to differentiate between the three flower classes(Iris-setosa, Iris-versicolor, and Iris-virginica). Add a legend to indicate class labels.
- Based on the 3D scatter plot, discuss whether all three classes appear to be linearly separable in this space.
- Do you think a perceptron model would be able to classify any two of the classes correctly?
- Test your hypothesis by modifying the demo code and training the perceptron model. Specifically, try to classify the data with labels(Iris-versicolor and Iris-virginica)

### Question 2: Adaline learning dynamics
- Using the first 100 rows of the Iris dataset to test the demo codes with the Adaline learning rule.
- For a given number of iterations, e.g., 200, plot the MSE loss function as a function of learning rate $\eta$.
- Identify a critical $\eta$, beyond which the loss function does not converge.
- For the adaptive learning rate, $\eta=c_1/(N + c_2)$ where $N=200$ is the number of iterations, create a 2D heatmap to show the loss function (after 200 iterations) as a function of $c_1$ and $c_2#. If 200 is not a good number, try a different one.

## NOTE:
- You do not need to submit your code and results. At the beginning of the next class, students will be randomly selected to talk about one of these two questions. Your grade for this assignment will be determined by the clarity of your presentation and your response to some questions from me and the audience. For the other students, you will receive an A for this HW if not selected.

- If you find some of the questions do not make sense, just try to solve them based on your understanding and discuss the issue next time.
