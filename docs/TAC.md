# TAC Resources

## Internet

### iPhone

#### Privacy Warning

![apple_warning](/_media/apple_privacy_warning.jpeg)

To get rid of this warning, following steps needs to be performed:

1. Go into the Settings on your Apple device and select “WiFi.”

2. Locate your active network in the list and touch the “i” icon

3. Then touch the toggle to enable “Private Address.”

With this update, your Apple device generates a unique MAC address for each network you access, so you can no longer be tracked.

If you are getting a “privacy warning” on WiFi on your device, it means that your MAC address is not being masked and the network can see your device’s address and track it.

#### Weak Security

![weak security](https://tunecomp.net/wp-content/uploads/2020/09/fix-Wi-Fi-Weak-Security-iPhone-iOS-14-1280x720.png)

To remove Weak Security Message

1. Change autentication mode to **WPA2**

2. Change encryption mode to **AES**

*If it is EG8147X6 ONT then you can choose* **WPA3**

Note: In case WPA2 and AES doesn't clear the Weak Security alert is iOS, change the authentication mode and encryption mode to **WPA/WPA2** and back to **WPA2** once again and you could also try resetting the network settings of iOS device and/or forgetting the WiFi network.




### Wifi Settings

Recommended Wi-Fi settings for HG8247H, EG8247H5 and EG8147X6 ONTs

1)	Authentication Mode

- a. 2.4 GHz: WPA/WPA2-PSK

- b. 5 GHz: WPA/WPA2-PSK

2)	Regulatory Domain:

- a. 2.4 GHz: Pakistan

- b. 5 GHz: Pakistan

3)	Channel Width

- a. 2.4 GHz: 20MHz / 40MHz (In case no neighboring SSID exist)

- b. 5 GHz: Auto (20/40/80/160MHz)

4)	 Channel

- a. 2.4 GHz: As per analysis of channels of neighboring SSIDs present. Can never be AUTO

- b. 5 GHz: Auto

5)	Band Steering

- a. Enabled

Note: For this to work, SSID name and password are set the same for 2.4 GHz and 5GHz WiFi.

image here

### 5Ghz why not 160Mhz

![uni_3](/_media/uni_3.jpeg)

Don't set channel width to Auto (20/40/80/160). 

Use Auto (20/40/80) instead.
The spectrum doesn't include 160 Mhz band. May cause no internet issues.






## Others

### Optical Powers


| Wavelength | Range                           |
|------------|---------------------------------|
| 1490       | -8 to -26                       |
| 1310       | -8 to -27 (B+)   -12 to -31 (C+) |
| 1150       | +2 to -8                        |


### Credentials

#### Phone Credentials

<table>
<thead>
  <tr>
    <th>Mode</th>
    <th>Dial</th>
    <th>Username</th>
    <th>Password</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Log in</td>
    <td>788</td>
    <td>agent number</td>
    <td>1234#</td>
  </tr>
  <tr>
    <td>Log out</td>
    <td>799</td>
    <td>agent number</td>
    <td>1234#</td>
  </tr>
</tbody>
</table>


#### Other Credentials

<table>
<thead>
  <tr>
    <th>Platform</th>
    <th>Username</th>
    <th>Password</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>CRM</td>
    <td>your.name</td>
    <td>123456</td>
  </tr>
  <tr>
    <td>NCE</td>
    <td>your.name</td>
    <td>123456</td>
  </tr>
  <tr>
    <td>Queue</td>
    <td>tac</td>
    <td>t@Cl0G!n1</td>
  </tr>
  <tr>
    <td>Mail</td>
    <td>your.name@nayatel.com</td>
    <td>pak@123</td>
  </tr>
  <tr>
    <td>NMS</td>
    <td>nayatel</td>
    <td>N@y@te123456</td>
  </tr>
  <tr>
    <td>WiFi</td>
    <td>Hardware 5Ghz</td>
    <td>Test@1234</td>
  </tr>
  <tr>
    <td>Knowledge</td>
    <td>tac</td>
    <td>Int3rnal</td>
  </tr>
</tbody>
</table>


### Escalation for Systems

![systems_escalate](/_media/systems_escalate.jpeg)

### UPS Status

<table>
<thead>
  <tr>
    <th colspan="2">UPS Status</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>No light</td>
    <td>UPS is fully charged</td>
  </tr>
  <tr>
    <td>CHG</td>
    <td>UPS is Charging</td>
  </tr>
  <tr>
    <td>DIS</td>
    <td>UPS is Discharging (Switch is off or power adapter unplugged)</td>
  </tr>
  <tr>
    <td>ALA</td>
    <td>Alarm (UPS is probably faulty)</td>
  </tr>
</tbody>
</table>

### Visit Timings

#### Normal Customer

**Complaints**

6-8 HOURS

---

**Cabling**

5-7 DAYS

---

**Relocation (same premises)** 

4-5 DAYS

---

**Shifting** 

up to 8 DAYS

#### 1 Star Customer

**Complaints**

4 HOURS

#### 2 Star Customer

**Complaints**

3 HOURS

#### 3 Star Customer

**Complaints**

2 HOURS

:::tip Pro tip

Always convey VAS charges to the customer

:::


![teamvisit](/_media/teamvisit.jpeg)


### Telemarketing

📞To block telemarketing communication, register your number on the Do not Contact Register (DNCR)

- SMS 'Reg' to 3627.

📨 To block spamming, type spammer's number, give a space, paste the received message & SMS to 9000.

❓To block obnoxious/unknown calls and SMSs, dial *420# (for Jazz, Telenor and Ufone subscribers) or 420 (for Zong subscribers)

![telemarketing](/_media/telemarketing.jpeg)


### BRAS Nodes

![bras image](/_media/ip_nodes.jpeg)

F11 58.65.175.242


F POP 58.65.175.251


MT 58.65.175.240


SADDAR 58.65.175.252


FSD 58.65.175.248


PSH 58.65.175.45


GRW 58.65.175.8



### Cabling

User wants cabling

### Forward Traces

- Go to BRAS
- Do WG IP NAT
- Grab that IP
- Open ONT
- take forward trace ???



### WINMTR

For mac its Ping Plotter

### Which Team to forward TT

Which Cabling/Installation team to forward specific ticket?

1. Use Area Lead Time Module https://crm.nayatel.com/views/crmViews/nayatelCrm/EInstallation/perAreaLeadTime.php

![Team1](/_media/Team1.jpeg)

2. For escalation, use Employee Reporting Module https://crm.nayatel.com/views/crmViews/nayatelCrm/employeeInfoRpt.php

![Team2](/_media/Team2.jpeg)

### ONT Specs

![Ontspecs](/_media/ont_specs.jpeg)

### FAULT TYPES

Another fault types added.

Fault Type :                        Hanging
Sub Fault Types :              Outdoor cable re-routing
Optical fiber cable at low height
Optical fiber cable fell on road
Cable Cut

Fault Type :                        Installation
Sub Fault type :                 BPR down

Please use Installation - BPR Down in case of NAP/BPR has fallen from the pole. Forward such tickets to concerned Installation team.



### PC support 5Ghz

For PC/Laptop 5GHz Support: https://grok.lsu.edu/article.aspx?articleid=17341

netsh wlan show drivers 

### Phones support 5Ghz

http://support.heartv.com/miscellaneous/5ghz-devices


### Billing

Billing stays from 9am till 8pm , Sundays are off (Mon-Sat)

### Useful Links

[**Traceroute**](https://ping.eu/traceroute/) - [**Port Check**](https://traceroute.eu/port-chk/) 


