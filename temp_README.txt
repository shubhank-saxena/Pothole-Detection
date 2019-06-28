
### Rickshaw detection of pothole

### Gify of the working
Original
[Ready]

Pothole Detected
[Ready]

#### Wireframe/Working for the anroid Appliaction
[REady]
````
image
````

### Detailed working for the whole project
#### Working for the whole Project
[ready]
````
image---------------(Server Two)---------------------[/workDir] --------------------[**/GPSdir]----[/finalDir]
|                    High CPU 4vCPU                   Images are processed                            |
|                      22GB Ram                       by running an automated                         |
|                                                     script and saved in mapsDir                     |
(Server One)                                            [Image]
Normal CPU
1vCPU
1gb RAM
|
|
From Android Application( Images collected have cordinates in the name of the file)
[image shown]
[cordinates of the image]
|
|
Images are stored in the working directory
[/workDir]                                                                                            |
|                                                                                                     |
|                                                                                                     |
|                                                                                                     |
--------------------------[final Dir]------------------------------------------------------------------

Server One works only for the data Collection that is recieved from the Application
on the daily basis
Everyday at 9pm IST scheduled via cron script (server Two) would run and Mask RCNN
would run on all the images present in the working directory


** Using Slicing We add the size of the pothole in the image found via maskRCNN
along with the cordinates and then save it into GPS dir
Now we dont send the images to the final directory but only the names of the files

Now each file will be like this
[number of pothole found]-[pothole size]-[longitude]-[latitude].jpg

And from there via PHP Script we display them on google maps
````

#### Problem of this research project

Some images are getting wrongly detected
[images links]


FAQ/ Contact / Troubleshoot/ Issues


















#
