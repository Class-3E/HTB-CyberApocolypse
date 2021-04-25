# Compromised

>An embedded device in our serial network exploited a misconfiguration which resulted in the compromisation of several of our slave devices in it, leaving the base camp exposed to intruders. We must find what alterations the device did over the network in order to revert them before its too late

downloaded Logic-2.3.26-master.AppImage and opened the file (.sal) then clicked F1 button on the right and choosed channel 0 and 1 then the data apeared

![](https://i.imgur.com/ulBIkwG.png)

```
write to 0x34 ack data: 0x73 
write to 0x34 ack data: 0x65 
write to 0x34 ack data: 0x74 
write to 0x34 ack data: 0x5F 
write to 0x34 ack data: 0x6D 
write to 0x34 ack data: 0x61 
write to 0x2C ack data: 0x43 
write to 0x34 ack data: 0x78 
write to 0x2C ack data: 0x48 
[...]
```
this is the output if we get all the data of all adresses (0x34, 0x2C, 0x04) and decode it from hex

>set_maCxH_lTimB{itn_tuo1:110_se73t_2mimn1_nli4mi70t_2to5:

so if the 7th pos is C which is the begining of the flag BUT has address 0x2C, so i filtered by that adress by the below script and that gave the flag

```
f = open("addresses.txt", "r")
f2 = open("data.txt", "r")
Lines = f.readlines()
Lines2 = f2.readlines()
i=0
for i in range(len(Lines)):
	if Lines[i] == "0x2C\n":
		print(Lines2[i])
```
* addresses.txt contained the addresses column from the above text
* data.txt contained the data column from the above text

>CHTB{nu11_732m1n47025_c4n_8234k_4_532141_5y573m!@52)#@%}

[BL4CKC0FF33 ☕](https://github.com/BL4CKC0FF33/)
