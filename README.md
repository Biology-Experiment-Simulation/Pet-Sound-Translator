# Pet-Sound-Translator (Cats)

* BU ©Steven Zhu
* BU ©Yingqi Zhang
* TA: Zhenpeng

## Product Definition
* Product Mission

The goal of this project is to create a cat sound processing software that can identify their positive and negative emotions. Our product can be used by cat owners to have a better understanding of their pets. It can also be used to monitor cat's mood automatically.
* Target Users

    1. new pet owner
    2. pet store/pet clinic staff
    3. anyone who want to have a better understanding of domestic cats
* User Stories

    1. I, a new pet owner, should be able to figure out the mood of my cat(s) using this product.
    2. I, as a pet owner, should be able to compare the recognition result of this product with the understanding of my cat(s) based on my own experience and make a comment on the result.
    3. I, as a pet store/clinic staff, shoud be able to use this product to monitor cat(s)' mood when I leave the cattery.
    4. I, as a pet store/clinic staff, should be able to look at records of cats' mood to see when the cat had bad emotions, how serious it was and how long it lasted.
    5. I, as a ML researcher, should have access to the code of this model and thus can use it as a pretrained model for other animals' mood detection.

* MVP

    1. Uer should be able to upload cat sound audio file via a GUI
    2. User shoud be able to get a cat mood recognition result.
* User Iterface Design

Our product should be an API or a computer/mobile app that:

  1. User can upload cat sound recordings using our interfaces/ User can record live cat sound and upload it to the app.
  2. Once the record is uploaded, the user will get a generalized category of cat’s emotion corresponding to its sound. 
 
 
 ## Product Survey
 * Existing Similar Products
 * Related Papers
 
 #### Similar Products
 Baby Sound Monitors (Overall):
 
 Summary: 
 
 - Stream sound from another device to monitor the user's baby
 
Differences and Takeaway: 
 
 - The main difference between baby sound monitors and our own product would be that our device will be able to categorize the recording, to give the user a better idea of what the current situation is. Secondly, the ability to stream this data to another device may be something to be implemented in our system in the future. 
    
 Dogstar (Wearable for a dog's tail)
 
Summary: 

- This product is a wearable that sends motion data to the user's mobile device and analyzes it to categorize the current emotions of the dog. The app is able to keep track of these moments and give a overall evaluation as well as a timeline for the dog. Additional features include keeping track of the user's dog's schedule.

 Differences and Takeaway: 

 - In terms of the general architecture, this product is similar to our own. If the final product that we create is to be a mobile application then the dogstar application may be a good comparison for what to include.
 
 #### Related Papers

 We can only find two papers directly related to this task which were done by the same team.
 
 ***Domestic Cat Sound Classification Using Transfer Learning***, Yagya Raj Pandeya, Dongwhoon Kim, Joonwhooan Lee, 2018
 ***Domestic Cat Sound Classification Using Learned Features from Deep Neural Network***, Yagya Raj Pandeya, Dongwhoon Kim, Joonwhooan Lee, 2018

According to these two papers, the state-of-art method is as follow:
   1. Feature Extraction:
      - Extract mel bank features from original audio signal
      - Use a pre-trained CNN (with Frequency Divison Average Pooling) to extract features from mel bank features.
   2. Classification:
      - Use five different machine learnign algorithms (Random Forest, KNN, Extra Tree, Linear Discriminant Analysis, Support Vector Machine) for the classification and ensemble all of them using majority voting.
   3. Categories: There are ten categories of cat mood (Happy, Angry, Resting, Defence, etc).

## System Design
* Major Components

![SystemArchitectureFlowchart](https://github.com/sz64/Pet-Sound-Translator/blob/Sprint1/petsoundtranslatorflowchart.png)
  
  `User Interface` Module: The basic function of this interface should be uploading audio file to our software, while the advanced version will allow users to record cat sound in real time.
  
  `Feature Extractor` Module: This module consists of two part. The first part will extract mel bank features from the original audio signal and the second part will find most useful features using multiple approaches like CNN, CDBN, etc.
  
  `Classification` Module: This module will make prediction of cat's mood based on features generated by `Feature Extractor`. Several machine learning models will be used, results of which will be ensembled to the final prediction.
  
  `Communication Interface` Module: This module will focus on transfering data between our software and the remote sever.
* Technology Selection
  `Feature Exytaction`: 
  
     First Step: Mel bank features
     
     Second Step:
     1. PCA (Principal Component Analysis)
     2. ICA (Independent Component Analysis)
     3. CNN (Convolutional Neural Network)
     4. CDBN (Convolutional Deep Belief Network)
   `Classification`:
   
     Classifier:
     1. KNN
     2. Linear Deiscriminant Analysis
     3. Random Forest
     4. Extra Tree
     5. Support Vector Machine
     
     Ensembler:
     1. Majority Voting
     
* Test Programs

 `Feature Exytaction`: 
  
   First Step: Mel bank features (see folder 'Mel')
     
   Second Step:
   1. PCA (Principal Component Analysis)
   2. ICA (Independent Component Analysis)
   3. CNN (Convolutional Neural Network)
   4. CDBN (Convolutional Deep Belief Network)
   `Classification`:
   
   Classifier:
   1. KNN
   2. Linear Deiscriminant Analysis
   3. Random Forest
   4. Extra Tree
   5. Support Vector Machine

     
   Ensembler:
   1. Majority Voting

## Application
(Located in the Application Branch, did not merge as it is separate entity)
 - Able to record .wav files.
 - Ready to integrate the classification system.
    - Can integrate through internet or possibly incorporating python code with java. 
    
    



