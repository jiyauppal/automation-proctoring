# Auto Practo

Project to create an automated proctoring system where the user can be monitored automatically through the webcam and microphone. The project is divided into two parts: vision and audio based functionalities.

## Table of Content

 - [Introduction](https://github.com/jiyauppal/face-mask-detector#Auto_Practo)
 - [Technologies Used](https://github.com/jiyauppal/face-mask-detector#Technologies_Used)
 - [Vision](https://github.com/jiyauppal/face-mask-detector#Vision)
 - [Audio](https://github.com/jiyauppal/face-mask-detector#Audio)
 - [For Contributing](https://github.com/jiyauppal/face-mask-detector#For-Contributing)
 
### Technologies Used

For vision:
```
Tensorflow>2 and < 2.4
OpenCV
sklearn=0.19.1 # for face spoofing. 
The model used was trained with this version and does not support recent ones.
```
For audio:
```
pyaudio
speech_recognition
nltk
```

## Vision

It has six vision based functionalities right now:
1. Track eyeballs and report if candidate is looking left, right or up.
2. Find if the candidate opens his mouth by recording the distance between lips at starting.
3. Instance segmentation to count number of people and report if no one or more than one person detected.
4. Find and report any instances of mobile phones.
5. Head pose estimation to find where the person is looking.
6. Face spoofing detection

### Face detection
It is implemented in `face_detector.py` and is used for tracking eyes, mouth opening detection, head pose estimation, and face spoofing.

### Facial Landmarks
It is implemented in `face_landmarks.py` and is used for tracking eyes, mouth opening detection, and head pose estimation.

### Eye tracking
`eye_tracker.py` is to track eyes.


### Mouth Opening Detection
`mouth_opening_detector.py` is used to check if the candidate opens his/her mouth during the exam after recording it initially. 


### Person counting and mobile phone detection
`person_and_phone.py` is for counting persons and detecting mobile phones.


### Head pose estimation
`head_pose_estimation.py` is used for finding where the head is facing.


### Face spoofing
`face_spoofing.py` is used for finding whether the face is real or a photograph or image.


## Audio
It is divided into two parts:
1. Audio from the microphone is recording and converted to text using Google's speech recognition API. A different thread is used to call the API such that the recording portion is not disturbed a lot, which processes the last one, appends its data to a text file and deletes it.
2. NLTK we remove the stopwods from that file. The question paper (in txt format) is taken whose stopwords are also removed and their contents are compared. Finally, the common words along with its number are presented to the proctor.

The code for this part is available in `audio_part.py`

## For Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

