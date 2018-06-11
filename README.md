# Image-classification
Image classification with SIFT and Neural network
We roughly categorize the photos extracted from Instagram of Huangshan City, China into 5 categroies: Architecture, Cloud, Food, Pine, Hiking.Then, we manually label 100 images for each of the 5 categories, for a total of 500 images. With this set at hand, we randomly split the data with keeping 80% of the data as training data and 20% of data as testing data.
- The Architecture category includes the photos of ancient architecture, like ancient residential houses, memorial archways, shrines, bridges, and street;
- The Cloud category includes the photos of cloud, sunset, sunrise, and sky; 
- The Food category includes the photos of food, drinks, recipes;
- The Pine category includes the photos whose main object is pine tree; 
- The Hiking category includes the photos taken while people are hiking.

## SIFT + Bag-of-words + Kmeans + SVC
- First, we use the scale-invariant feature transform (SIFT) algorithm  to extract a set of key features for images in the dataset; The extracted key features are invariant to image translation, scaling, and rotation, as well as partial invariant to illumination changes and robustness to geometric distortions. Then, k-means clustering algorithm is used to cluster the extracted key feature vectors, which provides a set of codewords to form the dictionary of our bag-of-words (BOW) representation. Next, for the extracted SIFT features of an image, we assign each feature to the closest BOW, which allows us to express the image as a histogram of BOW. 
- Finally, we train the corresponding histograms of labelled images with Support Vector Machine (SVM) algorithm, to get the SVM image classifier. For the unlabeled images, we classify the BOW presentations with the SVM image classifier. The output is a vector of probability classified to each category and the category with maximum probability is the label of the unlabeled image. 


## Convolutional Neural Network
