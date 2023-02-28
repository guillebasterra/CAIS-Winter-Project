# CAIS-Winter-Project

Guillermo Basterra
basterra@usc.edu

For my winter project, I chose the Muffin vs Chihuahua computer vision problem. I decided on this project because I did natural language processing (Sentiment analysis on tweets) for my end of semester project and so I wanted to try transfer learning for computer vision instead.
For the model, I followed much of what is described in the Lesson 4 transfer learning model from CAIS curriculum as well as the PyTorch “Transfer Learning for Computer Vision” tutorial. This involved a couple of steps. 

First, I imported the dataset into Google Colab from Kaggle as it was - I did not need to expand the dataset since I would be using transfer learning and thus knew the model would be able to generalize well even from a small dataset set. However, in order to do transfer learning and use ResNet18 (pre-trained model trained on the ImageNet dataset with 18 layers) I did need to process the data slightly. ResNet expects images of shape (3 x H x W), where H and W are expected to be at least 224, and I needed to load the images into a range of [0, 1] and then normalize them using mean = [0.485, 0.456, 0.406] and std = [0.229, 0.224, 0.225].

After processing the data, I defined my model architecture. Then, I loaded ResNet into the colab notebook and adjusted it so that its output would be 2 (to differentiate between chihuahuas and muffins). I then chose my loss function (Cross entropy loss for classification), optimizer (Stochastic gradient descent), and learning rate (to help the model converge). Like this, I was able to train the model across 24 epochs and ended up with an accuracy of 99.6. At first, I was worried the model had overfit, but I think the problem is just easy enough that it can predict with such high accuracy. 




