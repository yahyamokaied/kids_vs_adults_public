# Kids vs. Adults Public
## Python and AI-based Classification: Distinguishing Between Children and Adults


[![GitHub stars](https://img.shields.io/github/stars/yahyamokaied/kids_vs_adults_public.svg?style=social&label=Star)](https://github.com/yahyamokaied/kids_vs_adults_public)
[![GitHub YahyaMokaied](https://img.shields.io/github/followers/yahyamokaied?label=follow&style=social)](https://github.com/yahyamokaied)

Welcome to the Kids vs. Adults Public repository! This repository contains information about the Kids vs. Adults Game, a machine learning project that aims to differentiate between images of kids and adults.

## Project Overview

The goal of this project is to use machine learning techniques to differentiate between images of kids and adults. Two different models were used for this classification task: a MobileNet model and a custom Convolutional Neural Network (CNN) model.

## Accessing the Full Project

If you're interested in accessing the full project, including the complete code, dataset, and detailed documentation, you can request access by clicking the button below:

[![Request Access](button.png)](https://your-request-page.com)

By clicking the "Request Access" button, you will be redirected to a page where you can submit your request to access the full project. Please provide a brief explanation of why you are interested in accessing the project.

Please note that access to the full project is subject to approval by the repository owner. Once your request is reviewed and approved, you will receive further instructions on how to access the complete project.

## Project Overview
The goal of this project is to use machine learning techniques to differentiate between images of kids and adults. I used two different models for this classification task, a MobileNet model and a custom Convolutional Neural Network (CNN) model.

## Testing and Results...
The two models used here, a Convolutional Neural Network (CNN) and MobileNet, yielded different results when classifying images into 'Adult' or 'Kid' categories. While both models accurately classified adults, they struggled with images of children.

The CNN incorrectly identified all child images as 'Adult'. On the other hand, MobileNet managed to correctly classify one child image ("5-kid-boy.JPG") but misclassified the others.

The variation in results could be attributed to the distinct architectures of the two models. MobileNet, which is designed to be lighter and more efficient, managed to capture some features in the images that helped in correct classification of one child image, which the CNN failed to do.

However, given that they were both trained and tested on the same data, and they both misclassified several child images, it seems that there may be a bias in the data or the features extracted by the models are not sufficient for distinguishing between adults and children consistently. It might be helpful to revisit the data, examine feature extraction, and consider model tuning to improve results.
### Testing with CNN...
1/1 [==============================] - 0s 48ms/step
CNN_Predicted class for 9-adult-old-man.jpg: Adult
1/1 [==============================] - 0s 14ms/step
CNN_Predicted class for 2-adult-man.jpg: Adult
1/1 [==============================] - 0s 15ms/step
CNN_Predicted class for 1-adult-man.jpg: Adult
1/1 [==============================] - 0s 14ms/step
CNN_Predicted class for 5-kid-boy.JPG: Adult
1/1 [==============================] - 0s 14ms/step
CNN_Predicted class for 3-adult-girl.jpg: Adult
1/1 [==============================] - 0s 14ms/step
CNN_Predicted class for 8-kid-girl.JPG: Adult
1/1 [==============================] - 0s 14ms/step
CNN_Predicted class for 4-adult-girl.jpg: Adult
1/1 [==============================] - 0s 13ms/step
CNN_Predicted class for 7-kid-boy.JPG: Adult
1/1 [==============================] - 0s 14ms/step
CNN_Predicted class for 6-kid-girl.jpg: Adult

### Testing with MobileNet...
1/1 [==============================] - 0s 377ms/step
Mobilenet Predicted class for 9-adult-old-man.jpg: Adult
1/1 [==============================] - 0s 23ms/step
Mobilenet Predicted class for 2-adult-man.jpg: Adult
1/1 [==============================] - 0s 22ms/step
Mobilenet Predicted class for 1-adult-man.jpg: Adult
1/1 [==============================] - 0s 22ms/step
Mobilenet Predicted class for 5-kid-boy.JPG: Kid
1/1 [==============================] - 0s 22ms/step
Mobilenet Predicted class for 3-adult-girl.jpg: Adult
1/1 [==============================] - 0s 21ms/step
Mobilenet Predicted class for 8-kid-girl.JPG: Adult
1/1 [==============================] - 0s 23ms/step
Mobilenet Predicted class for 4-adult-girl.jpg: Adult
1/1 [==============================] - 0s 21ms/step
Mobilenet Predicted class for 7-kid-boy.JPG: Adult
1/1 [==============================] - 0s 21ms/step
Mobilenet Predicted class for 6-kid-girl.jpg: Adult

## Project Structure:
.
├── dataset
│   ├── train
│   │   ├── kids
│   │   ├── adults
│   ├── validation
│   │   ├── kids
│   │   ├── adults
│   ├── test
│   │   ├── kids
│   │   ├── adults
│   ├── resized
│   │   ├── train
│   │   │   ├── kids
│   │   │   ├── adults
│   │   ├── validation
│   │   │   ├── kids
│   │   │   ├── adults
├── models
│   ├── mobilenet
│   ├── custom_cnn
├── requirements.txt
├── train_custom_cnn.py
├── train_mobilenet.py
├── test_custom_cnn.py
├── test_mobilenet.py

## Data
The images of kids and adults are collected from open sources website called 'www.kaggle.com' following the necessary legal and ethical guidelines & GDPR.
These images are then used to train both models.

## Data Preparation
Data preparation involves using the OpenCV library to crop faces from the images and resize them to a common size of 224x224 pixels. This allows the models to focus on the most important parts of the images, the faces.

## Models
I used two models in this project:

1. **MobileNet Model:** A pretrained MobileNetV3 model is used as the base model with additional custom layers added to the end. This model is efficient and effective for mobile and embedded vision applications.
2. **Custom CNN Model:** A custom-built Convolutional Neural Network (CNN) model is also used for this classification task.

## How to Use

To use this project, follow the steps below:

1. **Prepare dataset:** 
   - Place training images in the following directories:
      - Kids: `dataset/train/kids`
      - Adults: `dataset/train/adults`
   - Place validation images in the following directories:
      - Kids: `dataset/validation/kids`
      - Adults: `dataset/validation/adults`

2. **Create a virtual environment:** 
    Navigate to the project directory and run the following command: 
    ```bash
    python3 -m venv kids_vs_adults_env
    ```

3. **Activate Python virtual environment:** 
    Run the command: 
    ```bash
    source kids_vs_adults_env/bin/activate
    ```

4. **Install necessary packages:** 
    Run the command: 
    ```bash
    pip install -r requirements.txt
    ```

5. **Interact with the program via a simple command-line interface:** 
    Run the following command: 
    ```bash
    python menu.py
    ```

## Command Options

Choose from the following options in the command-line interface:

1. Crop and resize train_data kids' images
2. Crop and resize train_data adults' images
3. Crop and resize validation_data kids' images
4. Crop and resize validation_data adults' images
5. Crop and resize all images
6. Train MobileNet
7. Train Custom CNN
8. Train all models
9. Test MobileNet
10. Test Custom CNN
11. Test all models
12. Compare results
13. Export MobileNet to TFLite
14. Export Custom CNN to TFLite
15. Exit

Choose the appropriate option and follow the prompts to execute the task.

## Evaluation
After the models are trained, they are tested on unseen data. The performance of the models is evaluated based on their accuracy, precision, recall, and F1-score. The results from each model are compared to identify the most effective model.

## Documentation
Each step of the process, from data collection and preparation to model design and training, is documented in detail. Additionally, code samples and instructions on how to use the models to classify new images are provided. All this information can be found in this README file.

