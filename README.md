# registration-master

This repo contains an application for automated face registration using AI.

Before running the codes, we need to install all the prerequisites. 

Have made a requirements.txt for the same. 

Use ``` pip3 install -r requirements.txt ``` to install prerequisites.

Can be executed on x86 and ARM architecture systems.

***

**Contents**

1. requirements.txt - contains all the prerequisites required for the smooth functioning of the application.

2. models - conatins pre-trained models for inference.

3. utils - contains the all dependencies that the main code require.

4. data.csv - database to store details of the people to be registered. Please update the csv according to the given format.

***

**Usage**

 - Run ``` python3 registration.py ```
 
 - You'll be encountered with 3 options **(Register/Detect/Exit)**
 
 - Register: Takes input as serial number of the person and face.
 
    - The code uses the MTCNN model for Face detection.

    - Face alignment is done using dlib.

    - FaceNet is used for converting the various features of a person's face into vectors (embeddings).

 - Detect: To recognize a registered person.

   - When a face is detected, the system checks if the person exists in the database.

   - On recognition, the person's face is highlighted with a green box. 

***



**For Embedded Linux Platforms**

- Connect 2 USB/CSI cameras (as per availability) and a mic for voice input

- Install drivers if required using ```insmod [driver location]```

- Check the device IDs for the connected peripherals in ```/proc/asound/```

- Make changes in .asoundrc accordingly.

***

**Docker Image**

Install docker using ```sudo apt-get install docker.io``` and assign sudo permission to it.

You can find the readymade image that I've already built using ``` docker pull darpanjain/ai-input ```

Visit [My DockerHub Profile](https://hub.docker.com/u/darpanjain/ "DockerHub Profile darpan-jain")

Run the image using ``` docker run -it --rm ai-input ```

You can use the provided Dockerfile to build your own image.

> 1. Clone the repo to your system
> 2. Build your image using ``` sudo  docker build -t application:v1 . ```

***

**_Any contributions to the project are welcome :)_**

