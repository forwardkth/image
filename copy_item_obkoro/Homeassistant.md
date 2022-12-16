title: Home assistant + Mysensors + Xiaomi + homebridge
date: 2018-04-25 22:59:28
tags:
- sensor
- Raspberry Pi
- Mysensors
- Xiaomi
- Siri
- Home assistant
- hass
- homebridge
- IoT
- Arduino
categories: projects-项目
visible:
---

<meta name="referrer" content="no-referrer" />

## Description:
I started to build a home sensor network with MySensors solution in 2016.
You can find it here:  https://forwardkth.github.io/2015/09/22/mysensors/
Recently I have expanded this project with the Home assistnat server, xiaomi plugs and homeBridge. Now Mysensors platform, xiaomi eco system, Home assistant controller and iOS eco system can be combined together as a complete smart home system.
You can find many similar instruction and tutorials from internet. So I just briefly show some key components needed.
## Raspberry Pi based home assistant server:
Home Assistant is an open-source home automation platform running on Python 3. Track and control all devices at home and automate control. Perfect to run on a Raspberry Pi.
https://www.home-assistant.io/
![](https://wx4.sinaimg.cn/mw1024/74505a4cgy1fqm3tjzxqxj21dc0wwwuq.jpg)
![](https://wx4.sinaimg.cn/large/74505a4cgy1fqrrxqivy8j21hc0qo12v.jpg)
![](https://wx2.sinaimg.cn/large/74505a4cgy1fqrrxpt9i8j21hc0qqgo5.jpg)
![](https://wx3.sinaimg.cn/large/74505a4cgy1fqrrxr4r2fj21gz0qo4dv.jpg)
## MySensor wireless sensor network:
![](https://www.mysensors.org/uploads/57bd7e180b692ab55e15504f/image/network.png)
MySensors is an open source hardware and software community focusing on do-it-yourself home automation and Internet of Things.
It helps people who'd like to create original and affordable sensors and actuators based on components like, Arduino, ESP8266, Raspberry Pi, NRF24L01+ and RFM69.
Website: https://www.mysensors.org/
### ESP8266 Sensor gateway:
In order to communicate between and collect data from your sensors, we need a wireless communications link. Currently we support a couple of small transceiver called nRF24L01+ and RFM69. You can also run the MySensors library directly on the WiFi enabled ESP8266 for sensors not running on batteries.
It's pretty smart, small, low-cost and does not consume a lot of battery power.
Gateway - passes data from nodes to your home automation controller as well as from the home automation controller back to nodes. You can attach sensors directly to the gateway as well.
You can also send messages directly between two nodes in the network without transiting through the gateway. For example, your outside temperature sensor can send its data directly to another sensor in your kitchen with an attached display.
It's possible to build a WIFI enabled gateway running directly on an ESP8266 module. The porting has been done by Yveaux and has been documented here.
https://forum.mysensors.org/topic/1870/esp8266-wifi-gateway-port-for-mysensors
The easiest build option is probably to use the NodeMcu Devkit v.10 (by the NodeMcu Team). This board has the ESP-12 module mounted. Just connect the radio, install gateway software and you're good to go.
![](https://wx1.sinaimg.cn/mw1024/74505a4cgy1fqm3vap22gj21dc0wwgxj.jpg)
![](https://wx2.sinaimg.cn/mw1024/74505a4cgy1fqm3v6r9rhj21dc0wwdp4.jpg)

### Ardoino Nano sensor nodes:
Your sensors will form a tree network topology. Normally the sensor nodes (S) will send their information directly to the gateway (GW). If you live in a mansion or very large house, you may need to enable the repeater mode for some sensor nodes (R) to relay data from sensors that are located far away from the gateway.

Sensor nodes - continuously read the status of all attached sensors and pass the sensor data through the radio network back to the gateway. These puppies have the option to sleep most of the time if you want to run them on battery.

Repeater-sensor nodes - must stay awake in order to pass messages from its child sensor nodes. A repeater-node can optionally include direct-attached sensors and report their sensor data to the gateway. In most setups you will probably not need any repeater-nodes as the transmitter range for the most basic radio is about 20-60 meters.

Each node is assigned a unique sensorId or address that is used for sending and receiving point-to-point messages. You can assign a static sensorId (in the sketch) or let the controller automatically assign one to the sensor. AUTO-mode configures the sensor to request a sensorId from the controller and is the default option for all the examples that we provide. The sensor stores the assigned sensorId in its non-volatile memory to ensure the correct sensorId persists across power transitions. A gateway always has sensorId 0.

The first time a new sensor boots up, it will determine the path to the gateway by sending out a special Help-me-find-my-way-home-message. The repeater-sensor nodes and gateway listen for these messages and will respond to a sensor's plea-for-help-message. Their reply will inform the sensor how far they are from the gateway so the newly born sensor can determine the shortest path to the gateway, be it directly to the gateway or through a repeater-sensor node which is the closest to the gateway. If the sensor node later loses contact with the gateway or a repeater-sensor node, it will automatically repeat this procedure to determine the best path to the gateway - a sensor node considers contact with the gateway to be lost if it fails to send 3 consecutive messages.

Gateway and repeater-sensor nodes maintain a small routing table to know where to direct their messages to the network surrounding it. The routing table is built up automatically by the repeaters and gateway by introspecting messages received.

A MySensor radio network can consist of up to 254 different radio nodes and each radio node can report data for 254 attached child sensors. This means that you can, in theory, manage data for up to 64516 sensors in a single radio network. If this isn't enough, you can create another parallel radio network on a different channel and there are 126 available channels [NRF24L01+].

To summarize: New nodes will automatically find the shortest path to gateway and and use a persistent unique sensorId to send and receive point-to-point messages. The tree network is robust and "self heals" as the topology changes. For example, you move a sensor node to a different physical location or a repeater-node dies.
![](https://wx1.sinaimg.cn/mw1024/74505a4cgy1fqm3uyr37lj21dc0wwk2z.jpg)
![](https://wx2.sinaimg.cn/mw1024/74505a4cgy1fqm3v2vwe8j21dc0wwqeo.jpg)
## HomeBridge and iOS home automation:
Homebridge is a lightweight NodeJS server you can run on your home network that emulates the iOS HomeKit API.
It supports Plugins, which are community-contributed modules that provide a basic bridge from HomeKit to various 3rd-party APIs provided by manufacturers of "smart home" devices.
This project can be found here: https://github.com/nfarina/homebridge
![](https://camo.githubusercontent.com/e9e98b1b146452a6987e4a05dd4ece8c34781643/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f31306c373949436f6854753469512f67697068792e676966)
It is perfect to combine with the HomeAssistant to interact with your home by your iphone home APP and Siri.
Below you can see that homebridge help my iphone detected all my sensor nodes and Xiaomi plugs at home.
![](https://wx2.sinaimg.cn/mw1024/74505a4cgy1fqm3uubkidj20ku112h4g.jpg)
<!-- more -->
![](https://wx2.sinaimg.cn/mw1024/74505a4cgy1fqm3vrx7sjj20ku112kb3.jpg)
I have set up some home automation rules for example turning on home lights when sunset happens. It is quite self adaptive since the sunset time differs every day.
Another one is that turning on the security camera when I leave my home and turning it off when my phone location is home.
![](https://wx3.sinaimg.cn/mw1024/74505a4cgy1fqm3vme4xxj20ku1120uz.jpg)