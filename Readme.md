###### MQTT/MQTT-SN (MQ Telemetry Transport for sensors)
* __MQTT__ 
** Is an machine-to-machine TCP/IP connectivity protocol
** MQTT stands for MQ Telemetry Transport. It is a publish/subscribe, extremely simple and lightweight messaging protocol, designed for constrained devices and low-bandwidth, high-latency or unreliable networks.

* __MQTT-SN__ 
** For non-TCP/IP protocol 

* __MQTT broker__
** The central communication point in charge of dispaching all the messages b/w senders and the rightful receivers.
** The topic is the routing information for the broker

* Spring has only support for MQTT 
* Eclipse Paho client has only C based library for MQTT-SN. Need to write our own Java code using JNI to support MQTT-SN 

###### The Raspberry Pi
* Raspberry Pi is a low cost, credit-card sized computer that plugs into the monitor or TV, and uses standard keyboard and mouse.
* __Installation__
** Can use SD Formatter 4.0 to format the SD and copy the NOOBS Raspberry pi bootable content
** 
* __Useful Commands__
** file raspbian-jessie.img : Displays the file information in MacOS
** hostname -I -> to display the pi ipAddress
** startx to start the GUI 
** ping raspberrypi.local
** ssh pi@raspberrypi.local
** pi-finder: Is an utility used to find the Raspberry Pi IP address
** pi-filler: Is an utility to mount the img to SD Card
** hdmi_force_hotplug=1 add it in config file, SD card to force HDMI display
** Find the Pi ip : https://github.com/thoqbk/pi-oi
** arp -a
* __Troubleshoot__
** Make sure SD card is not locked 
** After power plug is connected, Green light should blink
** 

###### OpenWRT
* Open source Linux distribution for embedded devices(typically wireless routers)

###### QEMU (Quick EMUlator)
* QEMU is a generic and open source machine emulator and virtualizer.
* Raspberry Pi Emulator
** XCode
** HomeBrew
** Install QEMU
*** brew install qemu --env=std
** RPi disk image
** Linux kernel image compiled for ARM
** command : 
qemu-system-arm -cpu arm1176 -m 256 -M versatilepb -no-reboot -serial stdio -append "root=/dev/sda2 rootfstype=ext4 rw init=/bin/bash console=ttyAMA0,115200" -kernel kernel-qemu -hda 2013-07-26-wheezy-raspbian.img
qemu-system-arm -cpu arm1176 -m 256 -M versatilepb -no-reboot -serial stdio -append "root=/dev/sda2 rootfstype=ext4 rw init=/bin/bash console=ttyAMA0,115200" -kernel kernel-qemu-4.1.13-jessie -hda raspbian-jessie.img
* To emulate the Raspberry Pi on OS X
* Link: https://sourceforge.net/projects/raspberrypiemulator/?source=directory
* __How to Use__
** Get the Raspberrypi from https://sourceforge.net/projects/raspberrypiemulator/ 
** Run /raspberry-pi-emulator-1.6.1/Mac OS X/Raspberry Pi Emulator.app/Contents/MacOS/Raspberry Pi.sh (run ./Raspberry\ Pi.sh)
** Might take time as it needs to download the Raspbain OS image and kernal 
* __Useful commands/tools__
** hostname -I -> to display the pi ipAddress
** ping raspberrypi.local
** ssh pi@raspberrypi.local
** pi-finder: Is an utility used to find the Raspberry Pi IP address
** pi-filler: Is an utility to mount the img to SD Card
** hdmi_force_hotplug=1 add it in config file, SD card to force HDMI display
** Find the Pi ip : https://github.com/thoqbk/pi-oi
** arp -a
** 

###### AllJoyn (AllseenAlliance.org)
* AllJoyn is a collaborative open-source software framework that makes it easy for developers to write applications that can discover nearby devices, and communicate with each other directly regardless of brands, categories, transports, and OSes without the need of the cloud.
* AllJoyn framework: it serves as the glue to allow devices from different companies, running on different operating systems, written with different language bindings to all speak together, and just work
* common services and interfaces that solves a specific use case, such as onboarding a new device for the first time, sending notifications, and controlling a device
* AllJoyn App: An application that uses the AllJoyn framework. Apps use either the AllJoyn Core APIs or the AllJoyn Service Frameworks API. Apps can either use the Standard Core or Thin Core implementations.
* AllJoyn-enabled device: An entity which has an AllJoyn application installed to send or receive notifications using the Notification service framework interface
* 

###### IoT Gateways

###### PoC
* __Client (Producer)__
** Install the Raspberry Pi Image
** Install the OpenWRT on Raspberry Pi image
** Emulate the Raspberry Pi in Mac OS
** Install the Client specific capabilities on Raspberry Pi (May be like Java client to run)
* __Broker__
** Install the MQTT Broker on Mac OS
** 
* __Client (Consumer) (Subcribers)__
** Could be any device like Raspberry Pi or Mobile or desktop

###### User Stories
* DONE -- As a User I want to see a simple Spring application to simulate the Publisher and Subscriber communication 
* As a User I want to see running client in the Raspberry Pi emulator, which publishes the info on a topic
* As a User I want to see running client in the Raspberry Pi emulator which subscribe and consumes the info on a topic
* As a User I want to see running client on Mac OS as a Subscriber to get the info published by the Raspberry Pi client 
* As a User I want to see the communication b/w the Bridge and the IoT platform.
* As a User I want to have JSON Message Converter
* 

###### Spring MQTT Integration 
* http://docs.spring.io/spring-integration/docs/4.3.0.RELEASE/reference/html/mqtt.html
* https://github.com/spring-projects/spring-integration-samples/tree/master/basic/mqtt
* https://github.com/andypiper/spring-int-mqtt

###### Mosquitto 
* Open source MQTT Broker 
* 

###### Architecture
![Alt Initial architecture daigram](Architecture.jpg)

###### Eclipse IoT
* http://iot.eclipse.org/
* https://eclipse.org/kura/
* https://eclipse.org/smarthome/
* http://www.eclipse.org/paho/

######