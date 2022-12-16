title: Project@KTH "Cardio wireless ECG handheld device" (2010)
date: 2015-08-26 21:42:00
tags: 
- ECG
- Bluetooth
- wireless
- handheld
- 心率
- 蓝牙
- 手持设备
categories: projects-项目
---

<meta name="referrer" content="no-referrer" />

![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evgrf9np3gj20e80ao3zx?raw=true)

## Overview:

The basic idea of this project is to develop a kind of ECG monitoring and analysis system. It includes a handheld ECG recording device, a data gateway, mobile phone application, web application (GUI) and a stationary which used to do the interaction between the patients and the doctors. The patients can monitor their ECG condition any time and upload the data via bluetooth and internet to the remote database for the analysis by the doctors later. The doctors can give the feedback to the patients via the web application or Phone application.

I together with my team were responsible for the development of the Cardio Device which is based on MSP430experimental board "WASA" and a bluetooth module from "Bluegiga". 

![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1eviq4d5w48j20f30bbabf?raw=true)
The data transmiting among Cardio device, PC and mobilephone.

<!-- more -->

## Gateway:
The gateway is a piece of hardware, which is connected to a TV screen (optional when there is a mobile phone with internet connection). It serves to the patient as a means of displaying the cardio data and sending it to the server. It is capable of receiving Bluetooth signals and can send https request via an existing Internet connection.

## cardio Device: 
The cardio handheld  device which measures the pulse/ECG of the patient can send the ECG data to other devices via  bluetooth.
![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evgrdjt1ouj21kw0zpdld?raw=true)
Cardio Device architecture

![](https://github.com/forwardkth/image/tree/master/weibo/74505a4cgw1evhi2qoiicj20go0cidh0?raw=true)
the cardio device prototype

## Mobile phone:

The patients mobile phone (optional when there is a gateway) can receive cardio data from the device and output the EKG image. If there is an internet connection, it can send the data via an https request to the server. If there is no internet connection, the data can be sent to the gateway via Bluetooth.

## Web application:
 
This encompasses the web interface for phones and stationary computers of patients and doctors, the main database, the authentication/security mechanisms, and the update commands interface for the gateway and mobile phones.

## Stationary: 

A computer located at a patients home or a doctors office/hospital, etc. It can be used to access the website.