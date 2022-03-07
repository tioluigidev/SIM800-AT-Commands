[ <-- Back to Index](README.md)
# Modem Information
### Get Manufacturer Identification
```
AT+GMI
```
Return:
```
SIMCOM_Ltd

OK
```

---
### Get Manufacturer Identification Number
```
AT+CIMI
```
Return:
```
724112909681804

OK
```

---
### Get Model Identification
```
AT+GMM or AT+CGMM
```
Return:
```
SIMCOM_SIM800L

OK
```

---
### Get Product Identification Information
```
ATI
```
Return:
```
SIM800 R14.18

OK
```

---
### Get Global Object Identification
```
AT+GOI
```
Return:
```
SIM800

OK
```

---
### Get Firmware Identification Revision
```
AT+GMR or AT+CGMR
```
Return:
```
Revision:1418B05SIM800L24

OK
```

---
### Get Modem Serial Number Identification (IMEI)
```
AT+GSN or AT+CGSN
```
Return:
```
012345678901234

OK
```
---
### Set Factory Defined Configuration
```
AT&F
```
Return:
```
OK
```
Set all current parameters to the manufacturer defined profie.
This command does not reset the modem. This is about the operating profile.

---
### Antenna Detection
Command:
```
AT+CANT=1,1,1
```
Return:
```
OK

+CANT: 2

+CANT: 2

+CANT: 2

...
```
Command:
```
AT+CANT=0,0,0
```
Return:
```
OK
```
Results:

- +CANT: 0 - Connected Normally
- +CANT: 1 - Connected to GND
- +CANT: 2 - Connected to other power source
- +CANT: 3 - Not connected

---
### Get Signal Quality
```
AT+CSQ
```
Return:
```
+CSQ: 14,0
```
Result (first number):

| Signal | CSQ | dBm | Signal Strengh            | Quality |
  | :--- | :--- |:--------------------------| :--- | :--- |
| 1 | 0 to 4 | -110 to -106| 0 to 11 %                 | Bad |
| 2 | 5 to 9 | -105 to -96 | 12 to 28 %                | Marginal |
| 3 | 10 to 14 | -95 to -84 | 29 to 47 %                | OK |
| 4 | 15 to 18 | -83 to -76 | 48 to 60 %                | Good |
| 5 | 19 to 31|-75 to -50 | 61 to 100 %               | Excelent |
|  | 99 | | Unknown or not detectable | | 

---
### Enable Jamming Detection in Query Mode
```
AT+SJDR=1,0
```
Return:
```
OK
```

---
### Get Radio Status (Jamming Detection)
```
AT+SJDR?
```
Return:
```
+SJDR: 1,0,255,0,0
```
Result:
The 3rd number is the signal strength variance. Default is 255. In addition to 'OK', the following messages may appear:
- +SJDR: JAMMING DETECTED
- +SJDR: INTERFERENCE DETECTED
---

### Set Phone Functionality
```
AT+CFUN=1,1
```
Return:
```
OK
```
Usage:
AT+CFUN=Functionality,Reset

Functionality parameter:

- 0 = Minimum functionality
- 1 = Full functionality (Default)
- 4 = Disable phone both transmit and receive RF circuits

Reset parameter:

- 1 = Reset modem before setting to Functionality parameter power level.

Notes:

- AT+FUN=1,1 can be used to reset module purposely at minimum/full functionality mode.
- Minimum functionality mode (AT+CFUN=0) and RF disabled functionality mode (AT+CFUN=4) cannot be switched to each other.

**Examples**:

Command:
```
AT+CFUN=0
```
Result:
```
+CPIN: NOT READY

OK
```
Command:
```
AT+CFUN=1
```
Result:
```
+CPIN: READY

OK

SMS Ready

Call Ready
```
Command:
```
AT+CFUN=4
```
Result:
```
OK
```
Command:
```
AT+CFUN=1
```
Result:
```
OK
```
Command:
```
AT+CFUN=1,1
```
Result:
```
OK
```
