[ <-- Back to Index](README.md)
# SIM Card Commands
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
