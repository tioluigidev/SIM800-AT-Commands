[ <-- Back to Index](README.md)
# SIM Card Commands
### Get SIM Card Presence (SIM Card inserted?)
```
AT+CSMINS?
```
Return:
```
+CSMINS: 0,1

OK
```
Result (second number):
- 0 - SIM Card not inserted
- 1 - SIM Card inserted


---
### Get SIM Card Access
```
AT+CPIN?
```
Return :
```
+CPIN: READY

OK
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

OK
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
Result:
+CNUM: "String", "Number",Type,Speed,Service
- String - Optional alphanumeric string associated with Number used character.
- Number - Phone number (IMSI)
- Speed - As defined by AT+CBST command
- Service:
  - 0 - Asynchronous modem
  - 1 - Synchronous modem
  - 2 - PAD Access (asynchronous)
  - 3 - Packet Access (synchronous)
  - 4 - Voice
  - 5 - Fax
  
---
### Get SIM Card Preferred Operators
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
...

OK
```
Result:
+CPOL: Index,Format,Operator
- Index - Order number of operator in SIM preferred operator list.
- Format:
  - 0 - Long format alphanumeric
  - 1 - Short format alphanumeric
  - 2 - Numeric
- Operator Id

---
### Get Operator Names
```
AT+COPN
```
Return:
```
+COPN: "20201","COSMOTE"
+COPN: "20205","vodafone"
+COPN: "20209","Q-TELECOM"
+COPN: "20210","TIM"
+COPN: "20404","vodafone"
...

OK
```
---

### Get Operator
Set long alphanumeric format
```
AT+COPS=3,0
```
Return:
```
OK
```
Command
```
AT+COPS?
```
Return:
```
+COPS: 0,0,"Claro"
```

---
### Get SIM Card Operator
```
AT+CSPN?
```
Return:
```
+CSPN: "Vivo",0

OK
```
---

### Get Mobile Operation Band
```
AT+CBAND?
```
Return:
```
+CBAND: GSM850_MODE,ALL_BAND

OK
```
Result:
- EGSM_MODE
- PGSM_MODE
- DCS_MODE
- GSM850_MODE
- PCS_MODE
- EGSM_DCS_MODE 
- GSM850_PCS_MODE
- EGSM_PCS_MODE
- ALL_BAND