---
title: "LED Display Control Card"
linkTitle: "LED Display Control Card"
weight: 1
description: >
  LED Display Control Card
---

<!--
{{% pageinfo %}}
This is a placeholder page that shows you how to use this template site.
{{% /pageinfo %}}
-->


# MODBUS Configuration:



#### Comport Setting : 
* Baudrate : 9600
* Databits : 8
* Parity   : None
* Stopbits : 1

---
#### Function Code : 0x06
Use Function **06 : Write Single Register** to change below settings.

| Parameter Name | Address | Value |
| :---:   | :---: | :---: |
| LED Module Count | 29   | 1-9 (auto save) |
| X Offset | 30   | 0 (must be zero) |
| Protocol | 31 | EA = 0 <br> MODBUS = 1 <br> (auto save)|
| Firmware Version | 32 | - |
| Restart Controller | 33 | - |
| Font Type | 35   | Regular = 0 (single line) <br> Big = 1 (dual line) |
| Brightness | 36   | TBD |
| Baudrate | 37 | *see below |
| Data Bits | 38 | 7 = 7 Data Bits <br> 8 = 8 Data Bits <br> 9 = 9 Data Bits  |
| Parity | 39 | 0 = None <br> 1 = Odd <br> 2 = Even |
| Stop Bits | 40 | 1 = 1 Stop Bits <br> 2 = 2 Stop Bits |
| Modbus Device ID | 41 | - (auto save) |
| Save Setting | 42 | 1 |
| Reset Swtich Status | 43 | 0 = switch pressed (read only) |
| Response Time | 44 | 0 (must be zero) |


#### Baudrate Setting:
0 = 300 <br> 
1 = 600 <br> 
2 = 1200 <br> 
3 = 2400 <br> 
4 = 4800 <br> 
5 = 9600 <br> 
6 = 14400 <br> 
7 = 19200 <br> 
8 = 28800 <br> 
9 = 38400 <br> 
10 = 56000 <br> 
11 = 57600 <br> 
12 = 115200 <br> 
13 = 128000 <br> 
14 = 256000 <br> 
other = 9600 <br> 
	
Note : Do not modify any other address value.

---
#### Function Code : 0x10
Use Function **16 : Write Multiple Registers** to write data on display

Line 1 start adress = 1000  
Line 2 start adress = 2000

---











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


