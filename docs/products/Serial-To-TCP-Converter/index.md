---
title: "Serial To TCP Converter"
linkTitle: "Serial To TCP Converter"
weight: 1
description: >
  Serial To TCP Converter convert serial RS485 data to TCP and vice versa.
---

<!--
{{% pageinfo %}}
This is a placeholder page that shows you how to use this template site.
{{% /pageinfo %}}
-->

### Default Setting
DEVICE IP   : 192.168.0.213  
SUBNET IP   : 255.255.255.0  
GATEWAY IP  : 192.168.0.1  



## Setting Command from LAN
```
Send      : %{,??,INFO,}!
Response  : 

```

---


```
DHCP Enable/Disable:
Set       : %{,??,TBL,5,1,ENABLE/DISABLE,}!

            %{,??,TBL,5,1,1,}!		// ENABLE = 1
            %{,??,TBL,5,1,0,}!		// DISABLE = 0

Get       : %{,??,GETTBL,5,1,}!
Response  : <<,13,GETTBL,5,1,1~,>>{0D}{0A}
```

```
Device IP:
Set       : %{,??,TBL,6,4,192~168~1~101~,}!
            IP = 192.168.1.101

Get       : %{,??,GETTBL,6,4,}!
Response  : <<,13,GETTBL,6,4,192~168~1~206~,>>{0D}{0A}
```

```
DNS IP:
Set       : %{,??,TBL,11,4,8~8~8~8~,}!
            IP = 8.8.8.8

Get       : %{,??,GETTBL,11,4,}!
Response  : <<,13,GETTBL,11,4,8~8~8~8~,>>{0D}{0A}
```

```
Gateway IP:
Set       : %{,??,TBL,16,4,192~168~1~1~,}!
            IP = 192.168.1.1

Get       : %{,??,GETTBL,16,4,}!
```

```
Subnet IP:
Set       : %{,??,TBL,21,4,255~255~255~0~,}!
            IP = 255.255.255.0

Get       : %{,??,GETTBL,21,4,}!
```

```
MAC ID:
Set       : %{,??,TBL,55,6,234~14~10~0~0~1~,}!
            MAC Address = EA:0E:0A:00:00:01

Get       : %{,??,GETTBL,55,6,}!
```

```
Device Server Port Number

Set       : %{,??,PORT,26,2,1234,}!
           
Get       : %{,??,GETPORT,26,2,}!
Response  : <<,13,GETPORT,26,2,1234,>>{0D}{0A}
```

```
Restart MCU

Set       : %{,??,RSTMCU,}!

Note      : Do Not Use This Command.
```

Note : Hold reset switch for 5 seconds while device boot to reset setting.

## Documents

<p>Open a <a href="IP_Finder.exe"  target="_blank">IP Finder</a></p>


---


