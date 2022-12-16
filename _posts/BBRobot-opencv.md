title: The Remote autonomous controller with Computer vision, Deep learning and Sensor fusion for my WiFi Robot (ongoing)
date: 2018-03-30 23:11:59
tags:
- sensor
- BeagleBone
- Robot
- CV
- Computer Vision
- CUDA
- YOLO
- Deep learning
- OpenCV
categories: projects-项目
visible:
---

<meta name="referrer" content="no-referrer" />

## Description:
This is a ongoing project. The idea is to build a remote Wifi Robot controller based on OpenCV 3.4.0, cuDNN, CUDA, Deep learning and Sensorfusion.
The sensor data and video are streamed to the PC for computer vision functions and Sensorfusion solutions realization. Then the controller sends back the control command back to the Wifi robot to execute.
You can find it here:  https://github.com/forwardkth/BBRobotController_CV_DL_SF
It can be seen as a mini Autonomous Vehicle project with a RaCAM （forward looking Radar and Camera.
I just started to work on this project from time to time since 2017. So the code on Github has not been completed yet.
<iframe width="560" height="315" src="https://www.youtube.com/embed/Y1jZm1aZNGg" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Historical updates:

2018.5  Project moved to Linux platform
2018.6  Integrate YoloV3 into BBRobot controller project with C++ Wrapper and shared library
        BBRobot controller C++ project built up with Eclipse setup
