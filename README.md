# Semi-Supervised-on-CIFAR-100-dataset

My project on the CIFAR 100 dataset using two semi-supervised algorithms

1. Self Training
2. Co-Training


I have not implemented the algorithm completely because of limited time on GPUs, as it was taking a lot of time to predict all the values of the unlabeled dataset. I have taken a part of the unlabeled dataset in each iteration. Also I did not run the algorithm until the unlabeled dataset becomes empty due to the same reasons as above. However I have written the ideal code in the notebook and the user has to just uncomment the part of the code to run the complete algorithm

I have used two architectures-

1. VGG
2. VGG with Squeeze Excitation layers


Link to my VGG notebook - "link"

Link to my VGG with Squeeze Excitation layers - "link"

I have implemented the above two using self training algorithm.

Link to my Co-Training notebook - "link"

I have used the above two architectures as the two classifiers in this algorithm.
