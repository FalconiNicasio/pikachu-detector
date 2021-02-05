# pikachu-detector

This project was part of my Independent Study at Indiana University during my Master's program in Data Science. The goal of this was to learn the inner workings of object detection at a deeper level in order to understand all the moving parts it takes to build an object detector from scratch. Please see the notebook for more in-depth look at the work.

## Summary

Object detection is a classic Computer Vision problem and one of the more efficient ways to solve it is through Single Shot Detectors (SSD). The goal of this notebook is to build an SSD using a Fully Convolutional Network (FCN). This is mainly a learning exercise to understand the inner workings of an SSD network by building it from scratch using PyTorch (and MXNet). The dataset used is about 1000 images of Pikachu with bounding boxes and was found [here](https://cv.gluon.ai/build/examples_detection/finetune_detection.html) on this tutorial that uses MXNet for transfer learning. This notebook differs from that because it’s not using a pretrained network, rather it shows a custom network architecture built from scratch. Results show that even a small SSD, limited data, and a short training time of under 3-4 minutes (on GPU), it can still detect objects and draw bounding boxes with a confidence percentage of 0.64 and higher.

## Discussion

What was interesting about this project was seeing the network learn bounding box regions. Since this architechture has an hierarchical nature to it that has a 1 to 1 ratio feature map, it first identifies all the objects in a single bounding box then identifies them at larger feature maps.

## Recommendations

The next steps to take is to replace the base network of this architechture with a pretrained model like ResNet-50 to get more accuracte results. This should work due to the modularity of the network as the base network identifies the features of the object and the branches after that are used to search the image with a single pass at different resolutions. 
