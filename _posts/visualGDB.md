title: Cross compling and remote debuging with VisualGDB on Windows
date: 2016-03-06 16:08:24
tags:
- robotics
- robot
- smart car
- 机器人
- 智能车
- Beaglebone
- open source
- VisualGDB
- cross compiling
categories: Notes-随笔
---

<meta name="referrer" content="no-referrer" />

![](https://ww3.sinaimg.cn/large/74505a4cgw1f1mhjohmbej21b70rcdwl.jpg)
Today I tried to use VisualGDB with Visual Studio 2017 to compile and run my wifi robot C++ code on my beaglebone.

https://github.com/forwardkth/BBRobot

The experience is good. You can follow the link below to install and configure the VisualGDB for your beaglebone:

https://visualgdb.com/tutorials/beaglebone/

## But I got some problems when I compiled my code.

### The first one is :

error directive: This file requires compiler and library support for the upcoming ISO C++ standard, C++0x. 
This support is currently experimental, and must be enabled with the -std=c++0x or -std=gnu++0x compiler options.	

The solution: open your VisualGDB project properties from your right click menu.
Then uncheck box of Same as CFLAGS and add  "-std=c++0x" to CXXFLAGS configuration. 
So I will looks like -ggdb -ffunction-sections -O0 -std=c++0x

### The second one is about Pthread:

The error info indicate that pthread library is missing. 

So I download the pthread for windows and configure the include derectories and library directories, then add -lpthread to the CXXFLAGS. But It still does not work.

The real solution is:

<!-- more -->
You do not need to down load any pthread lib for windows. Just write "pthread" to the Library name in the Makefile settings. Then it works. 
Or you can write "-lpthread" to Common flags. Both solutions work fine. 

I think that is because this configuration is related to your target environment, not your host machine.
You can see the screenshot of the configurations below:

![](https://ww3.sinaimg.cn/large/74505a4cgw1f1mhjohmbej21b70rcdwl.jpg)

https://ww3.sinaimg.cn/large/74505a4cgw1f1mhjohmbej21b70rcdwl.jpg

You can find the new DEMO video of my wifi robot on Youtube：
<iframe width="560" height="315" src="httpss://www.youtube.com/embed/q4rHsRQ4LsQ" frameborder="0" allowfullscreen></iframe>
