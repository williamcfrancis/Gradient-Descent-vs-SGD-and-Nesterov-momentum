## Gradient Descent vs SGD and Nesterov momentum
An analysis study between the performance of Gradient Descent, Stochaistic Gradient Descent and Nesterov momentum for a logistic regression model on two classes of the MNIST dataset.

### Loss curves and observations
Plot of the training loss as a function of the number of parameter updates on a semi-log scale:
![image](https://user-images.githubusercontent.com/38180831/205387923-691bbd8d-2c17-47be-95f2-d1675ac9c65d.png)
The slope of the line from the plot is-0.0084

The following is the loss curve obtained for Gradient Descent with Nesterov Momentum:
![image](https://user-images.githubusercontent.com/38180831/205399395-9b949e9f-9f3b-4688-9dc7-25f9375483a8.png)
It can be observed that the slope for the plot obtained with Nesterov’s acceleration (=-0.0374) is better than the slope of the plot obtained without Nesterov’s acceleration (=-0.0102).

Plotting the training loss against the number of parameter updates on a semi-log scale for gradient descent with Nesterov’s updates, SGD without Nesterov’s acceleration, and SGD with Nesterov’s acceleration:
![image](https://user-images.githubusercontent.com/38180831/205399460-ceaf4617-1228-4389-8b96-95a1ab5a5d4c.png)

Convergence of (iii) SGD with Nesterov’s acceleration is faster than of (ii) SGD without Nesterov’s acceleration. The convergence curve of GD with Nesterov reduces the loss with the number of weight updates much faster than SGD without Nesterov. This is because Nesterov momentum adds inertia to the gradient descent which helps it to bounce out of local optima easily. We can also observe that the convergence curve for SGD is irregular and rugged as compared to the curve of GD with Nesterov which is smooth. This is because in SGD, the model updates the weights after seeing a batch size of 128 images at a time whereas, in GD, the model updates the weights after seeing the entire training set at least once. This increases the probability that the loss always decreases. When the weights are updated after looking at 128 images, the loss could also go up after a certain mini batch although it decreases in a general fashion.
