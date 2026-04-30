# Dji Neo2_battery
Reverse engineering of dji Neo 2 battery

# IC founded:
*	4× VS 2R5N03M: sezione di switching/protezione della batteria.
*	Z2401 2451S28: probabile main chip
*	QFN-32 sul retro: IC di gestione/controllo.

![alt text](./media/bms_neo2.png)

# Pin Out:
(- - D + +)
![alt text](./media/pinout.png)

# Battery:
* 2x Ampace HKA530CG03C1 1.606aH 3,7v
* (55 x 30 x 0,55 mm) ±

![alt text](./media/battery.png)

# Comunication:
* Il pin D del bms del Neo 2 è una  linea dati proprietaria single-wire ~55 kHz protocollo DUML V1 (il drone invia request, il bms risponde con dati codificati nei tempi).
  
* CMD Founded:
  
| CMDSET/CMDID | #Description|
| ------- | --- |
|  0x0D/0x02 | Stato batteria (tensione, corrente, temp) |
|  0x0D/0x03 | Stato batteria (tensione celle) |
|  0x0D/0x04 | SerialNumber |
|  0x00/0x01 | Device info / FW version |
