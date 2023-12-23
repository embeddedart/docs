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

# LED Status :
```
D2 = Power Red LED

D63 = Green (Network)

D62 = RED
	continuous on = connected to server
	when blink = sending data to server
```

# MQTT Configuration From Server Command :
```
To test server communication with hardware
Send : 
@@,test,##
Response : 
@@,test ok,XX,##
  - XX = any number
```

```
Time Sync Command : 
Send : 
@@,timesync,##
Response :
@@,timesync ok,XX,##
```

```
Get Device Time (Real Time)
Send : 
@@,gettime,##

```

```
To read data from modbus device and this data will sent on server.

@@,txn no, txn flag, modbus id, function code, start add, qty, poll interval, txn timeout, txn retry count,##

Send :
@@,txn,0,1,1,3,0,10,3000,1000,1,##

Response :
@@,txn ok,XX,##
```

```
@@,txnendis,txn no., enable/disable,##
@@,txnendis,0,1,##
```

```
To read txn setting :

Example :
Send :
@@,gettxn,0,##
	0 = txn no.

Response :
@@,txn,0,1,1,3,0,10,3000,1000,1,##
```

```
To read all enabled txn setting :

@@,gettxnall,##

this will reply enabled txn setting
```




```
To send modbus function code 16 command :

@@,fn16,modbus id, fn code, start add, qty,data 1, data 2, data 3,##

Example :
Send :
@@,fn16,1,16,0,3,1,2,3,##
```

```
@@,comport,baud rate, data bits, parity, stop bits,##

	parity : 0 = none
			 1 = odd
			 2 = even

@@,comport,115200,8,0,1,##
```
```
get modbus communication setting :

@@,getcomport,##
```

```

@@,getmqtt,##

@@,mqttport,1883,##

@@,mqttserver,broker.hivemq.com,##
    
@@,mqttuser,ea_test,##

@@,mqttpass,ea_test,##

@@,mqtttopicpub,ea_pub,##

@@,mqtttopicsub,ea_sub,##

@@,mqttsave,##

```





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

44 10 Mqtt_Port
44 11 MQTT_server_IP
44 12 MQTT_user_name
44 13 MQTT_Password
44 14 MQTT_publish_topic
44 15 MQTT_subscribe_topic
44 20 reconnect_to_mqtt_server
```

```
Set MQTT setting using SMS :

44 10 port_number
44 11 server_ip
44 12 user_name
44 13 password
44 15 subscriber_topic
44 14 publish_topic
```

```
NTP Time Server (SMS):

44 16 time.nist.gov
```
