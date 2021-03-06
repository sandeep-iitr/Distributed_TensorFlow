# Distributed_TensorFlow
This repository contains the code used to set up distributed TensorFlow cluster for the course project CSM213B.

## Details about Project
1. Website more details is available [here](https://sites.google.com/view/csm213b/home).
2. Demo video is available [here](https://www.youtube.com/watch?v=Xyw2u2cab84).
3. Slides of the final presentation are available [here](https://drive.google.com/file/d/0B9XBlYTll5ttTDFkZVVGc3g2b0U/view?usp=sharing).

## There are 4 folders the details of which are explained as below:

* Alex

* Backend

* FrontEnd

* SoftMax_Local

## 1. Alex
The AlexNet is build in Tensorflow. 
We imported the caffe trained model (https://github.com/BVLC/caffe/tree/master/models/bvlc_alexnet) and only make inference in our program to get the image classification result.
The codes include:
1. Runnining AlexNet in local machine
2. In distributed clusters (after partition)
3. In distributed clusters (multiple sessions)

## 2. Backend
The backend server is developed using Flask in Python. The backend listend to the connections from the front end and process the request.
The code of the backend is present in Backend folder.
###  Installation
1. The cluster on raspberry pi devices is set up by following the procedure described [here](https://github.com/samjabrahams/tensorflow-on-raspberry-pi).
2. The flask installation is described in detail [here](http://flask.pocoo.org/docs/0.12/tutorial/).
3. Installing distributed TensorFlow on multiple machines is explained on the official page [here](https://www.tensorflow.org/deploy/distributed).
4. First add the cluster details in the server file, and then start the server process on each device of cluster as explained in the official documentation given in 3.
5. Now you can start the flask basked backend server to listen to the incoming connections.
###  Requirements
1. Raspberry pi with camera attached and running python 2.7+ along with following the installations described in upper sections.
2. Connectivity of cluster devices along with unique ip assingement in the local subnet. All cluster devices should be able to logically communicate with each other.

## 3. FrontEnd
The frontend is developed using the Javascript. The server is hosted using the apache tomcat and is deveoped in eclipse.
###  Installation
1. The eclipse for web development can be downloaded from the [link](http://www.eclipse.org/downloads/packages/eclipse-ide-javascript-web-developers/indigosr2).
2. The eclipse requires the setting up of Apache Tomcat which is explained in detail [here](http://tomcat.apache.org/).
###  Requirements
1. Eclipse requires the Java SDK to be installed.
2. The machine running frontend should be able to communicate with the cluster so as to schedule jobs at runtime on the cluster backend server.

## 4. SoftMax_Local
This folder contains the local implementation the softmax in python.
The codes include:
1. Training the naive softmax regression classifier and stored the ckeckpoint files.
2. Running inference using softmax regression classifier on both MINST dataset and also self-created digit image data.
3. Running softmax in single machine, and in distributed cluster settings.
4. Folder for Image preprocessing in TensorFlow.
