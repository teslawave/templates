---
date_added: 2019-03-09
title: Xenon SM-SW102-2
category: switch
type: Switch
standard: us
link: https://www.amazon.com/Tempered-Controlled-Separately-Standard-Compatible/dp/B0719Q5G5B
image: https://user-images.githubusercontent.com/5904370/54644416-85fe5480-4a99-11e9-8f0a-ece4a8640e45.png
template: '{"NAME":"SM SW102","GPIO":[255,255,255,18,22,255,255,255,17,21,255,255,255],"FLAG":0,"BASE":18}' 
link_alt: https://www.amazon.ca/SM-SW102-Tempered-Wireless-Compatible-Assistant/dp/B07KFVYMPT
---
I didn't spot any headers, but device has a sub-board with an ESP-12 module on it. Solder right to the 3.3V, Ground, TX, RX, and GPIO pins and flash away. I set the device up as a generic device with the following assignments. 

* GPIO 3 is button 2
* GPIO 4 is relay 2
* GPIO 12 is button 1 
* GPIO 13 is relay 1
