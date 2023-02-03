# Deep-Learning-OCR-Cursive-Handwriting

## Problem Statetment
OCR (Optical Character Recognition) is a technique of reading textual information directly from digital documents and scanned documents without any human intervention. These documents could be in any format like PDF, PNG, JPEG, TIFF, etc.
Handwritten characters are much more difficult to recognize than printed characters due to differences in writing styles for different people due to deformations, inclination, size, different handwriting styles, and incomplete strokes having a place with ligatures, continuous characters, and noise. Thus the need for deep learning that provides solutions for text information extraction from images arises.

## About the dataset
The **IAM On-Line Handwriting Words Database (IAM-OnDB)** contains forms of handwritten English text acquired on a whiteboard. It can be used to train and test handwritten text recognizers and to perform writer identification and verification experiments.

- The IAM Online Handwriting Database is structured as follows:
- 115,320 isolated and labeled words
- 221 writers contributed samples of their handwriting
- more than 1700 acquired forms
- 10257 isolated and labeled text lines in on-line and off-line format
- 86272 word instances from a 11059 word dictionary

## Exploratory Data Analysis 
- **Preprocessing:** Real-world images are not always clicked/scanned in ideal conditions, they can have noise, blur, skewness, etc. That needs to be handled before applying the DL models to them. For this reason, image preprocessing is required to tackle these issues.
- **Text Detection/ Localization:** Different models are used to detect text in the images. These models usually create bounding boxes (square/rectangle boxes) over each text identified in the image or a document. 
- **Padding the Images:** As the dataset contains words of various lengths (the maximum length being 21) and different sizes due to difference in handwriting, padding has been added to the images so that all of them are of the same size- 128x32 (width x height). 


## Models implemented
1. CRNN
<img width="307" alt="image" src="https://user-images.githubusercontent.com/98946943/216513456-8c52e905-1ca7-4a16-b0c8-4cca39cd2ef2.png">

2. CNN-BiLSTM
<img width="320" alt="image" src="https://user-images.githubusercontent.com/98946943/216513630-7129a4c1-d028-447b-b759-6cf905245937.png">

3. CNN-BiGRU
<img width="751" alt="image" src="https://user-images.githubusercontent.com/98946943/216513689-5efcc712-7d44-4ecf-b9d4-0b937305fcfa.png">

## Conclusion
The following models were chosen for this purpose: CRNN, CNN+BiLSTM, and CNN+BiGRU. We determined these models' accuracy after training. The model correctly classifies a data instance if all the letters in the word have been predicted correctly. If all the letters in the word aren't predicted correctly, it is a misclassification.Further,since the three gates in the LSTM model address the issue of vanishing gradients and long-range dependencies that are common in CNN, CNN+BiLSTM had the best accuracy of all the models. Also as there are very few differences between their architectures, the accuracy of GRU and the LSTM model is roughly equivalent.The accuracy of CRNN, however, is somewhat low, primarily because RNN depends on long-distance signals. An RNN's state keeps track of data from all prior time steps. The current input modifies the previous information at each new timestep. The data that was stored in the early timesteps entirely changes after a considerable number of steps. Therefore, it cannot predict more than 2-3 letters correctly.Conclusively, the application of our models can be extended for recognizing medicine names from doctor’s prescriptions, historical document recognition, automatic reading of bank cheques, automatic postal code identification, converting handwriting to text in real-time, extracting data from filled-in forms, etc.

