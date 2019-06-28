Pothole Detection via MaskRCNN
==============================

This whole Project was primarly build for the TATA innoverse competition 2018
(November) Pothole Detection Competition

Pothole detection Accuracy 81%

------------------------------------------------------------------------------

### Team
-------------------
[Pradyum Gupta](https://www.linkedin.com/in/pradyumgupta/)
[Surya Pratap Shekhawat](linkedin https://www.linkedin.com/in/surya-pratap-shekhawat-906147159/)
[Avinash Kumar](https://www.linkedin.com/in/avinashme/)

------------------------------------------------------------------------------
**Structure for the repository**
```
.
├── AnnotationFile
│   └── Pothole.json
├── ImageWorking_add_textInImage
│   ├── Image_working_Python.ipynb
│   ├── README.md
│   ├── fonts_Dir.zip
│   └── test_photos.zip
├── LabelMaker
│   ├── README.md
│   └── install_LabelMaker.ipynb
├── PotholeDetectionMaskRCNN_jupyterNotebooks
│   ├── Pothole_detection.ipynb
│   └── PrelimearyModelBuildingGPU.ipynb
├── README.md
├── search_bing_api.py
├── stitchImage2Video
│   ├── image2VideoSec.py
│   └── imageToVideo.py
├── videoFormation
│   ├── README.md
│   ├── VideoFormationMaskRCNN.ipynb
│   └── successfulVideoFormationWithMaskRCNN.ipynb
└── visualize.py
```
------------------------------------------------------------------------------

We have used variety of Datasets  :

#### Install youtube-dl to download files from google drive directly in terminal
```
https://github.com/ytdl-org/youtube-dl#installation
```
------------------------------------------------------------------------------

#### Training Dataset
For the training dataset we have considered 4 types of dataset..
- Original Dataset Links
````

````
-------------------------------------------------------------------------------
#### We have resized all the images for faster processing to 800x800
file named

We have also done annotion of all the images present there,
Annotion images

- For Annotion of images we have used robots.ox.ac.uk
````
http://www.robots.ox.ac.uk/~vgg/software/via/via-1.0.6.html
````
-------------------------------------------------------------------------------
-  train
````
https://drive.google.com/file/d/1PGhXUnaJDpcjgoLEhNn9gRvGZGRCzWUt/view?usp=sharing
````

- val
````
https://drive.google.com/file/d/1PGhXUnaJDpcjgoLEhNn9gRvGZGRCzWUt/view?usp=sharing
````
-------------------------------------------------------------------------------

#### Testing Dataset link  
Donwload the whole folder and test accordingly
````
https://drive.google.com/drive/u/2/folders/1duZ9O0If8mpHk8lZkFHQifv5R8z4dcKx
````
````
Structure for the whole Test Dataset Links

├── test_dataset
├──----- Photos
├──----- IMG_7300.MOV
├──----- IMG_7301.MOV
├──----- IMG_7310.MOV
├──----- IMG_7311.MOV
├──----- IMG_7312.MOV

````
-------------------------------------------------------------------------------

#### We have trained model till 160 epoch
- As our accuracy of our model is 81% people who want to replicate in between and can take it
  the higher accuracy feel free to download
- we are also providing the different stage of trained model so that people who want to consider
  it to use in transfer learning can also use this

epoch 40
````
https://drive.google.com/file/d/1TGdD2TmuE70tSdysma3Z1PZiMOxWPqaq/view?usp=sharing
````

epoch 120
````
https://drive.google.com/file/d/1tTcE1tfeg57QaHW3A9v2gd_mqme8rU3u/view?usp=sharing
````

epoch 160
````
https://drive.google.com/file/d/1JA_xsHkohFiX-T7vSGefpTGemqMbYDCt/view?usp=sharing
````

- base model link (Normal github download is slow)
````
https://github.com/matterport/Mask_RCNN/releases
````

-------------------------------------------------------------------------------

For training Models
````

````

Accuracy : 81% in different environments

#### System configration used
For training

````
(Google cloud)
Nvidia V100 GPU
4vCPU
22gb RAM
````

For testing
````
(Google cloud)
4vCPU
16gb RAM
````

For Android Application
We have used Apache Cordova Framework

````
https://drive.google.com/file/d/1YIfFLZkNAF3R810iWtj8L3ygyLK4RmVw/view?usp=sharing
````
--------------------------------------------------------------------------------


#### For making the whole product life cycle simple and economical we have used
two servers and push the data in 1 bucket for easy access in the system accorss
````
Architecture image
````

#### Wireframe/Working for the anroid Appliaction
````
image
````

#### Working for the whole Project
````
image
````

-------------------------------------------------------------------------------

**We have created Android Application for the detection of potholes on Roads by the end of february we will shifting our application and model to openSource.**

To increase the model accuracy this time we are looking forward to _train it 6 diff environments_,

_Drop a mail if someOne require an early access to private repository_
'pradyumgupta@ieee.org'

-------------------------------------------------------------------------------
#### Extra Utilities that we used while building this whole Project with
Application


!mv
shutil
gpustat

-------------------------------------------------------------------------------
#### References used
````
1.  https://github.com/matterport/Mask_RCNN
2.  https://www.analyticsvidhya.com/blog/2018/07/building-mask-r-cnn-model-detecting-damage-cars-python/
3.  
````










------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------------------------------------------

Pothole Detection via MaskRCNN
==============================

This whole Project was primarly build for the **__TATA innoverse competition 2018
(November) Pothole Detection Competition__**

Pothole detection Accuracy **__81%__** in different environments

![Pothole Detected](https://media.giphy.com/media/Xc9DFuCIIiouihgfzZ/giphy.gif)  ![Original Images Link](https://media.giphy.com/media/jpKRIVzNVJv3VEegTZ/giphy.gif)


## Team

[Pradyum Gupta](https://www.linkedin.com/in/pradyumgupta/)
[Surya Pratap Shekhawat](https://www.linkedin.com/in/surya-pratap-shekhawat-906147159/)
[Avinash Kumar](https://www.linkedin.com/in/avinashme/)


## SETUP
We have used variety of Datasets  :

Install **youtube-dl** to __download files from google drive__ directly in terminal
```
https://github.com/ytdl-org/youtube-dl#installation
```
#### Training Dataset
To increase the model accuracy , For the training dataset we have trained them _5 types of dataset.._
- Original Dataset Links
```
Sunny Dataset
Anue Dataset
Road Damage Dataset (Adachi)
Rick_set6
Kitti image Dataset
```
If you want to add your own dataset into our dataset. We have **resized all the images** for faster processing to **800x800**, Please do same with your images too
```python
from PIL import Image
import os
from resizeimage import resizeimage

count = 0

for f in os.listdir(os.getcwd()):
    try:
        with Image.open(f) as image:
            count +=1
            cover = resizeimage.resize_cover(image, [800,800])
            cover.save('pgm-1_{}.jpg'.format(count),image.format)
            print(count)
            os.remove(f)
    except(OSError) as e:
        print('Bad Image {}{}'.format(f,count))
```


We have also done annotion of all the images present there,
Annotion images

- For Annotion of images we have used robots.ox.ac.uk
````
http://www.robots.ox.ac.uk/~vgg/software/via/via-1.0.6.html
````

**Download these files**

| Folder Name        | Download Link           |
| -------------------|:-----------------------:|
| Train | [Gdrive link](https://drive.google.com/file/d/1PGhXUnaJDpcjgoLEhNn9gRvGZGRCzWUt/view?usp=sharing) |
| Val      | [Gdrive link](https://drive.google.com/file/d/1PGhXUnaJDpcjgoLEhNn9gRvGZGRCzWUt/view?usp=sharing)     |

We have created this Dataset for final testing of the model
This folder contains videos and photos that we recorded in May 2019
**[Test Dataset Download Link](https://drive.google.com/drive/u/2/folders/1duZ9O0If8mpHk8lZkFHQifv5R8z4dcKx)**
```

Structure for the whole Test Dataset Links

├── test_dataset
├──----- Photos
├──----- IMG_7300.MOV
├──----- IMG_7301.MOV
├──----- IMG_7310.MOV
├──----- IMG_7311.MOV
├──----- IMG_7312.MOV
```
#### We have trained model till 160 epoch
- As our accuracy of our model is 81% people who want to replicate in between and can take it
  the higher accuracy feel free to download
- we are also providing the different stage of trained model so that people who want to consider
  it to use in transfer learning can also use this


| Epochs        | Download Link           |
| -------------------|:-----------------------:|
| epoch 40  | [Gdrive link](https://drive.google.com/file/d/1TGdD2TmuE70tSdysma3Z1PZiMOxWPqaq/view?usp=sharing) |
| epoch 120 | [Gdrive link](https://drive.google.com/file/d/1tTcE1tfeg57QaHW3A9v2gd_mqme8rU3u/view?usp=sharing)     
| epoch 160 | [Gdrive link](https://drive.google.com/file/d/1JA_xsHkohFiX-T7vSGefpTGemqMbYDCt/view?usp=sharing) |
| base model | [Github link](https://github.com/matterport/Mask_RCNN/releases)|

# Running Architecture for Application

![System Configration Image](https://raw.githubusercontent.com/Prady96/Pothole-Detection/master/Images/Pothole%20Detection%20Project.png?token=AHIVHIJUTMMMJIYCYLEPQN25D4EQC)

Explaination of each segment

For making the whole **product life cycle simple and economical** we have used
**two servers** and push the data in 1 bucket for easy access in the system accorss







# Download Andorid Application
We have used Apache Cordova Framework for the complete development of Android & iOS Application

| Andoird Application Link v0.5  | [Gdrive Link](https://drive.google.com/file/d/1YIfFLZkNAF3R810iWtj8L3ygyLK4RmVw/view?usp=sharing)          |
| -------------------|:-----------------------:|

## Working for the Andoird Application
![Wireframe of Application](https://raw.githubusercontent.com/Prady96/Pothole-Detection/master/Images/wireFrame_AndroidApp.jpg?token=AHIVHII2PZYI6KQPOLPYEGK5D4FJW)


**We have completed Application Development for Detectiono of Potholes on Roads**
_We have also open sourced are models for people who want to introduce tranfer learning or like to improve
this Deep learning model feel to take a pull requests_

**We have created Android Application for the detection of potholes on Roads by the end of february we will shifting our application and model to openSource.**

## Extra Utilities that we used while building this whole Project with Application


!mv
shutil
gpustat

## References used
````
1.  https://github.com/matterport/Mask_RCNN
2.  https://www.analyticsvidhya.com/blog/2018/07/building-mask-r-cnn-model-detecting-damage-cars-python/
3.  
````


_Feel free to contact me if you have any questions and/or suggestions _
**_[pradyumg@gmail.com](mailto:pradyumg@gmail.com)_**

























#
