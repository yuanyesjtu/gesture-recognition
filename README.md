# gesture recognition

#### Introduction
The basic idea is to convert the videos and classification labels in the dataset into images (video frames) and their corresponding classification labels. Optionally, a short video can be labeled with its classification category, and then a CNN network is used for training, learning, and testing on the images, thereby transforming the video classification problem into an image classification problem. The specific steps include:
(1) For each video (both training and testing videos), extract video frames (JPEGs) at a certain FPS and save them as the training and testing sets. The classification performance of the images will be regarded as the classification performance of the corresponding videos.
(2) Train a feature extraction model (such as for detecting persons or other features), and use a model fusion strategy—one for feature extraction and one for classification. The feature engineering part can be based on general human actions, while the classification model can be trained specifically for your own classification categories.
(3) After training is completed, load the model and perform validation by checking all video frames in the test set, obtaining the top-1 and top-5 accuracy across the entire test set.
(4) Real-time detection.

#### Software Architecture
![项目文件架构](https://foruda.gitee.com/images/1688969241116817172/ef447c68_11347056.png "屏幕截图")

Place model here：

resources
├── backbone
│   ├── strided_inflated_efficientnet.ckpt
│   └── strided_inflated_mobilenet.ckpt
├── fitness_activity_recognition
│   └── ...
├── gesture_recognition
│   └── ...
└── ...
```

#### Installation Tutorial
# create imi/src/
mkir imi
cd imi
git clone 
colcon build 
source install/local_setup.bash 
ros2 run action action_pub

1. pip install -r requirements.txt
2. replace the custom_classifier in train_classifier.py and run_custom_classifier.py with a local file
3. run run_custom_classifier.py, and then run ros2 run action action_pub
