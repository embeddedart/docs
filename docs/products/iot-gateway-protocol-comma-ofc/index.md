
# Office Use Only :

```
device publish topic    : 	embedded_art_pub
device subscribe topic  : 	embedded_art_sub
```


# MQTT Configuration From Server Command :

```
To set device serial number :

@@,srno,123456,##

To get device serial number :

@@,getsrno,##
```




# SMS for Configuration :

```
Set MQTT setting using SMS :

SMS 44 10 1883
SMS 44 11 broker.hivemq.com
SMS 44 12 embedded_art_test_user
SMS 44 13 embedded_art_test_password
SMS 44 14 embedded_art_pub
SMS 44 15 embedded_art_sub
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


