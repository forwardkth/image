title: My Tele-operation robot, Generation II
date: 2015-08-28 08:59:16
tags:
- robotics
- robot
- smart car
- 机器人
- project
- 智能车
- Beaglebone
- open source
categories: projects-项目
---

<meta name="referrer" content="no-referrer" />

![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evho2onxwsj21kw16o7wh?raw=true)
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cjw1f15bm3c82lj218g0xcqku?raw=true)
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgy1fpvirumai6j23402c0e82?raw=true)
## Description:

This is my second generation Tele-operation robot  built since 2015. This robot is based on the open source platform [Beaglebone white](https://beagleboard.org/bone) which running with Debian Linux.
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evgrdvaux5j21kw16o1if?raw=true)
The **Beaglebone** is a credit-card-sized Linux computer that connects to the Internet and runs software such as Android 4.0 and Ubuntu with plenty of I/O and processing power for real-time analysis provided by an AM335x 720MHz ARM® processor. It has 256M DDR2 RAM, 3D graphics accelerator, power management capacity.

All of these above  makes it  an excellent platform  for building sensor based embedded systems and Robotics.

The source code on github: https://github.com/forwardkth/BBRobot

## Historical Project Updates:

2015
1. Modification to the class BalckPWM
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

## DEMO videos:

The Demo video 2018
<iframe width="560" height="315" src="https://www.youtube.com/embed/Y1jZm1aZNGg" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

The Old DEMO video in 2015 summer on Youtube: (The performance now is much better than it is shown in the video. There are new demo videos in 2016 below.)
<iframe width="560" height="315" src="https://www.youtube.com/embed/v77tkjFmZqY" frameborder="0" allowfullscreen></iframe>

The new DEMO video in 2016 on Youtube：
<iframe width="560" height="315" src="https://www.youtube.com/embed/8HmHFWRzwfQ" frameborder="0" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/q4rHsRQ4LsQ" frameborder="0" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/8c8KAbVZPCA" frameborder="0" allowfullscreen></iframe>
DEMO video in Youku: (For Visitors from China...)

<embed src="https://player.youku.com/player.php/sid/XMTMyMjM2MTE5Ng==/v.swf" allowFullScreen="true" quality="high" width="480" height="400" align="middle" allowScriptAccess="always" type="application/x-shockwave-flash"></embed>

you can see more by clicking **Read more** below :) 
<!-- more -->
Compare to my first Generation robot, thanks to the Beaglebone, the hardware structure of the second Generation is more simple now. The Beaglebone runnning with Linux is responsible for all the tasks: motion control, networking communication, sensor interface and video streaming.
I can realize more advanced  features for my robot like the machine vision with it. Now I just only connect a laser lamp and a Ultra sound sensor to it.

I will not talk about a lot of basic things here like motion control or networking programming. I prefer to say some my feelings and experience from **system point of view** about this project.

### Structure Overview
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evho2vc9exj21kw16o4qp?raw=true)
This robot uses Beaglebone white as the local smart brain, TPLINK WR702N as the WIFI module, one power supply and motor driver circuit board, ultra sound sensor and Laser lamp. The Beaglebone use TPLINK WR702N mini router as the wireless networking card to receive the control orders and send the data and video streaming through WIFI. But you should notice that this is not the popular **OpenWR+router+arduio or what** soluction. Why not? I will explain later.
 
### Mounting
The first thing I thought about is not the programming...it is how to mount the beaglebone on to the Robot Body. I bought the body from Chinese website TAOBAO.COM (Chinese version ebay) which cost about 500 RMB (650SEK).  Its metal material makes it strong and the two powerful DC motors with encoders mounted on it came from Japan.
There are a lot of holes on the body. But most of them is designed to fit the Arduino... (I always think that Arduino is more like a Toy for Kids...). My beaglebone is put inside a nice looking iron box with transparent cover which bought from Canada. And I do not like sticking it on the surface of the body. There is no confidence with this solution when imaging the robot running offroad.
So what I have done is to use the cable holders (usually you can find them when you open the box of your new Digi devices) to mount the whole beaglebone box tightly. I am glad to see their silver color mathching each other. (You can see it the second picture above)

### Wireless communication
The second is the WIFI module. If you search for "OpenWRT robot" in Google, you can find plenty of examples shows how easy it is to own your own wifi robot. I think it is a quick and cheap solution. Then you do not need a expensive beaglebone but a cheap 8 bits sigle chip processor like 8051. 
But I don't like this solution. I prefer a strong and powerful local brain to let the robot own the potential to be smart (self control capacity). If you have a look at all the Mars rover or Moon rover nowadays, you can easily understand why the cheap solution is not always good. The Mars rover should be smart enough to control and recover itself since receiving the control signal from the earth takes even 20 mins. 
In my opinion, Robot means **"the machine like human" but not "the machine waiting orders"**. 

So the Beaglebone is like a computer that you can just use the Ethernet port to connect to the WR702N router then configure the router to the bridge work mode. In this mode, the router works like beaglebone's wifi module. That's good. Everything is original, very stable.

![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evgrdr0lsdj21kw16o4qp?raw=true)
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evgrdnssl3j21kw16o4qp?raw=true)

### The remote controller UI on the PC

You can find the C Sharp UI here: https://github.com/forwardkth/robot_WPF_UI

### The project source code:

https://github.com/forwardkth/BBRobot

### Issues and Some opinions

C++ and C are much better than java or python to do the embedded system development. When I use the pybbio library for the robot APP, the power consuming is 0.01A or 0.02A much more than using BlackLib(C++)which is 0.7A. And you can feel that the C++ application runs more smooth than the python APP. This is only a small robot application. If you consider a huge complex system, the power you can save is considerable. Besides I feel powerful and environmental friendly when I use C++. That means I can control all the details and do optimization rather than being a top layer API caller.

Here is the video on Youtube: Bjarne Stroustrup-Why I Created C++

https://www.youtube.com/watch?v=JBjjnqG0BP8

### My future work

This is a ongoing project. The idea is to build a Remote WifiRobot controller based on OpenCV 3.4.0, cuDNN, CUDA, Deep learning and Sensor fusion.
The sensor data and video are streamed to the PC for computer vision functions and Sensorfusion solutions realization. Then the controller sends back the control command back to the Wifi robot to execute.
You can find it here:  https://github.com/forwardkth/BBRobotController_CV_DL_SF
It can be seen as a mini Autonomous Vehicle project with a RaCAM （forward looking Camera and forward Radar.
I just started to work on this project from time to time since 2017. So the code on Github has not been completed and well organized yet.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Y1jZm1aZNGg" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgy1fpvish1t10j23402c0kjm?raw=true)
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgy1fpviriawz6j21gu0sjaky?raw=true)
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgy1fpvis7nq6vj23402c0e82?raw=true)
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgy1fpvira0vdvj21hw0sqk1f?raw=true)

## Pictures:

![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evho2kpw0gj21kw16o4qp?raw=true)
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evho2aaw0fj21kw16o7wh?raw=true)
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evho3dathuj21kw16o1kx?raw=true)
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evho3h7p5jj21kw16otx2?raw=true)
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evho3kkf90j21kw16o4qp?raw=true)


