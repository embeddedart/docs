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
Use Function **06 : Write Single Register** to change below settings.

| Parameter Name | Address | Value |
| :---:   | :---: | :---: |
| Protocol | 31 | EA = 0 <br> MODBUS = 1 |
| LED Module Count | 29   | 1-9 |
| Firmware Version | 32   |  |
| Font Type | 35   | Regular = 0 (single line) <br> Big = 1 (dual line) |
| Modbus Device ID | 41 | - |

Note : Do not modify any other address value.

---

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


