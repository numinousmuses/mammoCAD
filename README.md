![image](https://user-images.githubusercontent.com/103385201/184056451-ae9da128-4ce6-4ea1-90a5-d0046214354a.png)

# mammoCAD
CNN for tumor detection in mammograms

## Project Description

This was my project for my AP Research course in the AP Capstone Diploma program. The project goal was to create a Computer-Aided Diagnosis algorithm, which is an artificial intelligence algorithm that uses computer vision to detect and diagnose cancer in radiology images and other visually-based medical diagnostic tests. This project aimed to create one such algorithm for breast cancer using specifically mammograms, as previous research in the specific context of breast cancer CADs had [low accuracies](https://pubs.rsna.org/doi/full/10.1148/radiol.2018181371). Moreover, there has been sparse research in this specific cancer application in comparison to brain tumors or lung CT scans. Furthermore, research approaches to breast cancer CADs mostly utilized [breast histopathology data](https://www.kdnuggets.com/2019/10/convolutional-neural-network-breast-cancer-classification.html), aka breast biopsies, for diagnosis. 

TLDR: The focus of the project was chosen to be mammography because of the non-invasiveness of the screening test, and also the lack of research into breast cancer diagnosis using mammography.

## Data

The data was taken from the [Digital Database for Screening Mammography](http://www.eng.usf.edu/cvprg/mammography/database.html) curated by the University of South Florida. The actual database was much larger than could be utilized, so a subset of data, made available on [kaggle](https://www.kaggle.com/datasets/cheddad/miniddsm2), was used. Specifically, I created a subset of this dataset composed only of cancerous and noncancerous mammograms as JPEG files. The resultant dataset I published [here](https://www.kaggle.com/datasets/joshuaokolo/miniddsm-jpeg-dataset). The result was about 5000 images total.

Some sample images of the data below, resized to squares for easier CNN processing.

![image](https://user-images.githubusercontent.com/103385201/184054799-7080e48e-e9bf-4685-9ae3-8be51542b726.png)

## Neural Network
A layered CNN:

![image](https://user-images.githubusercontent.com/103385201/184056094-f9f46186-5891-4940-84a9-36427ffa2b29.png)

A Convolutional Neural Network was trained, the architecture is below.

![image](https://user-images.githubusercontent.com/103385201/184054104-54cc0560-9665-4d9e-8110-2110dce40dee.png)

In code:

![image](https://user-images.githubusercontent.com/103385201/184054858-75a2cb19-f407-4dd0-9090-3a9c56d971b5.png)

Sample CNN image processing. A CNN performs feature extraction through the layers. The visual features seem reduced to human eye, but the numerical arrays are the most important features the computer has extracted and uses to differentiate between cancerous and noncancerous mammograms.

![image](https://user-images.githubusercontent.com/103385201/184055108-ffc7a9e0-c5db-450b-a131-e9189dfeb6f9.png)

## Training Results

![image](https://user-images.githubusercontent.com/103385201/184055185-f73d68eb-5646-4d96-a5d8-50581e79ee3d.png)

## Analysis, Limitations, and Future Directions

The program had a 99 percent accuracy in classifying normal mammograms, and an approximate 85 percent accuracy in classifying cancerous mammograms. This means the program is adept at detecting normal mammograms, but for implementation, the cancerous mammogram accuracy needs to increase.

However, since it is indeed an AI model, the process is upgradable, and can be iterated with more data or perhaps training time to increase the accuracy. Through transfer learning the model could also be fine-tuned to datasets of other diseases.

An implication of this research project would be a faster and more accessible method to diagnosing breast cancer. It is esteemed to add more accurate to that list as well, but for that to be claimed with integrity some improvements would need to be made. While most CAD algorithms deployed in the clinical settings are used as an aid for radiologists, I hope for the development of this technology in order to be utilized in lieu of a radiologist in impoverished or otherwise resource-limited regions of the world, as well as traditional clinics and hospitals.

## Misc

A slide presentation of the work can be found [here](https://docs.google.com/presentation/d/1d9mhd0fuubnEqmDddL0iYs00secpbMdi/edit?usp=sharing&ouid=113795033473157238384&rtpof=true&sd=true). Thank you for reading, and please credit my work if you choose to build on it!

## Citations

[Ref paper/Mini-DDSM] C.D. Lekamlage, F. Afzal, E. Westerberg and A. Cheddad, “Mini-DDSM: Mammography-based Automatic Age Estimation,” in the 3rd International Conference on Digital Medicine and Image Processing (DMIP 2020), ACM, Kyoto, Japan, November 06-09, 2020, pp: 1-6.

[Ref DDSM] Michael Heath, Kevin Bowyer, Daniel Kopans, Richard Moore and W. Philip Kegelmeyer, in Proceedings of the Fifth International Workshop on Digital Mammography, M.J. Yaffe, ed., 212-218, Medical Physics Publishing, 2001. ISBN 1-930524-00-5.

