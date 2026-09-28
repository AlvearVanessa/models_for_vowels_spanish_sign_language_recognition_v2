# models_for_vowels_spanish_sign_language_recognition_v2

![me](https://github.com/AlvearVanessa/models_for_vowels_spanish_sign_language_recognition/blob/main/Multimedia_vowelsLSE_example.gif)

In this work, we presented a sign recognition system for the vowels of the Spanish Sign Language (Lengua de Signos Española - LSE) in real time, based on hand detection and image classification, where each vowel is a class. The *vowelsLSE* dataset consists of 5 gestures of one person signing each vowel according to LSE and contains 3461 images. The *vowelsLSE_new_test* dataset has 197 images of five different people signing LSE vowels and was created to evaluate the models with different images rather than with training data from the same person. Both datasets consist of RGB images in JPG format with a size of 400 x 400 and have a white background to make them the same size. This dataset has been created as a proof of concept and is being worked on for improvement in future updates. This work was based on the Hand Sign Detection for the American Sign Language (ASL) course on the following website: https://www.computervision.zone/courses/hand-sign-detection-asl/

The repository includes:

    *inference\_images* folder contains images for making inferences once the classification models are trained.
    
    _integration_codes_ folder includes five Python scripts where the detection and classification models are merged to make the recognition of the vowels of the LSE:
    
      - DataCollection.py to collect and create the vowelsLSE dataset.          
      - HandTrackingModule_noSkeleton.py is the hand detection module and works with the Keras and FastAI libraries.            
      - classificationModule_init_fastai.py is the classification module for the vowels of LSE and works with the FastAI model.  
      - cuttingHand_new_test_data.py cuts, collects, and creates the vowelsLSE_new_test dataset.     
      - signRecognition_init_fastai.py is a recognition module for the vowels of LSE in real-time using the hand detection and image classification modules that work for the FastAI model.
      
      
    The _classification_models_ folder has six image classification models using the FastAI library:    
    
      - Convnext_tiny.ipynb.        It uses the ConvNeXt architecture.       
      - ResNet18.ipynb.             It is a model that applies the ResNet18 architecture. 
      - ResNet50.ipynb.             It is a model that applies the ResNet50 architecture. 
      - ViT_b_16.ipynb.             It is a model that applies the ViT base 16 architecture. 
      - ViT_b_32.ipynb.             It is a model that applies the ViT base 32 architecture. 
      - ensemble_best_models.ipynb. In this notebook, we create an Ensemble model with the best three models applied according to the results of the metrics.
      
    _notebook_images_ folder has images used in the notebooks, such as the transformations applied to the data and the samples of signs of the vowels of the LSE.

   # Datasets
   ## 1. vowelsLSE_new_version Dataset

It was created in May, 2023 at the University of La Rioja. It consists of RGB images of 5 different gestures in JPG format. It contains three folders: one for training `train` (2423 images), one for testing `test` (692 images), and one for validation `val` (346 images), for a total of 3461 images. It contains 5 classes. The images can be classified into:
  - A (332 (right hand), 335 (left hand), total images: 667)
  - E (377 (right hand), 393 (left hand), total images: 770)
  - I (333 (right hand), 335 (left hand), total images: 668)
  - O (340 (right hand), 338 (left hand), total images: 678)
  - U (334 (right hand), 344 (left hand), total images: 678)
  
The images are 400 x 400 in size and have a white background so that they are the same size.

**Observation:** Here we are going to refer to the test dataset as **Original test data**.

![me](https://github.com/AlvearVanessa/models_for_vowels_spanish_sign_language_recognition_v2/blob/main/vowelsLSE_new_version.png)



   ## 2. vowelsLSE_new_test Dataset

It was created in January 2024 at the University of La Rioja. It consists of RGB images of 5 different gestures in JPG format from five different people on different days, and in this dataset there is no information about the person who created the training dataset. This folder contains two subfolders: `test` (197 images) and `train`, which is the same as the previous dataset. We collected a total of 197 images, which can be classified into:

  - A (21 (right hand), 21 (left hand), total images: 42)
  - E (22 (right hand), 15 (left hand), total images: 37)
  - I (21 (right hand), 20 (left hand), total images: 41)
  - O (18 (right hand), 20 (left hand), total images: 38)
  - U (21 (right hand), 18 (left hand), total images: 39)
  
The images are 400 x 400 in size. They have a white background to make them the same size, and this process was made in local.

**Observation:** The `train` folder here has the same images as the dataset vowelsLSE, a total of 2423 images. This might be added to this folder because, when we are creating the `DataBlock` structure for the data provided in the `DataLoader`, we use an object of class `GrandparentSplitter`. It is necessary to partition the dataset into train and test to select the `test` data in our case.

**Observation:** Here we are going to refer to the test dataset as **New test data**.

![me](https://github.com/AlvearVanessa/models_for_vowels_spanish_sign_language_recognition_v2/blob/main/vowelsLSE_new_test_sample.png)


The corresponding datasets are in the following links: 
- *vowelsLSE_new_version*          :  https://unirioja-my.sharepoint.com/:f:/g/personal/maalvear_unirioja_es/IgAkTj4A2JiVSauTByOrrXI0AfFFkFulvpb3fQlPP5QMhsM?e=7d8cj6
- *vowelsLSE_new_test*             :  https://unirioja-my.sharepoint.com/:f:/g/personal/maalvear_unirioja_es/Eq7UEiPeQvlOppvG_Fj1NgEBrlOwAIXGocOiVSC11JM0-w?e=HP3Qdl

For any further information: maalvear@unirioja.es
