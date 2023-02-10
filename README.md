# Semi-Supervised-on-CIFAR-100-dataset

My project on the CIFAR 100 dataset using two semi-supervised algorithms

1. Self Training
2. Co-Training


I have not implemented the algorithm completely because of limited time on GPUs, as it was taking a lot of time to predict all the values of the unlabeled dataset. I have taken a part of the unlabeled dataset in each iteration. Also I did not run the algorithm until the unlabeled dataset becomes empty due to the same reasons as above. However I have written the ideal code in the notebook and the user has to just uncomment the part of the code to run the complete algorithm. (Please change the variable name of len(X_unlabeled) in the for loop and before the for loop while uncommenting.

I have used two architectures-

1. VGG
2. VGG with Squeeze Excitation layers


Link to my VGG notebook - https://www.kaggle.com/code/harshrachalwar/vgg-semi-supervised/notebook

Link to my VGG with Squeeze Excitation layers - https://www.kaggle.com/code/harshrachalwar/squeeze-excitation/notebook

I have implemented the above two using self training algorithm.

Link to my Co-Training notebook - https://www.kaggle.com/code/harshrachalwar/co-training/notebook

I have used the above two architectures as the two classifiers in this algorithm.

## Self training algorithm

We train the classifier for some epochs. Then we predict each value in the unlabeled dataset. If we get the probability of a prediction above a threshold(confidence) level we appen the correspoding image with the predicted class and append to the labeled dataset. We keep doing this until certain iterations or till unlabeled dataset becomes empty.

Algo for CIFAR-100:
    If I get a confidence level above 0.95 I append the correspoding X unlabeled value to labeled dataset by using np.append(X_labeled,x,axis=0) where x is X_unlabeled[j:j+1](I did this to get the shape right) and append the converted y predicted so that the index corresponding to the maximum probabilty is made 1 and others 0 (1 means it is the class label for the given x). I append this updated y(given as array in the code) by appending [array](again due to shape compatibilty). I continue this process repeatedly. I also drop the corresponding x from the unlabeled dataset.

## Co training algorithm

We train two classifiers for some epochs. Then we predict for unlabeled data for each classifier. We take the maximum of the max probabilities of the two predictions. If it exceeds the threshold value we append the data with the correspoding predicted class. And almost similar method for appending to the labeled dataset. I drop the corresponding x from the unlabeled dataset.
