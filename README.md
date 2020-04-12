# Facial-Expression-Recognition for customer Relationship Management

**Facial Expression or Facial Emotion Detector can be used to know whether a person is sad, happy, angry and so on only through his/her face. This Repository can be used to carry out such a task. It uses your WebCamera and then identifies your expression in Real Time. Yeah in real-time!**

> ## PLAN:

This is a three step process. In the first, we load the XML file for detecting the presence of faces and then we retrain our network with our image on five diffrent categories. After that, we import the label_image.py program from the last video and set up everything in realtime.

> ## DEPENDENCIES

Hit the following in CMD/Terminal if you don't have already them installed:

		pip install tensorflow
		pip install opencv-python
That's it for now.

So let's take a brief look at each step.

> ## STEP 1 - Implementation of OpenCV HAAR CASCADES :

I'm using the "Frontal Face Alt" Classifier for detecting the presence of Face in the WebCam.

Next, we have the task to load this file, which can be found in the label.py program.

		# We load the xml file
		classifier = cv2.CascadeClassifier('haarcascade_frontalface_alt.xml')
		
Now everything can be set with the Label.py Program. So let's move to the next Step.

> ## STEP 2 - ReTraining the Network - Tensorflow Image Classifier:

We are going to create an Image classifier that identifies whether a person is sad, happy and so on and then show this text on the OpenCV Window. This step will consist of several sub steps:

- We need to first create a directory named images. In this directory, create five or six sub directories with names like Happy, Sad, Angry, Calm and Neutral. You can add more than this.

- Now fill these directories with respective images by downloading them from the Internet. E.g., In "Happy" directory, fill only those iages of person who are happy.

- Now run the "face-crop.py" program .

- Once you have only cleaned images, you are ready to retrain the network. For this purpose I'm using Mobilenet Model which is quite fast and accurate. To run the training, hit the got to the parent folder and open CMD/Terminal here and hit the following:

        python retrain.py --output_graph=retrained_graph.pb --output_labels=retrained_labels.txt --architecture=MobileNet_1.0_224 --image_dir=images
That's it for this Step.

> ## STEP 3 - Importing the ReTrained Model and Setting Everything Up:

Finally, I've put everything under the "label_image.py" file from where you can get evrything. Now run the "label.py" program by typing the following in CMD/Terminal:

        python label.py
It'll open a new window of OpenCV and then identifies your Facial Expression. We are done now!!

# *Some Facial Emotions* :

![face_emotion1](https://www.psychonomic.org/resource/resmgr/featured_content/content_pictures/8.26.16emofaces.png)

## *Analyzing Each dimensions of the Face*
![face_emotion2](https://i.pinimg.com/originals/37/3c/4a/373c4a10b7185a59b33a79dce3340c74.jpg)
![face_emotion3](https://acart.com/wp-content/uploads/2017/04/facial-recognition-img2.jpg)
