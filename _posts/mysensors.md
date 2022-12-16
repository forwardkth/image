title: Mysensors Wireless sensing network at home 
date: 2015-09-22 09:07:50
tags:
- sensor
- 传感器
- wireless sensing network
- 家庭无线传感网络
- Arduino
- Beaglebone
- open source
- nRF24L01+
categories: projects-项目
---

<meta name="referrer" content="no-referrer" />

![](https://www.mysensors.org/uploads/57bd7e180b692ab55e15504f/image/network.png)
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1ew98gkmzhnj20k00qogqi?raw=true)
you can see more by clicking **Read more** below :) 
点击下方按钮阅读文章正文 （基于Mysensors开源项目的家庭无线传感网络 ）
<!-- more -->

## Wireless sensing network based on “mysensors” opensource project:

I built a wireless sensing network based on "Mysensors" (www.mysensors.org) with two humidity and temperature sensing nodes and a gateway controller.
I use beaglebone black running Openhab solution (https://www.openhab.org/)  as the controller (server). you can see the pictures below.
It is not necessary to copy and paste the information about "Mysensors". If you are interested in it, please browse their website. 

The interesting thing is that the introduction of "mysensor" says Arduino nano has unstable 3.3V  output. So it needs to connect a 4.7uF capacitor to stable the voltage.
But there is no this problem on all my arduino nano boards. The sensing network works stable without the capacitor. And the radio range and strenth are no problem too.
I think this is because I did not perchase the official version Arduino. I bought the modified and compatible version from a chinese dealer. They made their own version of Arduino boards. I think they fix the probelm from the original circuit design. That is good.

Another thing is I don`t want to call something like this "Smart home". It is far from smart but remote control only...
In my opinion, a real smart home should not use APP, use monitoring chart, use digital numbers, many complex settings and so on. It should run behind your home silently and aware what you need.
A simple example is when you go back home, the system will know that you are back and give your home a proper temperature and humidity environment according to your activities like awake or sleep. If you want warmer, you can just speak out "warmer please" instead of open a APP and click buttons or input some temperature numbers.
Most products we can see in the market now is someting like a remote control. I think that is why all of these products can not  succeed. A smart home system that always bother peolpe life or make you tired will never succeed.

Of course, my ideal thinking is limited by our technology. But at least we should stop calling those thing "Smart xxx". Remote control is not smart...

![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1ew98d2kw6hj20qo0k078e?raw=true)
Server(controller) with Arduino nano radio gateway in “Mysensors” wireless sensing network
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1ew98ge4sztj20qo0k0tf3?raw=true)
One of the sensor node in "Mysensors" wireless sensing network
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1ew9m56tnspj20xc18gdvm?raw=true)
One of the sensor node with humidity and temperature sensor mounted on the wall
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1ewarapj02cj20hs0qomzc?raw=true)
Control and Monitoring UI with “OPenhab” running in Beaglebone Black

## 基于Mysensors开源项目的家庭无线传感网络 （注意不是智能家居）:

上周末在家用Mysensors开源项目构建了一个简单的只含有两个节点外加gateway的无线传感网络。关于什么是Mysensors开源项目，如何构建一个自己的Mysensors网络。这里就不复制粘贴了。详细的信息可以访问 www.mysensors.org 了解。
简单的说，Mysensors 无线传感网络采用 Arduino外加nRF2401+无线模块做为单个传感节点，配合一个网关控制器可以组成含有成百上千个传感器和执行器的传感和控制网络。这个网络可以自动组织，自动修复，同时单个传感节点有功耗管理能力，在优化程序的基础上可以实现超低功耗，适合电池独立供电。
在Beaglebone或者树莓派server控制器中运行Openhab （https://www.openhab.org/） 开源软件，提供UI界面网络监控服务。 

以上都是可以在官网详细了解的信息。 我自己构建的简单网络如下图所示，楼上卧室和楼下客厅有两个传感节点，直接固定在含有USB接口的插座上，我认为这样的结构是未来的方向，对于室内的常规应用是中合理方便的供电方式。Openhab server （Beagblone）放置于路由器旁边，方便接入家庭局域网和internet。
然后就可以从任何设备的浏览器中访问网页来对传感网络进行监控。

这里我想发表一点儿个人的想法。现在国内对于智能家居或者物联网的概念炒作乌烟瘴气的，看看现在面世的各种产品，好像所谓的智能家居就是可以用远程摄像头看看家里情况，然后可以随时随地用手机控制家中设备，小到开关灯，大到监视温湿度，烟雾报警什么的。
直接的体现就是要各种设置，各种在屏幕上点点戳戳。不知道各位觉得怎样，我觉得很累。生活中加入了这样的系统，我不会觉得方便，反而觉得麻烦。这也就是为什么现在所谓的智能家居，并没有普及和很大的市场了吧。
因为它们这些根本就不是真的智能家居，叫做传感网络或者是遥控更适合。 

未来所谓的智能家居是应该在尽量不麻烦人，不干扰人正常生活的情况下，默默的在后台运行，可以体察到人的需求而自动进行动作。举个最简单的例子，我并不关心温度湿度的数字和曲线变化，我只关心是否体感舒适，如果系统发现环境不合适了直接动作调整就好了，数字曲线关我鸟事。
即便是需要人的命令，自然手势，语音控制这些都比一个APP上好多个页面各种数据和按钮调节条要来得正宗也是需要重点突破的技术。 而且系统和节点的部署需要方便快捷，对用户屏蔽专业的设置，这些都是需要解决的问题。
再扯远点儿，上升到理论，那就是我坚信，好的科技是顺应人的自然状态，而不是改变，所谓的 "科技以人为本"。突然好怀念诺基亚。。。。

![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1ew98d2kw6hj20qo0k078e?raw=true)
Beaglebone black做为交互界面互联网server和传感网络网关（Arduino nano with nRF24L01+）的控制器
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1ew98gkmzhnj20k00qogqi?raw=true)
"Mysensors" 无线传感网络单个节点
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1ew9m7qszxmj20xc18g4f7?raw=true)
含有温度湿度传感器的单个网络节点固定在墙上，由含有USB接口的插座供电，功耗非常小
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1ewarapj02cj20hs0qomzc?raw=true)
在Beaglebone Black中运行的UI界面服务器（Openhab）显示两个房间温湿度监控和历史记录曲线