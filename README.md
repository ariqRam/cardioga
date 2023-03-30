# TensorFlow Lite Pose Estimation Android Demo

### Overview
This is an app that continuously detects the body parts in the frames seen by
your device's camera. These instructions walk you through building and running
the demo on an Android device. Camera captures are discarded immediately after
use, nothing is stored or saved.

The app demonstrates how to use 4 models:

* Single pose models: The model can estimate the pose of only one person in the
input image. If the input image contains multiple persons, the detection result
can be largely incorrect.
   * PoseNet
   * MoveNet Lightning
   * MoveNet Thunder
* Multi pose models: The model can estimate pose of multiple persons in the
input image.
   * MoveNet MultiPose: Support up to 6 persons.

See this [blog post](https://blog.tensorflow.org/2021/05/next-generation-pose-detection-with-movenet-and-tensorflowjs.html)
for a comparison between these models.

![Demo Image](posenetimage.png)

## Build the demo using Android Studio

### Prerequisites

* If you don't have it already, install **[Android Studio](
 https://developer.android.com/studio/index.html)** 4.2 or
 above, following the instructions on the website.

* Android device and Android development environment with minimum API 21.

### Building
* Open Android Studio, and from the `Welcome` screen, select
`Open an existing Android Studio project`.

* From the `Open File or Project` window that appears, navigate to and select
 the `lite/examples/pose_estimation/android` directory from wherever you
 cloned the `tensorflow/examples` GitHub repo. Click `OK`.

* If it asks you to do a `Gradle Sync`, click `OK`.

* You may also need to install various platforms and tools, if you get errors
 like `Failed to find target with hash string 'android-21'` and similar. Click
 the `Run` button (the green arrow) or select `Run` > `Run 'android'` from the
 top menu. You may need to rebuild the project using `Build` > `Rebuild Project`.

* If it asks you to use `Instant Run`, click `Proceed Without Instant Run`.

* Also, you need to have an Android device plugged in with developer options
 enabled at this point. See **[here](
 https://developer.android.com/studio/run/device)** for more details
 on setting up developer devices.


### Model used
Downloading, extraction and placement in assets folder has been managed
 automatically by `download.gradle`.

If you explicitly want to download the model, you can download it from here:

* [Posenet](https://storage.googleapis.com/download.tensorflow.org/models/tflite/posenet_mobilenet_v1_100_257x257_multi_kpt_stripped.tflite)
* [Movenet Lightning](https://tfhub.dev/google/movenet/singlepose/lightning/)
* [Movenet Thunder](https://tfhub.dev/google/movenet/singlepose/thunder/)
* [Movenet MultiPose](https://tfhub.dev/google/movenet/multipose/lightning/)

### Criteria (Impacts)
* SDG Goal 3 with Target 3.8 - Achieve universal health coverage
* Google Technologies utilized - Frontend: Figma, Backend: TensorFlow Lite + Android
* Problem Statement - As one of the top causes of death among Malaysians, heart disease kills more people than road accidents. According to national statistics, 17 per cent of deaths in Malaysia are caused by ischemic heart disease. In Malaysia, the number of cardiovascular disease cases increases by 5 per cent every year, according to the National Heart Institute. There are 10,000 cases of cardiology and hypertension and 4,000 cases of heart surgery in one year. 
* Aim - Our app aims to enhance your cardiovascular fitness with real-time AI-proctored yoga sessions. With our pose estimation model, precise yoga pose will make the best out of your fitness sessions. Users can customize their schedule for yoga sessions and get in touch with our practitioners for advises and galvanizations. A personalized statistics will be provided for users to keep track of their progress to possess the best care of their cardiovascular health.

Promote yoga (holistic practice) to reduce risk of cardiovascular diseases with our app, you don’t need to prepare any budgets for equipment, places, fundamental, trained instructors & it is suitable for peoples from all ages and stages of life. (Coverage health and decrease the household expenditure). Yoga, a mind-body exercise involves a series of postures, breathing exercises, and meditation techniques designed to promote physical and mental well-being.
Yoga is also a low impact activity as it is gentle to joint and muscle, which means this makes it a safe exercise for people including seniors and those with injuries or physical limitations or even pregnant.

Physically: 
        1.) Flexibility
 	      2.) Strength
	      3.) Balance
	      4.) Cardiovascular health

Mentally: 
        1.) Reduce stress
	      2.) Improve concentration
	      3.) Promote relaxation

Spiritually: 
        1.) self-realization
	      2.) enlightenment
        
* Future and next steps of solutions:
a.) Implements more AI models like GCP’s AutoML - alleviate the workloads of   practitioners when the number of users is increased.
b.) Use a feedback loop – utilize and collect the real-time data to continuously improve the performance of our system like the accuracy of correcting the poses of users during the yoga sessions
c.) Outbound collaborations with other organizations like Ministry of Health of Malaysia – to obtain more opinions for improvements and increases the population of target beneficiary
d.) Escalate our application with more advanced and useful features – multi-languages, offline mode, premium services

### Criteria (Technology)
* Google Technologies used and reasons:
a.)	Android: The implementation of Cardioga requires the use of a camera device. Android holds a share of over 71% of smartphones worldwide. This will make Cardioga accessible, thus can bring a healthy lifestyle to more people.
b.)	TensorFlow Lite: TensorFlow is opensource and its lite version is easily portable and lightweight. Currently, Cardioga is expected to run on Android, but with the portability of TensorFlow Lite, it is easy to port Cardioga anywhere else. A custom IoT device might make the yoga experience easier, like a smart TV for better visual, or a smart watch for lighter access. The opensource nature of TensorFlow can leverage Cardioga by customizing its model and upgrading it under the supervision of health, heart, and yoga experts.

* Code Testing and iteration
One challenge faced is training the model on custom data set, and porting it back to the Android app. In order to address this challenge, we utilized the guide posted by Google Developers as a Collab notebook to train the model, and go through the 	example code posted on Pose Estimation tutorial by Google, to port the model back to the app.

### Additional Note
_Please do not delete the assets folder content_. If you explicitly deleted the
 files, then please choose `Build` > `Rebuild` from menu to re-download the
 deleted model files into assets folder.
