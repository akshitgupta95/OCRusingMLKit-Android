# ID Card Data Extractor

Text Extraction from Aadhaar Card,Pan Card for Indian Citizens using on-device(Android) machine learning. 
Since Aadhar Card and Pan Card contain sensitive info about users, sending images of these to cloud to extract data
raises security concerns particulary if the servers are located outside India.  
However, here all the text is extracted using machine learning implemented on device.All computations are happening on device and no server/internet connection is required once the trained ML model has been downloaded.

<img src="https://github.com/akshitgupta95/IDCardDataExtractorWithOnDeviceML/raw/master/aadhaar.png" align="center" width="1000">

## Supported Identity Cards (for Indian Citizens only)

1.Aadhar Card  
2.Pan Card  
The above 2 were carefully selected as they are one of the popular proofs of identity and address used in India and also because they follow a stricly defined template as they have been published over the years in comparison to Voter-ID cards which has several variations.  
Also i will add support for Indian Passports in the future.  

## Architecture

Here a pretrained ML Model is used whose output is fed to a data post processing layer(in android app). Once data is processed, the android app shows the relevant extracted details.  
I am not an expert in data science ,however if someone is really looking to build his own Machine learning model,[Tensorflow lite is place to start.](https://www.tensorflow.org/mobile/tflite/)  
You can make a custom Tensorflow model,convert it to TF lite and then embed it into the android app.  

<img src="https://github.com/akshitgupta95/IDCardDataExtractorWithOnDeviceML/raw/master/Untitled%20Diagram.png" align="center" width="800">


## Setup

1.Download your own google-services.json file and put in under /app directory.If you need more info check [add Firebase to Android](https://firebase.google.com/docs/android/setup).  
2.After successfully connecting to firebase, a pre-trained Mahine Learning model for text extraction is downloaded using MLKit.  
3.If everything is in place,you should be able to run the app for data extraction on an android phone.  
4.The app has three modes or activities (Select appropriate mode):  
  I : Aadhar Card : here output of pretrained ML Model from MLKit is processed specifically for Aadhaar Cards.  
  II: Pan Card : here output of pretrained ML Model from MLKit is processed specifically for Pan Cards.   
  III: Generic ID Card : Here standard output of ML model from MLKit is shown.    

**IMPORTANT**: This app was tested on Google Pixel running Android 8.1 which privides support for Neural Networks API to improve performance of
performing machine learning tasks on-device. Older devices may take slightly longer times to generate output.

## Contribution  

If you want to contribute by either by adding support for more types of identity documents or building a custom ML model from scratch, Feel free to contact me at akshitgupta1695@gmail.com

