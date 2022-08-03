# Sign Object Detection Prototype

There are many sign language detector concepts using object detection, however I didn't find one that created sentences from the words detected and displayed them as subtitles like in a movie. So, I tried to make one and this is it.

<img src="demo.gif" width="250" height="250"/>

## Description

Using [SSD ResNet101 V1 FPN 640x640](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2_detection_zoo.md) from the Tensorflow Model Zoo, I used transfer learning to train it on 7 new words/classes: hello, clear, day, good, look_around, below and peace. The training set for images included me doing random signs using NZSL (New Zealand Sign Language) that can be identified from a single frame. In a sense, this can be considered cheating as many signs require the movement of hands to mean different things but this is just a prototype built upon object detection.

A buffer system was implemented to store words that are frequently detected in a short period of time and display them based upon some criterias. These sentences are cleared when no signs are detected in the video input.

## Getting Started

First things first, make sure to have [python](https://www.python.org/downloads/) and a notebook IDE installed. I used [Jupyter Notebook](https://jupyter.org/install) but feel free to use any IDEs suitable.

To install jupyter notebook, after python is installed, run:
```
pip install notebook
```

To run the notebook, in console, run:
```
jupyter notebook
```

### Dependencies

Tensorflow has a lot of dependency issues. I spent more time on solving these than on the actual project. The creation of a virtual environment here is highly recommended if you plan on training a custom model. A good guide on creating environment can be found [here](https://towardsdatascience.com/create-virtual-environment-using-virtualenv-and-add-it-to-jupyter-notebook-6e1bf4e03415). If you plan on just running my model, you can make do without a virtual environment.

In the github repo folder, to install the dependencies, run:
```
pip install -r requirements.txt
```

Warnings might be seen but they can be ignored. For training a custom model, there is an issue with Protobuf not being able to import builder.py. I have included builder.py in the base directory of the repo. More details about the Import Error can be found [here](https://stackoverflow.com/questions/71759248/importerror-cannot-import-name-builder-from-google-protobuf-internal).

### Installing

* To use the model that I trained, download my_model from [here](https://drive.google.com/drive/folders/1Wj88Nd2iDOWxkq3IudcWXnvaqjHZUqPw?usp=sharing).
* Store this folder under ```pretrained_models\checkpoints```.

### Executing program

* Open the notebook called ```sign-translator-prototype.ipynb``` using an IDE (preferably a notebook).
* Run all the cells and a pop-up window should show your webcam. Note: If no video input can be seen, try changing the videoPath variable to different integers from 1 to 8 and test which one works for you.
![image](https://user-images.githubusercontent.com/67076071/182563005-5b04d32c-e0b0-47eb-850e-97674ae48e00.png)

* To quit the video feed, press ```q```.

## Help

Some useful documentation on tensorflow object detection can be found [here](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/). You can also contact me ```sttaseen@gmail.com``` for any help. Training a custom model can be very annoying becuase of tensorflow related dependency issues. I will try my best to aid in any way possible.

## Authors

Contributors names and contact info
* Sadat Taseen
 [@sttaseen](https://github.com/sttaseen)


## Acknowledgments

Inspiration, code snippets, tutorials etc.

* [nicknochnack](https://github.com/nicknochnack/RealTimeObjectDetection)
* [haroonshakeel](https://www.youtube.com/watch?v=2yQqg_mXuPQ)
* [krishnaik](https://www.youtube.com/watch?v=XoMiveY_1Z4)
