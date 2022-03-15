# Additional Usage

The following attributes which needs to be checked while investigating additional usage case:

- Security > Firewall It should be `standard` or `user-defined`

![Firewall](https://cdn.discordapp.com/attachments/475611486996398121/953321189793746944/Screen_Shot_2022-03-15_at_8.55.51_PM.png)

- Security > Check MAC Filtering

![](https://cdn.discordapp.com/attachments/475611486996398121/953322673977585664/Screen_Shot_2022-03-15_at_9.01.39_PM.png)

- Security > Check Wi-Fi MAC Filtering

![](https://cdn.discordapp.com/attachments/475611486996398121/953322661445001216/Screen_Shot_2022-03-15_at_9.01.47_PM.png)

- Security > Verify DoS configurations (Either all checked or as below)

![](https://cdn.discordapp.com/attachments/475611486996398121/953322828072120360/Screen_Shot_2022-03-15_at_9.04.23_PM.png)

- Security > Internet Access Control: Should be OFF

![](https://cdn.discordapp.com/attachments/475611486996398121/953322975652888646/Screen_Shot_2022-03-15_at_9.05.00_PM.png)

- Forward Rules > DMZ Function

![](https://cdn.discordapp.com/attachments/475611486996398121/953323864979542146/Screen_Shot_2022-03-15_at_9.08.16_PM.png)

- Forward Rules > IPv4 Port Mapping (Port forwarding). Mention if any exist

![](https://cdn.discordapp.com/attachments/475611486996398121/953323855043264522/Screen_Shot_2022-03-15_at_9.08.28_PM.png)

- Application > DDNS (if there is any entry)

![](https://cdn.discordapp.com/attachments/475611486996398121/953323551597928468/Screen_Shot_2022-03-15_at_9.06.01_PM.png)

- Application > UPnP: Should be disabled

![](https://cdn.discordapp.com/attachments/475611486996398121/953323566613532702/Screen_Shot_2022-03-15_at_9.05.48_PM.png)

- See Data Usage History (on CRM)

![](https://cdn.discordapp.com/attachments/475611486996398121/953326123444477962/Screen_Shot_2022-03-15_at_9.17.28_PM.png)

- Maintenance Diagnostics > User Log: Verify user logs to verify if any attacks (smurf / DOS ) are found

![](https://cdn.discordapp.com/attachments/475611486996398121/953324662765547550/Screen_Shot_2022-03-15_at_9.11.33_PM.png)

You can copy paste the log in a note pad and search for the word `attack` and copy all instances of those attacks (as seen in the screenshot as well) separately. 

If the attack is from IPs in the port forwarding entries, then there is a possibility of user security and that the usage is legit and this should be informed to the user that their network is not secure. 

However if no attacks are found then user is informed of that as well

If attacks are found of IPs not in the port forwarding entries, then it is possible that user charges be waived off. Consult Zaki bhai for final verdict.

## Example TT

> You can refer the following link to see an example of Additional usage TT and how to fill it 

https://crm.nayatel.com/views/crmViews/nayatelCrm/complaint_detatil.php?lid=waqas9783&tid=4656104&tim=1646709557


Example Extract from the above link

```
Firewall level : Standard

Mac filtering: None found

DoS: Settings verified

Internet Access Control: OFF

Forward Rules:  - No DMZ Found

- No port forwarding

DDNS: No entry

uPnP: Disabled

User logs:

Manufacturer:Huawei Technologies Co., Ltd;
ProductClass:EG8147X6;
SerialNumber:485754437473D9A4;
IP:192.168.18.1;
HWVer:229D.A;
SWVer:V5R020C00S280;

1981-01-01 00:00:33 [Critical][Config-Log] Terminal:OLT(-),Result:Success,Type:Set,Msg:Me[11] Inst[259] Att[5] Val[0]
1981-01-01 00:00:33 [Critical][Config-Log] Terminal:OLT(-),Result:Success,Type:Set,Msg:Me[11] Inst[260] Att[5] Val[0]
1981-01-01 00:00:34 [Critical][Config-Log] Terminal:OLT(-),Result:Success,Type:Set,Msg:Me[82] Inst[1025] Att[1] Val[0]
2021-04-24 13:26:14 [Critical][Run-Log] Time synchronized successfully, uptime:[47s], src:[2], app:[OMCI_PRO_Proces], pid:[1553]


ATTACKS FOUND (MOST ATTACKS ARE FROM IPs IN PORT FORWARDING ENTRIES)

2021-08-30 15:28:42 [Error][Alarm-Log] AlarmID:303500,AlarmLevel:Error,DoS attack. Type: smurf. Source IP address: 192.168.18.19. Destination IP address: 255.255.255.255. Source MAC address: 9e-9d-7e-0e-bb-88

2021-10-27 09:40:56 [Error][Alarm-Log] AlarmID:303500,AlarmLevel:Error,DoS attack. Type: smurf. Source IP address: 192.168.18.19. Destination IP address: 255.255.255.255. Source MAC address: 9e-9d-7e-0e-bb-88

2022-01-17 09:26:39 [Error][Alarm-Log] AlarmID:303500,AlarmLevel:Error,DoS attack. Type: smurf. Source IP address: 192.168.18.36. Destination IP address: 255.255.255.255. Source MAC address: 9e-9d-7e-0e-bb-88
2022-01-18 09:26:49 [Error][Alarm-Log] AlarmID:303500,AlarmLevel:Error,DoS attack. Type: smurf. Source IP address: 192.168.18.36. Destination IP address: 255.255.255.255. Source MAC address: 9e-9d-7e-0e-bb-88
2022-02-07 09:41:22 [Error][Alarm-Log] AlarmID:303500,AlarmLevel:Error,DoS attack. Type: smurf. Source IP address: 192.168.18.36. Destination IP address: 255.255.255.255. Source MAC address: 9e-9d-7e-0e-bb-88
2022-02-07 09:41:22 [Error][Alarm-Log] AlarmID:303500,AlarmLevel:Error,DoS attack. Type: smurf. Source IP address: 192.168.18.36. Destination IP address: 255.255.255.255. Source MAC address: 9e-9d-7e-0e-bb-88

LAPTOP-FLSKL7JO
SSID1
f0:9e:4a:38:11:07
192.168.18.36
```
