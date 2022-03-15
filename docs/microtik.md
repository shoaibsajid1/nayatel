## Configure Mikrotik

### Step 1: Reset the Router
Below is official Mikrotik reset procedure
- Turn off the device power
- Hold the reset button and do not release
- Turn on the device power and wait until the USER LED labeled with “USR” starts flashing
 
![](https://cdn.discordapp.com/attachments/475611486996398121/953329088469282826/Page-2-Image-1.png)

- Now release the button to clear configuration
- Wait for a few minutes for the router to clear and restore the factory settings


### Step 2: Update the Router Firmware
Update procedure for the Mikrotik router is mentioned below. Internet access is required since the firmware is downloaded over the web.
- Go to Systems>Packages
- Press **Check for Updates** button

![](https://cdn.discordapp.com/attachments/475611486996398121/953329088834199562/Page-3-Image-2.png) 

- Once the updated version is displayed press the Download and Install button
- The Mikrotik router should display a progress bar which is showing percentage of firmware downloaded and after completion it will restart
- Internet is to be disconnected after firmware has been updated

### Step 3: The Security setting
Following are the things I highly recommend while configuring a Mikrotik router. These steps should be performed with the router disconnected from the internet
- In IP>DNS Allow Remote Requests should be disabled

![](https://cdn.discordapp.com/attachments/475611486996398121/953329089136164864/Page-4-Image-3.png)

- In IP>Firewall all the drop rules and fasttrack rule is to be disabled to allow remote access
 
![](https://cdn.discordapp.com/attachments/475611486996398121/953329089404629053/Page-5-Image-4.png)



- In IP>Firewall>Service all ports are to be disabled by pressing the button marked “D”
 

![](https://cdn.discordapp.com/attachments/475611486996398121/953329089639489626/Page-6-Image-5.png)


- In IP>Services telnet port is to be set to 2323, winbox should be left enabled with default port 8291 and web port is to be set to 8080 while the remaining ports are to be disabled
 
![](https://cdn.discordapp.com/attachments/475611486996398121/953329089916338186/Page-7-Image-6.png)

- In IP>Web Proxy should be disabled (Enabled should be unchecked)
 
![](https://cdn.discordapp.com/attachments/475611486996398121/953329090214101052/Page-8-Image-7.png)

- In System>Password set the router password as **N<NTL #><User ID>**
Note: The IP Pool is to be configured against the “**bridge 1**” interface in IP>Addresses instead of “**ether-2 master**” in the updated firmware 6.42.x

![](https://cdn.discordapp.com/attachments/475611486996398121/953329090511917106/Page-8-Image-8.png)

<h1 align="center"> MikroTik RB750 </h1>

### Technical Details

Mikrotik is the most feature enriched router available in market. Following are the technical details of Mikrotik RB750r2
Features:

> - IP Pool support because of Source and destination based NAT
> - Filtering by IP address, address range, port, port range, IP Protocol and many more
> - VRF, RIP, OSPF, BGP, MPLS and policy based routing support
> - IPsec p2p tunneling and 802.1q support

### Limitation:
> - 4x100Mbps Ethernet ports
> - No WLAN support in this model

### Deployment

The main reason for deploying MikroTik router was IP Pool configurations. Previously we used the TP-link routers with DD-WRT firmware to enable multi-natting since the stock firmware lacked this feature. Recently, this firmware started causing frequent disconnections due to which the DD-WRT solution was discontinued and MikroTik router was introduced


### Security

First things first, we need to secure this router because, if compromised, it has the capability to destabilize the economy. (Not kidding)

1. Access the router

2. Go to System > Password
3. Initially, no password is set so leave the old password field blank and set a new strong password. Hit apply (User is always admin)
4. Go to IP > Services

5. Disable all the services except **www** and **telnet**

6. Change the port of **www** to **8888** by clicking it and change the telnet port to **2324**

7. Now telnet the router using the above port and password

8. Copy the below lines and press **enter**:

```
/ip neighbor discovery-settings set discover-interface-list=none
/tool bandwidth-server set enabled=no
/ip dns set allow-remote-requests=no
/ip proxy set enabled=no
/ip socks set enabled=no
/ip upnp set enabled=no
/ip cloud set ddns-enabled=no update-time=no
```

Hopefully, we will not see any issue of additional usage after these settings. 


### Basics
The basic configuration of the router is as follows
1. **Ether1** is used as **WAN** port
2. **Ether 2-5** are used as **LAN** ports

## Bridge

Bridge interface is used to replicate single configurations on multiple interfaces. It is not a physical interface, rather a virtual interface which consists of multiple physical interfaces. By default, 1 bridge interface is already created and ether 2-5 are added in this bridge. By doing so, we can simply assign 192.168.88.0/24 on the bridge interface and enable DHCP, and the ports Ether2-5 will automatically start assigning IP addresses via DHCP to any device. We would not need to manually configure DHCP on all of the interfaces. 
Below mentioned are the steps required to configure a bridge interface
1.  Access the router
2. Select Bridge on the left side
3. Click on Add new

![](https://cdn.discordapp.com/attachments/475611486996398121/953337160734474371/Page-4-Image-9.png)

4. You can give any name to this bridge. In the image I have named it Test Bridge.
5. Leave the rest of the settings as they are and click OK.
6. A new bridge is configured are seen in the images below
 
![](https://cdn.discordapp.com/attachments/475611486996398121/953337161170690088/Page-5-Image-12.png)

Now the bridge interface is created, we will proceed to add ports into it. To do so, follow the below steps


1. Go to Bridge on left side
2. On the top, select Ports and click add new

![](https://cdn.discordapp.com/attachments/475611486996398121/953337161493667890/Page-5-Image-13.png)

3. From the interface option, select the interface name from the drop-down menu (Ether2, Ether3 etc.) 
4. From the Bridge option, select the bridge in which you want to add this interface
5.  Leave the rest of the settings as is and click OK.

![](https://cdn.discordapp.com/attachments/475611486996398121/953337161762095204/Page-6-Image-16.png)

Once done, the selected port will be shown as the member of the selected bridge

![](https://cdn.discordapp.com/attachments/475611486996398121/953337162110206033/Page-6-Image-17.png)

Similarly, to remove any port from the bridge, just click on the - sign.

> NOTE: A port which is not a part of any bridge will act as an independent port and will not replicate any configurations. Configurations will be required on this port separately. Such ports are useful to be used as WAN ports (Example: Ether1)

## PPPoE

To configure PPPoE on MikroTik please follow the below mentioned steps
1. Access the Router
2. Select Quick Settings
3. Set **Address Acquisition** to **PPPoE**
4. Enter PPPoE User and Password
5. Set the LAN IP address which in this case is 192.168.88.1
6. Set the subnet mask
7. Check **DHCP Server** Set 
8. DHCP range
9. Check **NAT**
10. Refer to the image

![](https://cdn.discordapp.com/attachments/475611486996398121/953337162605162556/Page-7-Image-20.png)

## IPoE

To configure IPoE on MikroTik please follow the below mentioned steps
1. Access the Router
2. Select Quick Settings
3. Set **Address Acquisition** to **Static**
4. Enter IP address and Gateway
5. Select subnet Mask
6. Set the LAN IP address which in this case is 192.168.88.1
7. Set the subnet mask
8. Check **DHCP Server**
9. Set DHCP range
10. Check **NAT**
11. Refer to the below image

![](https://cdn.discordapp.com/attachments/475611486996398121/953337163062329384/Page-8-Image-23.png)

## IP Pool

In order to route an IP Pool (115.186.188.80/30) in a MikroTik router, below mentioned steps are to be performed.
First, we have to specify the IP Pool in the IP address list of router. Below mentioned are the steps:

1.	Add the pool by going to IP > Addresses > Add New 
2.	First usable IP (in the example shown, it will be 115.186.188.81) will be entered in the Address field along with the subnet mask as shown in the image
3.	The network address will be mentioned in the network field
4.	The interface should be the LAN interface of the router since the IP Pool is always configured on the LAN side. In the example it is Test Bridge. 

> NOTE: If we select the bridge interface, the IP Pool will be available on all the ports in the bridge. In case customer specifically wants to run the IP Pool on a single port, we will first remove that interface from the bridge and will select it in the interface tab.


![](https://cdn.discordapp.com/attachments/475611486996398121/953337163431411722/Page-9-Image-26.png)

### Method 1

1. Go to IP > Firewall > NAT > Add New
2. Set chain to srcnat in the drop-down list
3. Set Src. Address to the Useable IP (in this case 115.186.188.82) of the IP pool. This is the IP that will be directly assigned to any machine in the LAN side to make it live
4. Set the out interface to the gateway or exit interface through which the traffic will flow towards ISP. In case of Premium, it will be Ether-1, in case of PPPoE (Connect), it will pppoe-out1


![](https://cdn.discordapp.com/attachments/475611486996398121/953337163683098624/Page-10-Image-29.png)

5. Scroll down to Action tab and set Action to src-nat
6. Fill the To Addresses with the same IP address written in the Src. Address field above. 
7. Hit Apply to save the configuration

![](https://cdn.discordapp.com/attachments/475611486996398121/953337163947335790/Page-11-Image-32.png)

> Note: Multiple One to One Nat Mappings are needed in case of more than 1 useable IPs.

### Method 2

1. Go to IP > Firewall > NAT > Add New
2. Set chain to **srcnat** in the drop-down list
3. In the Src-Address field, add the complete network address including subnet as mentioned below
4. Set the out interface to the gateway or exit interface through which the traffic will flow towards ISP. In case of Premium, it will be Ether-1, in case of PPPoE (Connect), it will pppoe-out1

![](https://cdn.discordapp.com/attachments/475611486996398121/953337243752341534/Page-12-Image-35.png)


5. Scroll down to Action tab and set **Action** to **same**
6. Fill the **To** Addresses with the same network written in the Src. Address field above. 
7. Check the field Not by Dst.
8. Hit Apply to save the configuration

![](https://cdn.discordapp.com/attachments/475611486996398121/953337243987218453/Page-12-Image-36.png)


By using the above method, we can configure any subnet with only one rule, therefore multiple mappings will not be required. 
Once the rule is applied, it will be shown in the list. Drag this rule and place it on the top of the list. Same should be done with all the mappings.
The default “masquerade” rule should be kept at the bottom otherwise this rule will always trigger first and the IP Pool will not work


## Port Fowarding (Microtik)

For port forwarding on Mikrotik router, follow the below mentioned steps.

1.	Access the router
2.	Go to IP > Firewall > NAT


![](https://cdn.discordapp.com/attachments/475611486996398121/953337244259856474/Page-13-Image-39.png)


3.	Click on Add New and a new window will appear
4.	Set **Chain** to **dstnat**
5.	Set protocol to **6 TCP** or **TCP**
6.	Set **Destination port** to the External Port which in this case is 3389
7.	Select the **In interface** as the PPPOE dialer interface which in this case is pppoe-out1
8.	Refer to the below image


![](https://cdn.discordapp.com/attachments/475611486996398121/953337244784140308/Page-14-Image-42.png)


9.	Now scroll down to **Action**
10.	Select **Action** to **dstnat**
11.	Set **To** Addresses to the LAN side IP address of the machine which in this case is **192.168.88.205**
12.	Set **To** Ports to the Internal port which in this case is **3389**
13.	Refer to the below image

![](https://cdn.discordapp.com/attachments/475611486996398121/953337245149069352/Page-15-Image-45.png)


## Per IP Bandwidth Restriction

In order to set per IP BW restriction kindly follow the below mentioned steps

1.	Log into the router
2.	Select Queues tab
3.	Click on Add new
4.	Set Target to the LAN IP of the PC/Laptop whose Bandwidth you want to restrict
5.	Set the Upload and Download limit and click on OK
6.	Same can be done for multiple IPs in the LAN side
7.	Refer to the image below

![](https://cdn.discordapp.com/attachments/475611486996398121/953337245375533117/Page-15-Image-46.png)

## Secondary DHCP Server

- Go to IP -> Addresses -> Add new

![](https://cdn.discordapp.com/attachments/475611486996398121/953352828519329882/Page-2-Image-1.png)

- Define network in `Address` field with 1st useable address with / CDR.
- Define network ID (1st IP of the pool) in `Network` field.
- Select interface on which this DHCP server will run under `Interface` field.
- Click `OK` button.

![](https://cdn.discordapp.com/attachments/475611486996398121/953352828938747914/Page-3-Image-2.png)

- Go to IP -> Pool -> Add New

![](https://cdn.discordapp.com/attachments/475611486996398121/953352829161050152/Page-4-Image-3.png)

- Define start and end IPs of the pool that is to be assigned by DHCP server in Addresses filed.
- Select `none` for Next Pool
- Click on `OK` button.

![](https://cdn.discordapp.com/attachments/475611486996398121/953352829379158036/Page-5-Image-4.png)

- Go to IP -> DHCP Server -> Add New

![](https://cdn.discordapp.com/attachments/475611486996398121/953352829639229500/Page-6-Image-5.png)


- Select interface other than Ethernet interface for primary DHCP server
- Select lease time as per requirement
- Select Address Pool which was created under IP -> Pool for this DHCP server
- Click on `OK` button.

![](https://cdn.discordapp.com/attachments/475611486996398121/953352829878284348/Page-7-Image-6.png)

- Go to IP -> DHCP Server -> Networks ->Add New

![](https://cdn.discordapp.com/attachments/475611486996398121/953352830180266054/Page-8-Image-7.png)

- Write Network Address of LAN network with CIDR in Address field.
- Gateway of Network in Gateway field.
- Keep Netmask as `0`
- Write Nayatel DNS server address in DNS Servers field or leave it blank.
- Click on `OK` button.

![](https://cdn.discordapp.com/attachments/475611486996398121/953352830406762596/Page-9-Image-8.png)

- Go to `Interfaces` -> Double click on Ethernet interface selected for secondary DHCP server.

![](https://cdn.discordapp.com/attachments/475611486996398121/953352830629072956/Page-10-Image-9.png)

- Select Master Port as `none`
- Click on `OK` button.

![](https://cdn.discordapp.com/attachments/475611486996398121/953352895561076796/Page-11-Image-10.png)

- Now any network with Ethernet connection to this Ethernet port will be assigned IP from this secondary configured DHCP Server
 
![](https://cdn.discordapp.com/attachments/475611486996398121/953352895825330196/Page-11-Image-11.png)

![](https://cdn.discordapp.com/attachments/475611486996398121/953352896039231488/Page-12-Image-12.png)