![](https://wx1.sinaimg.cn/mw1024/74505a4cgy1fs496rv0zrj21hb0t31kx.jpg)

Some tips:
1.in the makefile for generating the shared lib of Darknet, the nvcc configuration should be the path of your local cuda bin folder.
![](https://wx4.sinaimg.cn/mw1024/74505a4cgy1fs496vfj4aj212p0ql7bj.jpg)
2. Suggest to copy the shared lib to /usr/lib folder to avoid the "can not find xxxx.so" problem.
![](https://wx2.sinaimg.cn/mw1024/74505a4cgy1fs496lhc7qj20z90khn1k.jpg)
3. The OpenCV lib dependancies should be manually added to the project build configuration in Eclipse.
4. You can find the Darknet shared lib builder here: https://github.com/forwardkth/DarkLibBuilder

## Some old Pictures:
![](https://ww4.sinaimg.cn/mw1024/74505a4cjw1f15bm3c82lj218g0xcqku.jpg)
![](https://wx4.sinaimg.cn/mw1024/74505a4cgy1fpvirumai6j23402c0e82.jpg)
![](https://wx2.sinaimg.cn/mw1024/74505a4cgy1fpvish1t10j23402c0kjm.jpg)
![](https://5b0988e595225.cdn.sohucs.com/images/20170820/f96728dcc26d4eb0a7db9c49acf6756b.gif)

<!-- more -->
![](https://wx3.sinaimg.cn/mw1024/74505a4cgy1fpviriawz6j21gu0sjaky.jpg)
![](https://wx1.sinaimg.cn/mw1024/74505a4cgy1fpvis7nq6vj23402c0e82.jpg)
![](https://wx2.sinaimg.cn/mw1024/74505a4cgy1fpvira0vdvj21hw0sqk1f.jpg)

## BBRobot project:
The source code of the Wifi Robot project can be found here: https://github.com/forwardkth/BBRobot


My Modification to the original Blacklib recently are:

1. Modification to the class BalckPWM
2. Implement the BlackServo class for easier Servo control like "PyBBIO"
3. Add Servo control example code (example_Servo.h) under /BlackLib/examples folder
4. Add my WIFI robot code (example_wifirobot.h) as a example under /BlackLib/examples folder

You can run the examples with the ExampleMain.cpp or run the formal project with WiFiRobotMain.cpp

Historical project updates:

2015
1. Modification to the class of BalckPWM
2. Add Servo motor control class "BlackServo"
3. Add Servo control demo code under /BlackLib/examples folder
4. Add demo WiFi robot code (example_wifirobot.h) as a example under /BlackLib/examples folder
5. Add Video streaming code
		   
2016       
1. New remote control UI with C sharp and WPF
2. iOS APP for WiFi Robot remote control
		   
2017       
1. Start working with the Computer Vision based remote controller for the WiFiRobot (ongoing...)
    
2018       
1. Add formal WiFi robot project code under "BBRobot/WiFiRobot/"
2. Add Json support for Multiple sensor data transmission

The picture below shows the visualGDB configuration with VS2017 for cross complie and remote debug and deploy
https://ww3.sinaimg.cn/large/74505a4cgw1f1mhjohmbej21b70rcdwl.jpg

------------------------------------------------------------
![](https://ww2.sinaimg.cn/mw690/74505a4cgw1evho2onxwsj21kw16o7wh.jpg)
![](https://ww1.sinaimg.cn/mw690/74505a4cgw1evgrdvaux5j21kw16o1if.jpg)
![](https://ww2.sinaimg.cn/large/74505a4cgw1f7oypkop58j20ku0fmn0o.jpg)
![](https://ww4.sinaimg.cn/large/74505a4cgw1f7oyqnelgnj20qo0qo79n.jpg)

The new DEMO video on Youtube:
https://youtu.be/q4rHsRQ4LsQ
https://youtu.be/8c8KAbVZPCA

The old outdoor DEMO video on Youtube:
https://www.youtube.com/v77tkjFmZqY

------------------------------------------------------------

In order to continue my project (remote contoller for my wifiRobot based on computer vision and sensor fusion), I bought a powerful Desktop PC from HP with the Nvidia Geforce GTX1070 Video Card. It looks quite nice and very easy for maintenance. But I am too old to have interest in playing games. Just use it as a working horse...

![](https://wx4.sinaimg.cn/mw1024/74505a4cgy1frlwtesrlpj22c0340kjm.jpg)
![](https://wx1.sinaimg.cn/mw1024/74505a4cgy1frlwt4rv50j22c03404qq.jpg)
![](https://wx2.sinaimg.cn/mw1024/74505a4cgy1frlwu19befj23402c07wj.jpg)
![](https://wx2.sinaimg.cn/mw1024/74505a4cgy1frlwuctqswj23402c0x6q.jpg)

It took a lot of time to figure out the solutions for different issues before making the development enviroment ready.

1. You need to disable the default driver for the video card and install the nvidia one. It is also OK to directly install the CUDA Tookit which has the official driver included.

2. Disable the secure boot in BIOS. Otherwise the Nvidia driver will not be loaded. And It will not take effect.

3. It also takes me a lot of time to figure out how to install tensorflow with CUDA9.2.
actually you need to compile the tensorflow source code with the CUDA9.2 configuration by yourself. this blog might help:  https://www.python36.com/install-tensorflow141-gpu/

I installed both the lastest versions of CUDA and CUDNN. But the TensorRT does not support CUDA9.2 for now. Later I will try to install multi versions of CUDA and try to switch among them.

![](https://wx3.sinaimg.cn/mw1024/74505a4cgy1frmxjykddej23402c0e82.jpg)
![](https://wx3.sinaimg.cn/mw1024/74505a4cgy1frmxk74fhdj23402c0e82.jpg)

4. The version of Phython is also a something needs to be noticed. It is very important to know under which version of python the tensorflow is installed. And you need to do corresponding python interpreter configuration in the Pycharm IDE when working with tensorflow
![](https://wx3.sinaimg.cn/mw1024/74505a4cgy1frn6qe1itqj21h80rmagc.jpg)


5. OpenCV is quite easy to install without any issue.

6. Another thing is that when you compile the Darknet Yolo with Debug = 1, you need to add the following lines in the makefile. Unless the make process will not be successful.
![](https://wx4.sinaimg.cn/mw1024/74505a4cgy1frn6qdjc88j20p30kc413.jpg)

Then I am happy to see the YoloV3 model can run more in real-time on this PC with maximum rate of 14FPS!
![](https://wx4.sinaimg.cn/mw1024/74505a4cgy1frn0x6dh7zj20qo0qon1g.jpg)

You can see the Video of testing here:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Y1jZm1aZNGg" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Finally I can really continue my project now: https://github.com/forwardkth/BBRobotController_CV_DL_SF

I will have the both versions of project for Linux and Windows.
