---
title: "Python PyQt GUI"
linkTitle: "Python PyQt GUI"
date: 2023-08-02
author: Brijesh Khokhar ([@khokhar_brijesh](https://twitter.com/khokhar_brijesh))
description: >
  Python PyQt GUI related command and details
---


install pyqt6 package:
```
pip install PyQt6
```
install the pyqt6-tools package that contains the Qt Designer and other related tools:
```
pip install pyqt6-tools
```
The pyqt-tools package will install the Qt Designer in the following location:
```
c:\application\venv\Lib\site-packages\qt6_applications\Qt\bin
```
execute the pyuic6 command (within the pyqt6-env virtual environment) to check the version:
```
pyuic6 -V
```
<br>
#### Converting .ui file to Python code command
```
pyuic6 -x tcp_utility_gui.ui -o tcp_utility_gui.py
```








---
