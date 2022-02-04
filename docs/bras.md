
## NODES

<table><thead><tr><th>Location</th><th>IP</th><th>Port</th></tr></thead><tbody><tr><td>F11</td><td>58.65.175.242</td><td>22</td></tr><tr><td>FPOP</td><td>58.65.175.241</td><td>22</td></tr><tr><td>SDR</td><td>58.65.175.252</td><td>22</td></tr><tr><td>MT</td><td>58.65.175.240</td><td>2002</td></tr><tr><td>FSD</td><td>58.65.175.248</td><td>22</td></tr><tr><td>PSH</td><td>58.65.175.45</td><td>22</td></tr><tr><td>GRW</td><td>58.65.175.8</td><td>2002</td></tr><tr><td>SGD</td><td>58.65.175.9</td><td>2002</td></tr></tbody></table>

## Connected to BRAS

```
show subscribers user-name ridaali
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939145677961850910/Screen_Shot_2022-02-04_at_6.08.46_PM.png)

## Link Utilization

```
show interfaces extensive pp0.3221288579 
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939145879762403358/Screen_Shot_2022-02-04_at_6.09.19_PM.png)

## Logout customer

```
clear network-access aaa subscriber username salmanzia
```

## Check authentication

```
test aaa ppp user salmanzia password Ntl@67682
```
![noc](https://cdn.discordapp.com/attachments/389455820741541893/939146325210050640/Screen_Shot_2022-02-04_at_6.12.00_PM.png)

