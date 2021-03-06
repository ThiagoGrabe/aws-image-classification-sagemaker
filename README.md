# Image Classification using AWS SageMaker

Use AWS Sagemaker to train a pretrained model that can perform image classification by using the Sagemaker profiling, debugger, hyperparameter tuning and other good ML engineering practices. This can be done on either the provided dog breed classication data set or one of your choice.

## Project Set Up and Installation
Enter AWS through the gateway in the course and open SageMaker Studio. 
Download the starter files.
Download/Make the dataset available. 

## Dataset
The problem we’re going to solve today is to train a model to classify ants and bees - Hymenoptera Pytorch Dataset. We have about 120 training images each for ants and bees. There are 75 validation images for each class. Usually, this is a very small dataset to generalize upon, if trained from scratch.

### Access
Upload the data to an S3 bucket through the AWS Gateway so that SageMaker has access to the data. 

## Hyperparameter Tuning
This project used the pretrained [Resnet18](https://pytorch.org/hub/pytorch_vision_resnet/) and a final fully connected layer to perform the final classification. Using the `best_estimator()` it is possible to achive the best hyperparameters configuration.

!['img/hyperparams.png'](hyperparams.png)

The best hyperparameters was:

!['img/Best.png'](Best.png)

## Debugging and Profiling

The Loss decreased smoothly indicating a good training. The Model itself performed well withou any issues and the metric was satisfying.

!['img/debugg.png'](debugg.png)

### Results

The model performed very well achieving 95.4% of accuracy

!['img/accuracy.png'](accuracy.png)


## Model Deployment
The model is deployed using the following endpoint:

!['img/endpoint.png'](endpoint.png)

I have developed a simple function to load the data using its path and performing the inference:

!['img/inference.png'](inference.png)
