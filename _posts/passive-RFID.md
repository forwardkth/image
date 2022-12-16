title: Project@KTH "The wireless RFID sensing device"(2010)
date: 2015-08-26 20:11:11
tags:
- RFID
- wireless sensing
- 无线传感
categories: projects-项目
---

<meta name="referrer" content="no-referrer" />

![](https://ww2.sinaimg.cn/mw1024/74505a4cgw1evhi2sbx8nj20go0cimz4.jpg)

## Description:
Imaging the situation in a museum, some antiques are put inside a hermetically sealed container. We want to monitor the temperature and moisture inside. But we donot hope to open it. This small device can give us a solution. The device can be put inside the sealed container and capture the temperature and moisture information. We can read the sensor data from outside of the container with a RFID reader without open it. But We know that the passive RFID tags can only send fixed information (ID) when it gets energy from the RFID reader. Then the reader can recognize and identify the specific tag. How can we read the dynamic data from a passive RFID?

In this project a passive RFID tag's coil loop is cut off and connected with the MSP430 experimental board. We use the processor's GPIO to control the connection or disconnection of the loop in order to modulate the  active information.

Then a communication protocol is created for the data transmition between the reader and the sensing device. First of all, the same communication bit rate is defined both in the device and the reader which is 50 bits per second. Then the protocol defines that the reader receives binary 1 when it can detect the tag ID, otherwise means binary 0. The protocol also defines that the data package sent to the reader includes start sign 9bits, data 32 bits and end sign 9 bits. So the sending rate of the device and the receiving rate of the reader are synchronized. The sensing device detects the temperature and moisture info and encodes the sensor data into a 50 bits binary package according to the protocol. Then it will modulate this data package with the RFID tag's connection and disconnection. The RFID reader (antena) is connected to SUSE linux computer through serial port. A program running on the PC is responsible to control the reader and translate the 50 bits data package received into temperature info and humidity info.

## DEMO VIDEO:
[https://v.youku.com/v_show/id_XMjE1MDQzNzc2.html](https://v.youku.com/v_show/id_XMjE1MDQzNzc2.html)

<!-- more -->