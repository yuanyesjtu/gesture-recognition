# 手势识别

#### 介绍
基本思想是将数据集中视频及分类标签转换为图像（视频帧）和其对应的分类标签，也可以不标注，单独给一个小视频标注上分类类别，再采用CNN网络对图像进行训练学习和测试，将视频分类问题转化为图形分类问题。具体步骤包括：

（1） 对每个视频(训练和测试视频)以一定的FPS截出视频帧（jpegs）保存为训练集和测试集，将对图像的分类性能作为所对应视频的分类性能

（2）训练一个人物等特征提取模型，并采用模型融合策略，一个特征提取，一个分类模型。特征工程部分通用人物行为，分类模型，训练自己的类别的分类模型即可。

（4） 训练完成后载入模型对test set内所有的视频帧进行检查验证，得出全测试集上的top1准确率和top5准确率输出。

（5）实时检测。

#### 软件架构
![项目文件架构](https://foruda.gitee.com/images/1688969241116817172/ef447c68_11347056.png "屏幕截图")
```

将模型放置此处：

```
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

#### 安装教程
# 新建 imi/src/
mkir imi
cd imi
git clone 
colcon build 
source install/local_setup.bash 
ros2 run action action_pub可以施行程序，运行前先安装手语所需库

1.pip install -r requirements.txt
```

将模型放置此处：

```
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
2.将train_classifier.py 以及run_custom_classifier.py中custom_classifier换为本地文件
3.执行run_custom_classifier.py是否可以运行，可以运行后使用ros2 run action action_pub即可驱动机器人进行手语识别
