In this [experiment](G_Facial_keypoint_detection.ipynb), I implemented a convolutional neural network to detect 68 keypoints on a face, based on the starting code, instructions, utility functions and training data from Udacity's [Computer Vision](https://www.udacity.com/course/computer-vision-nanodegree--nd891) nanodegree.

The training data provided by Udacity includes thousands of facial images that come with 68 keypoints for each face (for example, eyebrows, eyes, mouth, nose bridge and jaw).

This is a regression task, and the convolutional neural network outputs 68 x, y-coordinates that should be as close as possible to the 68 ground-truth keypoints. Thus, loss function is MSE loss function. 

I used a pre-trained EfficientNet model as feature extractor, and only trained the final layers of the network to compute the keypoint coordinates based on those features.

Here's an example of 68 keypoints on sample facial images:
![key_pts_example.png](key_pts_example.png)

# Results

Before training, the model output 68 x- and y- coordinates but they represent random points.

![pretraining_img1.png](pretraining_img1.png)

After 45 epochs, the 68 output keypoints closely resemble the ground-truth keypoints from Udacity's dataset.

![pretraining_img2.png](pretraining_img2.png)

![pretraining_img3.png](pretraining_img3.png)

The model can still predict keypoints when the eyes are closed.

![pretraining_img4.png](pretraining_img4.png)

![pretraining_img5.png](pretraining_img5.png)

On testing images, the predicted keypoints are also close to the ground-truth keypoints, like in the image below of Joey Tribbiani with his eyes closed.

![testing_img1.png](testing_img1.png)

![testing_img2.png](testing_img2.png)
