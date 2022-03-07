[ <-- Back to Index](README.md)
# Commands I still have to document

- AT+CPBF, AT+CPBR and other phone book entry commands
- AT+CPIN, AT+CPWD and other PIN/password commands
- AT+CREG
- AT+CRSM
- AT+COPN
- AT+COPS
- AT+CCLK and correlated. (clock)
- Sim card commands
- SMS commands
- HTTP/HTTPS commands







---
### Get SIM Card Presence (SIM Card inserted?)
```
AT+CSMINS?
```
Return:
```
+CSMINS: 0,1
```

---
### Get SIM Card Access
```
AT+CPIN?
```
Return :
```
+CPIN: READY
```
Result:

- READY - Not pending for any password
- SIM PIN - Waiting SIM PIN to be given
- SIM PUK - Waiting for SIM PUK to be given
- PH_SIM PIN - Waiting phone to SIM card (antitheft)
- PH_SIM PUK - Waiting for SIM PUK (antitheft)

---
### Enter PIN
```
AT+CPIN=<pin>
```
Return :
```
OK
```
Set the password necessary before it can be operated
(SIM PIN, SIM PUK, PH_SIM PIN, etc)

---
### Get MSISDN (Phone Number)
```
AT+CNUM
```
Return:
```
+CNUM: "","+0011222222222",145,0,4
```

---
### Get SIM Card IMSI
```
AT+CIMI
```
Return:
```
123456789012345
OK
```

---
### Get SIM Card Prefered Operators
```
AT+CPOL?
```
Return:
```
+CPOL: 1,2,"72207"
+CPOL: 2,2,"74807"
+CPOL: 3,2,"73002"
+CPOL: 4,2,"71606"
+CPOL: 5,2,"732123"
+CPOL: 6,2,"73402"
+CPOL: 7,2,"74000"
+CPOL: 8,2,"70403"
+CPOL: 9,2,"70604"
+CPOL: 10,2,"710300"
+CPOL: 11,2,"714020"
+CPOL: 12,2,"33403"
+CPOL: 13,2,"26207"
+CPOL: 14,2,"26208"
+CPOL: 15,2,"23410"
+CPOL: 16,2,"23106"
+CPOL: 17,2,"23002"
+CPOL: 18,2,"21407"
+CPOL: 19,2,"27211"
+CPOL: 20,2,"71204"
OK
```

---
### Get SIM Card Operator
```
AT+CNUM
```
Return:
```
+COPS: 0,0,"72411"
OK
```

---
## Playing Arround =)
  
---
### Get GPRS Location
```
AT+SAPBR=3,1,"Contype","GPRS"
AT+SAPBR=3,1,"APN","zap.vivo.com.br"
AT+SAPBR=1,1
AT+CIPGSMLOC=1,1
AT+SAPBR=0,1
```
Return:
```
OK
OK
OK
+CIPGSMLOC: 0,-12.345678,-12.345678,2022/02/23,13:08:00
OK
```
  
---
### Get GPRS Timestamp
```
AT+SAPBR=3,1,"Contype","GPRS"
AT+SAPBR=3,1,"APN","zap.vivo.com.br"
AT+SAPBR=1,1
AT+CIPGSMLOC=2,1
AT+SAPBR=0,1
```
Return:
```
OK
OK
OK
+CIPGSMLOC: 0,2022/02/23,13:05:19
OK
```

---
### HTTP Get
```
AT+SAPBR=3,1,"Contype","GPRS"
AT+SAPBR=3,1,"APN","zap.vivo.com.br"
AT+SAPBR=1,1
AT+HTTPINIT
AT+HTTPPARA="CID",1
AT+HTTPSSL=0
AT+HTTPPARA="UA","SIM800 IOT"
AT+HTTPPARA="URL","htts://www.google.com.br"
AT+HTTPDATA=256,10000
AT+HTTPACTION=0
AT+HTTPREAD
AT+HTTPTERM
AT+SAPBR=0,1
```
Return:
```

```

