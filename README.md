# Prodigy InfoTech Machine Learning Internship Task 4

## **Task Details**

Implement a support vector machine (SVM) to classify images of cats and dogs.

## **Implementation**

Using this [DATASET](https://www.kaggle.com/c/dogs-vs-cats/data).

This was my basic workflow:

-   Read image from dataset
-   Resize image to have consistent dimensions
-   Flatten image and add to my data array. (This is done because images are three dimensional while SVMs only accept 1 dimensional data)
-   Add corresponding label to label array
-   Split dataset and fit using `sklearn.svm.SVC`
-   Measure performance by running predictions on new data

### Parameter tuning

I ran a `GridSearchCV` in order to decide which pairs of values of `gamma` and `C` are the most optimum for my model.

### Dimensionality

One of the problems I faced was how long my model took to fit and I concluded that its because of how many features each image produced. Each image turns into an array of length 451200 which is **a lot** of 'features'. And so this leads to the model taking ages to train. However, reducing the number of features results in a loss of accuracy.
