<h1 align="center">
  <img src="https://img.shields.io/badge/Fashion--MNIST--Image--Classification-FF6B6B?style=for-the-badge&logo=tensorflow&logoColor=white" alt="Fashion MNIST Classification"/>
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Deep_Learning-orange?style=flat-square" alt="Deep Learning"/>
  <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white" alt="TensorFlow"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
</p>

---

### 🔗 **Google Colab Link:**
[![Open In Colab](https://img.shields.io/badge/Open_in_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)](https://colab.research.google.com/drive/1kVbucp8P05WFTKDppJ6tES50ozcLyyII?usp=sharing)

---

## 📋 Questions:

### ![1](https://img.shields.io/badge/1-4A90E2?style=flat) What is the Fashion MNIST dataset?

The Fashion MNIST dataset serves as a widely used benchmark collection in machine learning which contains 70,000 grayscale images of fashion products across 10 categories. Each image has dimensions of 28×28 pixels. The research team from Zalando designed this dataset to serve as a more difficult test for contemporary machine learning systems which needed a better evaluation method than the original MNIST handwritten digit dataset. The 10 categories are: T-shirt/top, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag, and Ankle boot. The dataset serves as a common evaluation tool for classification algorithms because it presents more difficulties than digit recognition yet remains within the limits of practical computational power.

### ![2](https://img.shields.io/badge/2-4A90E2?style=flat) Why do we normalize image pixel values before training?

We normalize image pixel values (dividing by 255.0 in your code: train_images = train_images / 255.0) for several important reasons. First, the process of normalization establishes equal measurement standards by converting all input features to a shared value range between 0 and 1 which helps the optimization algorithm achieve faster and more dependable results. The training process experiences numerical stability problems when pixel values exist in a range from 0 to 255 because this unnormalized data creates extreme value differences between pixels. Second, it helps prevent certain features from dominating others simply because they have larger numerical values. Third, normalized data usually produces better generalization results which enhance the overall performance of the neural network. The process of normalizing image data to [0, 1] becomes easy because pixel values exist within the 0-255 range.

### ![3](https://img.shields.io/badge/3-4A90E2?style=flat) List the layers used in the neural network and their functions.

Your neural network architecture consists of three layers:

**Flatten Layer** - The Flatten layer of the neural network uses the layers.Flatten function which converts 2D input images that have dimensions of 28x28 pixels into single-dimensional arrays that contain 784 elements. The system uses this method to change image data into a format which can be used by fully connected dense layers. The system uses the shape transformation process to convert dimensions from (28, 28) into (784,) dimensions.

**Dense Hidden Layer** - The Dense Hidden Layer of the neural network uses the layers.Dense function to create a fully connected layer which contains 128 neurons that operate with ReLU (Rectified Linear Unit) activation. The system uses weighted connections to learn patterns and features from the input data. The ReLU function from the system uses its equation max(0, x) to create non-linear activation which enables the network to acquire complex pattern recognition abilities. The system has 100,480 trainable parameters which represent all the connections that exist between 784 inputs and 128 neurons.

**Dense Output Layer** - The Dense Output Layer of the system uses the layers.Dense function to produce output scores which function as logits for all 10 fashion categories. The system generates basic predictions which will undergo softmax transformation to create probability outputs. The system operates without an activation function because it uses logits together with from_logits=True in the loss function. The system has 1,290 trainable parameters which represent all the connections that exist between 128 hidden neurons and 10 outputs.

### ![4](https://img.shields.io/badge/4-4A90E2?style=flat) What does an epoch mean in model training?

The training of the model requires one complete period to process all training data. The Fashion MNIST dataset contains 60,000 training images which the model examines during each epoch. The training process uses smaller image batches instead of working with all images together which uses 32 images as the standard batch size. The training process requires 1,875 steps in each epoch because the model needs to process 60,000 training images using a batch size of 32 (60,000 ÷ 32). The code entry epochs=10 establishes 10 training cycles which permit the model to update its weights and biases through multiple iterations until it reaches the best performance. The model requires multiple training cycles because a single training cycle lacks the capacity to teach it complex pattern recognition.

### ![5](https://img.shields.io/badge/5-4A90E2?style=flat) Compare the predicted label and actual label for the first test image.

Your code results show the following output:

**Predicted label:** 0 (which denotes the T-shirt/top category)

**Actual label:** 9 (which corresponds to Ankle boot)

The model prediction shows complete failure because it identified a different clothing category. The results display poor performance because the output shows test accuracy of 11.8% which exceeds random guessing accuracy of 10% for 10 classes. The training accuracy reached 90% but test accuracy showed major decline because of two factors: extreme overfitting and defects in the prediction process. Your code uses probability_model = keras.Sequential([layers.Softmax()]) to build a prediction model that lacks essential trained model components which leads to random predictions despite the presence of good training results.

### ![6](https://img.shields.io/badge/6-4A90E2?style=flat) What could be done to improve the model's accuracy?

The system requires complete system enhancements to reach an accuracy level of 11.8 percent. The first critical step is fixing the prediction pipeline by including trained layers in the probability model. The next step requires regularization to be implemented through Dropout(0.3) which will follow dense layers and L2 regularization which will apply to all dense layers to prevent overfitting. The architecture requires additional hidden layers which should contain 256 or 512 neurons to achieve better learning abilities.

The training process needs optimization through two methods which include implementing validation during training and setting the learning rate to 0.0005 and increasing training time while monitoring validation loss to stop overfitting. Data augmentation through rotations and shifts creates artificial dataset expansion for Fashion MNIST even though it presents difficulties. The implementation of EarlyStopping through callbacks will control training management because it automatically stops when progress ceases while it adjusts the learning rate.

---

<p align="center">Made with ❤️ for Deep Learning</p>
