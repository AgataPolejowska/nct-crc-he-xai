# nct-crc-he-xai
XAI methods for a neural network classifier trained on NCT Biobank images.

<img width="594" alt="image" src="https://user-images.githubusercontent.com/44722312/236639903-f30fa476-f59f-490e-ae0d-1cb1d5a978e1.png">
<img width="457" alt="image" src="https://user-images.githubusercontent.com/44722312/236639967-576ac9ad-4c17-445b-973a-4ae9a7e33089.png">


### Purpose

The purpose of this project is to develop understanding of evaluation methods and decision visualization techniques for a convolutional neural network classifier. The analysis of impact of pixels, groups of pixels, and regions of the image on the classification decision is performed. The analysis is performed on a neural network classifier trained on the NCT Biobank dataset.


### Data

The datasets consists of histological images of human colorectal cancer and healthy tissue, can be accessed here: https://zenodo.org/record/1214456

Tissue classes are:
1. ADI: Adipose
2. BACK: Background
3. DEB: Debris
4. LYM: Lymphocytes
5. MUC: Mucus
6. MUS: Smooth muscle
7. NORM: Normal colon mucosa
8. STR: Cancer-associated stroma
9. TUM: Adenocarcinoma epithelium

Article that shows visualization of classifier decision for this dataset using DeepDream: https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1002730


### Methods

1. Feature Visualization

Feature visualization is performed for 10 parts from different depth of the neural network (from conv and dense).

It is an optimization problem. The goal is to find an image that maximizes the activation of a particular filter. It is assumed that the weights of neural network are fixed. 

2. Saliency maps visualization

Using Vanilla Gradient, DeconvNet or Guided Backpropagation.

The gradient network prediction is calculated in refrence to input data, with fixed weights of the neural network. It shows which elements of input data need the slightest change to change the prediction of the neural network.

3. CAM images visualization

Using Grad-CAM and Guided Grad-CAM.

Class Activation Mapping creates heat maps that show regions characteristic of a class.


### Classifier

The requirements:
- CNN based
- accuracy on training set > 0.8

The classifier tested in this project is based on the ResNet50 architecture.