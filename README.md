# SSDAN
SSDAN: Multi-Source Semi-Supervised Domain Adaptation Network for Remote Sensing Scene Classification

paper: Lasloum, T.; Alhichri, H.; Bazi, Y.; Alajlan, N. SSDAN: Multi-Source Semi-Supervised Domain Adaptation Network for Remote Sensing Scene Classification. Remote Sens. 2021, 13, 3861. https://doi.org/10.3390/rs13193861


We present a new method for multi-source semi-supervised domain adaptation in remote sensing scene classification. The method consists of a pre-trained Convolutional Neural Network model, namely EfficientNet-B3, for the extraction of highly discriminative features, followed by a classification module that learns feature prototypes for each class. Then, the classification module computes a cosine distance between feature vectors of target data samples and the feature prototypes. Finally, the proposed method ends with a Softmax activation function that converts the distances into class probabilities. The feature prototypes are also divided by a temperature parameter to normalize and control the classification module. The whole model is trained on both the unlabeled and labelled target samples. It is trained to predict the correct classes utilizing the standard cross-entropy loss computed over the labelled source and target samples. At one and the same time, the model is trained to learn domain invariant features using another loss function based on entropy computed over the unlabeled target samples. Unlike the standard cross-entropy loss, the new entropy loss function is computed on the model's predicted probabilities and does not need the true labels. This entropy loss, called minimax loss, needs to be maximized with respect to the classification module to learn features that are domain invariant (hence removing the data shift), and at the same time, it should be minimized with respect to the CNN feature extractor to learn discriminative features that are clustered around the class prototypes (in other words reducing intra-class variance). To accomplish these maximization and minimization processes at the same time, we use an adversarial training approach, where we alternate between the two processes. The model combines the standard cross-entropy loss and the new minimax entropy loss and optimizes them jointly. The proposed method is tested on four RS scene datasets, namely UC Merced, AID, RESISC45, and PatternNet using two-source and three-source domain adaptation scenarios. The experimental results demonstrate the strong capability of the proposed method to achieve impressive performance despite using only a few (six in our case) labelled target samples per class. Its performance is already better than several state-of-the-art methods including RevGard, ADDA, Siamese-GAN, and MSCN. 

Running the code:

1) You need to download the datasets from here:  https://figshare.com/projects/SSDAN/123421
2) Put the them under the datasets/ folder. Each class of images should be in a seprate folder.
3) Check the text files under the folder datasets/our_datasets/ , they represent the sets: source set, labaled training target set, labeled validation target set, unlabeled target set.
4) Correct the list of image path&files (with class label) in each file. (write your own simple python code to accomlish that)

Good luck!

paper citation:
Lasloum, T.; Alhichri, H.; Bazi, Y.; Alajlan, N. SSDAN: Multi-Source Semi-Supervised Domain Adaptation Network for Remote Sensing Scene Classification. Remote Sens. 2021, 13, 3861. https://doi.org/10.3390/rs13193861
