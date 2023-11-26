---
title: "IOT Gateway Protocol Comma"
linkTitle: "IOT Gateway Protocol Comma"
weight: 1
description: >
  IOT Gateway Protocol, 4G, LAN, WiFi, MQTT, all configuration command
---

<!--
{{% pageinfo %}}
This is a placeholder page that shows you how to use this template site.
{{% /pageinfo %}}
-->


# MQTT Configuration From Server Command :

```
To test communication with hardware
Send : 
{"method":"test"}
Response : 
{"response":"ok"}
```

```
Write multiple data to device using modbus function code 16
you can write any quantity as per slave device support
Send :
          {"method":"fn16", "params":"modbus id, fn code, start add, qty,data 1, data 2, data 3"}
Example : {"method":"fn16", "params":"1        , 16     , 0        , 3  ,     1,      2,      3"}
Response :
{"response":"fn16 ok"}
```

```
Read data from modbus slave device

Command Description
{"method":"txn", "params":"txn no, txn flag, modbus id, function code, start add , qty, poll interval, txn timeout, txn retry count"}

txn no          = number of slave device configuration supported in hardware
txn flag        = enable = 1 / disable = 0
modbus id       = slave device id
function code   = 3 or 4
start add       = start address
qty             = number of register read from device
poll interval   = delay between two command
txn timeout     = slave device response timeout
txn retry count = if response not receive, retry count

Send :
Example : {"method":"txn", "params":"0,1,1,3,0,10,1000,1000,1"}

Response :
{"response":"txn ok"}
```

```
sync time from internet server
Send :
{"method":"time sync"}
Response :
{"response":"time sync ok"}
```

```
comport setting
Send :
{"method":"comport", "params":"baud rate, config"}
{"method":"comport", "params":"9600     , 3     "}

Response :
{"response":"comport ok"}
```




# LAN Card, MQTT Configuration Parameter :
```
Firmware Version
%{,??,INFO,}!
```
```
Set MQTT Server
%{,??,MQTTSERVER,server ip,}!
```
```
Set MQTT User
%{,??,MQTTUSER,user name,}!
```
```
Set MQTT Password
%{,??,MQTTPASS,password,}!
```
```
Set MQTT Subscriber Topic
%{,??,MQTTTOPICSUB,subscriber-topic,}!
```
```
Set MQTT Publish Topic
%{,??,MQTTTOPICPUB,publish-topic,}!
```








<!--
# Images
-->

<!--

<div class="container">

![image](led-display-control-card-1.jpg)

</div>

-->


<!-- 

<div class="container">

![image](led-display-control-card-2.jpg)

</div>

-->


<!--

<div class="container">

![image](led-display-control-card-3.jpg)

</div>

-->

---


