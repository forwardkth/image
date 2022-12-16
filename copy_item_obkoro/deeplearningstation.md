title: HP OMEN Desktop PC for Deep learning and Vision Dev
date: 2018-04-02 00:18:13
tags:
- Deep learning
- Ubuntu
- 深度学习
categories: Notes-随笔
---

<meta name="referrer" content="no-referrer" />

In order to continue my project (remote contoller for my wifiRobot based on computer vision and sensor fusion), I bought a powerful Desktop PC from HP with the Nvidia Geforce GTX1070 Video Card. It looks quite nice and very easy for maintenance. But I am too old to have interest in playing games. Just use it as a working horse...

![](https://wx4.sinaimg.cn/large/74505a4cgy1frlwtesrlpj22c0340kjm.jpg)
![](https://wx1.sinaimg.cn/large/74505a4cgy1frlwt4rv50j22c03404qq.jpg)
![](https://wx2.sinaimg.cn/large/74505a4cgy1frlwu19befj23402c07wj.jpg)
![](https://wx2.sinaimg.cn/large/74505a4cgy1frlwuctqswj23402c0x6q.jpg)

It took a lot of time to figure out the solutions for different issues before making the development enviroment ready.

1. You need to disable the default driver for the video card and install the nvidia one. It is also OK to directly install the CUDA Tookit which has the official driver included.

2. Disable the secure boot in BIOS. Otherwise the Nvidia driver will not be loaded. And It will not take effect.

3. It also takes me a lot of time to figure out how to install tensorflow with CUDA9.2.
actually you need to compile the tensorflow source code with the CUDA9.2 configuration by yourself. this blog might help:  http://www.python36.com/install-tensorflow141-gpu/

I installed both the lastest versions of CUDA and CUDNN. But the TensorRT does not support CUDA9.2 for now. Later I will try to install multi versions of CUDA and try to switch among them.

![](https://wx3.sinaimg.cn/mw1024/74505a4cgy1frmxjykddej23402c0e82.jpg)
![](https://wx3.sinaimg.cn/mw1024/74505a4cgy1frmxk74fhdj23402c0e82.jpg)

4. The version of Phython is also a something needs to be noticed. It is very important to know under which version of python the tensorflow is installed. And you need to do corresponding python interpreter configuration in the Pycharm IDE when working with tensorflow
![](https://wx3.sinaimg.cn/mw1024/74505a4cgy1frn6qe1itqj21h80rmagc.jpg)


5. OpenCV is quite easy to install without any issue.

6. Another thing is that when you compile the Darknet Yolo with Debug = 1, you need to add the following lines in the makefile. Unless the make process will not be successful.
![](https://wx4.sinaimg.cn/mw1024/74505a4cgy1frn6qdjc88j20p30kc413.jpg)

Then I am happy to see the YOLOv3 model can run in more real-time on this PC with maximum 27FPS!
You can see the Video of testing here:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Y1jZm1aZNGg" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Finally I can really continue my project now: https://github.com/forwardkth/BBRobotController_CV_DL_SF

I will have the both versions of project for Linux and Windows.

 


