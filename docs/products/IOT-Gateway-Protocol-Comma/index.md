---
title: "IOT Gateway Protocol CS"
linkTitle: "IOT Gateway Protocol CS"
weight: 1
description: >
  IOT Gateway Protocol - Comma Saperated, 4G, LAN, WiFi, MQTT, all configuration command
---

<!--
{{% pageinfo %}}
This is a placeholder page that shows you how to use this template site.
{{% /pageinfo %}}
-->

# Default Setting :   
device publish topic    : embedded_art_pub   
device subscribe topic  : embedded_art_sub   


# MQTT Configuration From Server Command :
```
To test server communication with hardware
Send : 
@@,test,##
Response : 
@@,test ok,XX,##
  - XX = any number
```

// 	comma, separated format
// 	@@,timesync,##

// 	comma, separated format
// 	@@,txn,0,1,1,3,0,10,3000,1000,1,##
// txn no, txn flag, modbus id, function code, start add , qty, poll interval, txn timeout, txn retry count

// comma, separated format
// @@,txnendis,txn no., enable/disable,##
// @@,txnendis,0,1,##

// comma, separated format
// @@,gettxn,0,##

```
    
        //                   "params":"modbus id, fn code, start add, qty,data 1, data 2, data 3"
        // {"method":"fn16", "params":"1        , 16     , 0        , 3  ,     1,      2,      3"}

    	// comma, separated format
    	// @@,fn16,1,16,0,3,1,2,3,##
```

```
    	// comma, separated format
    	// @@,comport,baud rate, data bits, parity, stop bits,##
    	// parity : 0 = none, 1 = odd, 2 = even
    	// @@,comport,115200,8,0,1,##
```
```

    	// comma, separated format
    	// @@,getcomport,##
```

```
    	// comma, separated format
    	// @@,getmqtt,##

		// comma, separated format
		// @@,mqttport,1883,##

        	// comma, separated format
    	// @@,mqttserver,broker.hivemq.com,##

        	// comma, separated format
    	// @@,mqttuser,ea_test,##


          	// comma, separated format
    	// @@,mqttpass,ea_test,##

          	// comma, separated format
    	// @@,mqtttopicpub,ea_pub,##


          	// comma, separated format
    	// @@,mqtttopicsub,ea_sub,##


          	// comma, separated format
    	// @@,mqttsave,##

```

    	// comma, separated format
    	// @@,srno,123456,##

          	// comma, separated format
    	// @@,getsrno,##




# SMS for Configuration :
```
Get Admin Mobile Number : 
SMS 33                  
```
```
Add admin mobile number :

SMS 44 1 0123456789     admin mobile number add 1  
SMS 44 2 0123456789     admin mobile number add 2  
SMS 44 3 0123456789     admin mobile number add 3 

To admin mobile number add with password :
SMS 44 1 7048593237 xxxx
    xxxx = password

```

```
To get MQTT related setting via SMS :

SMS 44 10		Mqtt Port
SMS 44 11		MQTT server name
SMS 44 12		MQTT user name
SMS 44 13		MQTT Password
SMS 44 14		MQTT publish topic
SMS 44 15		MQTT subscribe topic
SMS 44 20		reconnect to mqtt server
```

```
Set MQTT setting using SMS :

SMS 44 10 1883
SMS 44 11 broker.hivemq.com
SMS 44 12 embedded_art_test
SMS 44 13 embedded_art_test
SMS 44 14 embedded_art_pub
SMS 44 15 embedded_art_sub
```

```
NTP Time Server :

SMS 44 16 time.nist.gov
```

```
office use only 
Set Card Serial Number: 

SMS 66 00 123456
```

```
To set table value :

SMS 69 001 00123  	
      001   = table address
      00123 = table value
```

```
Get table value :
SMS 69 001
    001 = table address
```

```
Set Password

SMS 91 0000
```

```
Get Device Firmware :

SMS 92
```
```
set company name, max. 25 character
SMS 93 EMBEDDED ART
```

```
MCU restart

SMS 94
```




---

---

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


