# Pixel-Importance-Image-Classification
An exploration of the predictive importance of individual pixels in a deep convolutional neural network using SHAP values. Neural Network architecture inspired by VGG16. Image classification on the Intel Scene Classification dataset available at https://www.kaggle.com/nitishabharathi/scene-classification. 

Since their inception, the complexity, interconnectedness, and semi-random nature of neural networks have led to their treatment as "black boxes" -- models in which the "meaning" of their inner workings is incomprehensible and undefinable. Black boxes are instead to be viewed as tools that can have their parameters (settings) tuned and their output/performance measured, but not as interpretable models that describe the behavior of their inputs and targets. The SHAP package seeks to change all that: https://github.com/slundberg/shap.

The following graph shows the SHAP values of 20 validation images linked to 200 training images through the trained CNN model using the SHAP package's DeepExplainer. Each row indicates a validation image, the true color version of which is printed on the extreme left. Each column indicates a possible class to predict for the image displayed to the extreme left (classes in order: buildings, forest, glacier, mountain, sea, street). Very simply, red pixels are encouraging the model to predict that class, and blue pixels are discouraging the model from predicting that class. Feel free to click on the plot and view it with a black background to easier spot the important pixels.

There are some curious insights to be gained just by looking at the pixel patterns. Flat horizons seem to be telltale signs of seascapes. Small gaps of sky between trees seem to be indicating forest scenes.

![alt text](https://github.com/michaelznidarsic/Pixel-Importance-Image-Classification/blob/master/SHAP%20OUTPUT1.png?raw=true)

The model's architecture is a simplified derivation of VGG16. Dropout and L2 normalization are applied on the fully connected layers.

![alt text](https://github.com/michaelznidarsic/Pixel-Importance-Image-Classification/blob/master/SHAP%20ARCHITECTURE1.png?raw=true)

The confusion matrix of the model's validation predictions shows that buildings/streets and glaciers/mountains are the most confused pairs of classes. This is fairly intuitive. The observed validation accuracy of this iteration was 85.97%.

![alt text](https://github.com/michaelznidarsic/Pixel-Importance-Image-Classification/blob/master/SHAP%20CM1.png?raw=true)

