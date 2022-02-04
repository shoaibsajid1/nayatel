# NOC


## To find the link

```
show interfaces descriptions  | match ACBLOPF
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939117760666017812/Screen_Shot_2022-02-03_at_10.47.12_PM.png)

## To check the interfaces details

```
show interfaces ae141.911   
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939117760359845918/Screen_Shot_2022-02-03_at_10.25.16_PM.png)

## To find MAC address

```
 show arp interface ae141.911
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939117760980582400/Screen_Shot_2022-02-03_at_10.48.46_PM.png)

## To find the interface on which user ID is configured 

```
 show configuration interfaces ae141.911 | display set 
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939117761198714970/Screen_Shot_2022-02-03_at_10.50.21_PM.png)

## To check route instance 

```
 show route instance acblopf  
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939117761769115668/Screen_Shot_2022-02-03_at_10.51.35_PM.png)

## To see routing table

```
show route table acblopf.inet.0
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939117762318594048/Screen_Shot_2022-02-03_at_10.52.47_PM.png)

## To ping any IP in the routing table

```
ping routing-instance acblopf 192.168.13.202
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939117762595405854/Screen_Shot_2022-02-03_at_11.22.52_PM.png)

## To find out xconnect group detail 

```
show bridge domain ALAZIZHOME_L2VPN_POINTB
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939139516353118268/Screen_Shot_2022-02-04_at_5.44.30_PM.png)

## To check IP Pool information

```
show configuration routing-options static | match 103.55.70.158
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939117762964492328/Screen_Shot_2022-02-03_at_11.23.52_PM.png)


<h1> PPPoE </h1>

## Mac lockout

```
show pppoe lockout
<underlying-interface-name>
```
![noc]()

## Clear lockout

```
clear pppoe lockout mac-address 00:00:5e:00:53:30
```

## Description of BGP neighbor 

```
show bgp neighbor 203.99.57.22 
```
![noc]()

## Description of interfaces

```
show running-config interface GigabitEthernet0/4
```
![noc]()