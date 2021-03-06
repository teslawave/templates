---
date_added: 2019-04-19
title: EACHEN ST-DC2
category: relay
type: Relay
standard: global
link: https://www.amazon.com/gp/product/B078JG96WW
image: https://images-na.ssl-images-amazon.com/images/I/61KkXM7qWTL._SL1001_.jpg
template: '{"NAME":"Garage Control","GPIO":[11,0,0,0,23,22,18,0,21,52,12,24,0],"FLAG":1,"BASE":18}' 
link_alt: 
---

This configuration will control and sense the state of 2 garage doors (or similar operating devices)

Supplies:
* ST-DC2 board
* 2 reed switches
* USB power supply
* micro USB cable

This project is controlled by Home Assistant with communications run through a MQTT server. 

To flash the board leads will need to be soldered to 3.3v, RX, TX, Ground, GPIO 4, & GPIO 14. 

Only leads Ground, GPIO 4, & GPIO 14 are needed to operate.

After loading the template enter go to the console enter the following:
'pulseTime1 5'
'pulseTime2 5'
This will cause the relays to turn back off after .5 seconds.

Hook the NO side of the relays to the momentary button on the garage door. Use a reed switch wired between GPIO 4 and ground to signal power 3 and GPIO 14 and ground to signal power 4. 

In  configuration.yaml add the following:
```yaml
cover:
- platform: mqtt
    name: "Garage 1"
    state_topic: garage/garageDoor/POWER3
    command_topic: garage/garageDoor/cmnd/POWER1
    availability_topic: garage/garageDoor/LWT
    payload_open: "ON"
    payload_close: "ON"
    payload_stop: "ON"
    state_open: "OFF"
    state_closed: "ON"
    payload_available: "Online"
    payload_not_available: "Offline"
    optimistic: false
    qos: 0
    retain: false
- platform: mqtt
    name: "Garage 2"
    state_topic: garage/garageDoor/POWER4
    command_topic: garage/garageDoor/cmnd/POWER2
    availability_topic: garage/garageDoor/LWT
    payload_open: "ON"
    payload_close: "ON"
    payload_stop: "ON"
    state_open: "OFF"
    state_closed: "ON"
    payload_available: "Online"
    payload_not_available: "Offline"
    optimistic: false
    qos: 0
    retain: false
```
