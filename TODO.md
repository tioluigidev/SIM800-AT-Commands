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

