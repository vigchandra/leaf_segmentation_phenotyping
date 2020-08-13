# Leaf Segmentation Phenotyping

## [Smart Agriculture](https://github.com/vigchandra/leaf_segmentation_phenotyping/blob/master/final.pdf) project report

## Summary

Using state-of-the-art object detection and image segmentation techniques we are able to infer the yield on different plant experiments. We demonstrate and produce an effective proof of concept computer vision model employing transfer learning that is capable of accurate predictions on a variety of Tomato and Basil plant species across 4 different experimental datasets. Finally, we visualize our yield predictions and results in an interactive dashboard combining the predictions with the operational experiment data (sensor data), showing the accuracy of the predictions and providing a solid base for future work.


![](https://github.com/vigchandra/leaf_segmentation_phenotyping/blob/master/dash.png)


In the domain of Smart Agriculture, I developed a computer vision model to support farming needs in Alberta and Latin America for a Calgary based client. 
## Data collection: 
The data can be broadly categorized into two types – images and sensor information. The images were of tomato and basil plants in an experimental container which were captured every 20 mins and the sensor information (water, light and temperature info.) which was recorded every 7 mins. Challenges: blurred, missing, overlapping leaves, 2D data, varied lighting conditions and overgrown images of plants, missing and ‘blip’ sensor information. The data was stored on Microsoft Azure in blobs.
## Data preprocessing: 
Brought all the image and sensor variables to a common time format. Split the data into training and validation datasets. Identified images which were worth training. Annotated and augmented images to make the training set richer since annotation was an expensive task. Extracted images from the internet to train the initial model on.
## Model building: 
Built a model using state of the art mask-R-CNN model using pytorch (detectron2 from Facebook AI Research) to predict the leaf area and number of leaves per image. The huge dataset needed GPUs for processing and was trained on Machine Learning Studio, Microsoft Azure. Specifically focused on the tasks of object detection and image segmentation since we were not only interested in knowing if a specific image had a leaf, but also how different it was from an adjacent leaf. The model was trained initially with just images taken off the internet. At the second level, we trained it again on the specific leaves which were annotated. 
## Quality metrics: 
As part of the metrics, we developed the mean average precision for the specific plant phenotyping model. It was important to know the F1 score based out of (Jaccard’s index / dice scores) for different thresholds and dice scores. Mean average precision accounted for both the object detection and image segmentation needs. The AP50 improved from 65.2 to 87.0 by using reinforcement learning at multiple stages.


