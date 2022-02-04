# eView

## Summary

- Account Active ?
- Physical Layer (Historical Alarms, Powers) ?
- Package Assigned ?
- Live IP Assigned ?
    - if no, fault type **IP Update Issue** send to **Core**
- URL resolved ? (and matching ?)
- Login time? (ext command)
- Start packet (in Usage History)
- Port forwarding in ONT ?

---

- Check if the Account is Active and Eview Package is assigned to the user.

- Check if the physical layer is okay.

- Check if the URL is resolving and matching in command prompt. In case the URL is resolving on BRAS IP and BRAS login time is 15+, generate the ticket with the fault type: **URL Resolution** and forward to **es-support** (check the concerned team box).

- Port forwarding exists in the CPE & Ports forwarded for Dynamic IP customers are from the allowed list & Ports status checked from outside the NTL network.

- Port forwarding is done properly. In case the issue is with the Port forwarding configurations, generate the ticket with the fault type: CPE Configurations and forward to Complaints.

- DVR is accessible from LAN side ?

- VAS were conveyed to user ?

### Port forwarding

#### Video Tutorial


<iframe src="https://player.vimeo.com/video/227704967?h=f59f0efe75" width="100%" height="100%" frameborder="0" allow="fullscreen; picture-in-picture" allowfullscreen></iframe>
<p></p>


### Allowed Ports
<table>
<thead>
  <tr>
    <th colspan="6">INGRESS TCP ALLOWED PORTS (FOR HOME CUSTOMERS)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>20</td>
    <td>21</td>
    <td>554</td>
    <td>843</td>
    <td>1234</td>
    <td>1433</td>
  </tr>
  <tr>
    <td>1720</td>
    <td>1723</td>
    <td>1935</td>
    <td>22</td>
    <td>3074</td>
    <td>3075</td>
  </tr>
  <tr>
    <td>3389</td>
    <td>3417</td>
    <td>3478</td>
    <td>3479</td>
    <td>3480</td>
    <td>3569</td>
  </tr>
  <tr>
    <td>4520</td>
    <td>4521</td>
    <td>4522</td>
    <td>4523</td>
    <td>4524</td>
    <td>5000</td>
  </tr>
  <tr>
    <td>7547</td>
    <td>7777</td>
    <td>8888</td>
    <td>8080</td>
    <td>9946</td>
    <td>9988</td>
  </tr>
  <tr>
    <td>15000</td>
    <td>20002</td>
    <td>30840</td>
    <td>30850</td>
    <td>30870</td>
    <td>8000-8160</td>
  </tr>
  <tr>
    <td>32400</td>
    <td>34567</td>
    <td>34599</td>
    <td>37777</td>
    <td>37778</td>
    <td>10000-10099</td>
  </tr>
  <tr>
    <td>42124</td>
    <td colspan="4"></td>
    <td>59900-59999</td>
  </tr>
</tbody>
</table>

#### Blocked Ports (All)

<table>
<thead>
  <tr>
    <th colspan="6">INGRESS BLOCKED PORTS (ALL CUSTOMERS)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td colspan="6">TCP</td>
  </tr>
  <tr>
    <td>87</td>
    <td>512</td>
    <td>513</td>
    <td>514</td>
    <td>515</td>
    <td>543</td>
  </tr>
  <tr>
    <td>5</td>
    <td>44</td>
    <td>7547</td>
    <td colspan="3"></td>
  </tr>
  <tr>
    <td colspan="6">UDP</td>
  </tr>
  <tr>
    <td>80</td>
    <td>87</td>
    <td>161</td>
    <td>162</td>
    <td>1900</td>
    <td></td>
  </tr>
</tbody>
</table>

#### Blocked Ports (Home)

<table>
<thead>
  <tr>
    <th colspan="6">INGRESS BLOCKED PORTS (HOME CUSTOMERS)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td colspan="6">UDP</td>
  </tr>
  <tr>
    <td>53</td>
    <td>80</td>
    <td>161</td>
    <td>162</td>
    <td>4520</td>
    <td>4521</td>
  </tr>
  <tr>
    <td>4</td>
    <td>522</td>
    <td>4523</td>
    <td>4524</td>
    <td colspan="2"></td>
  </tr>
</tbody>
</table>

#### Blocked Ports (All)

<table>
<thead>
  <tr>
    <th>TCP</th>
    <th>UDP</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>25</td>
    <td>1900</td>
  </tr>
</tbody>
</table>

#### Blocked Ports (Safeweb)

**TCP/UDP** 53
