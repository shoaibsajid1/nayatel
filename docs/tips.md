# Tips



### CRM tabs

CRM would not allow to open more than five (05) tabs (excluding CTI) in the browser.

---

### POTS outage

POTS service outage is being observed in following areas. Teams are working for resolution. No ETTR. Resolution could take days/months.

Gujranwala
Taxilla
Wah
B-17

---

### Emulator for Routers

https://www.tp-link.com/us/support/emulator/

Very useful site to know the options of TP Link routers GUI in case you are confused while guiding the customers about which options to select or see. Archer C7 is also there to help you.

---

### Whatsapp Tip

if a customer calls on WhatsApp, open their chat and tell them to send their query in written instead of just leaving the chat altogether. this is very wrong practice

---

### Support PC Mails

Trailing signatures have been added in both L1 Outlook PCs. Use these drafts to address customer concerns. Intimation emails will be sent to NTL customers by today.

1.	Signature Name: SMTP ToS 1

Dear Customer,
Nayatel has blocked SMTP port 25 to prevent our IP addresses and AS number from being blacklisted globally. You are requested to use secure ports 587 or 465 for SMTP connectivity.
You can refer to the following URL for guidance on how to change ports on different platforms: https://bit.ly/3KVmvSu 

We would highly appreciate your understanding and cooperation in this regard.

2.	Signature Name: SMTP ToS 2

Dear Customer,
Port 25 has been allowed for the mentioned mailing server for two weeks. In the meanwhile, please have secure ports configured in your workstation(s) and, if required, persuade your email hosting provider to shift to secure SMTP ports for seamless delivery of your emails. Till then, in case, any spam is generated from your IP address, all of the SMTP ports i.e., 25, 587 and 465 will be blocked against your connection. Furthermore, if your IP address is listed in any RBL then you will have to proceed for IP address de-listing at your end and also share precautionary measures taken to prevent spam generation. Once the precautionary measures are reviewed at our end (and are acceptable), only then the secured SMTP ports will be allowed again.
Thank you for your understanding and cooperation.

- 1st signature is to be used while replying the customer 1st time. We'll have to ask him to use 587 and 465 instead of port 25.
- If customer replies to our 1st signature and wants us to, due to some valid reason, allow port 25 for a particular destination; forward TT to CORE for allowance of port 25 for the mentioned mailing server or destination IP address.

- Note: for this customer must mention his mailing server or ip address for which port 25 is to be allowed on egress.
- 2nd signature is to be used once TT is reverted by CORE and port 25 is allowed for the mentioned destination.

---

### Breaks

Breaks in last 3 slots are reserved for Cover, Even+ and Even++,
Update your breaks accordingly. No one is allowed to break in last hour of duty.

---

### Complaint

Never ever ever mention to customer that your complaint is Pending due to work load.

---

### CTI Fix

Update Chrome to the latest version:
chrome://settings/help

Enable pop-ups:
chrome://settings/content/siteDetails?site=https%3A%2F%2Fcrm.nayatel.com

Disable flags:
chrome://flags/#enable-webrtc-hide-local-ips-with-mdns
chrome://flags/#temporary-unexpire-flags-m96
chrome://flags/#temporary-unexpire-flags-m97

Perform these steps. Also, as per few of you, CTI popups are observed to be missed if previous CTI is open. Verify this and if this is true and no CTI popup is missed if previous CTI entry is done, do let me know.

---

### Mobile App

Mobile Offers WORKS on PhoneApp number as well. Please treat PhoneApp as POTS number but only on mobile phones not landline.

---

### Trouble Tickets

Please ensure following points while coordinating trouble tickets:

1.	In case the issue is resolved (or auto resolved) and the ticket is kept on observation, the customer should be clearly communicated to contact us in case any issue is observed, otherwise the ticket will be closed after 2 days (number of days could change according to the situation).
2.	No coordination should be done with the customers when the tickets are on observation as the customer has to provide the updates.
3.	Ticket-observation option available on the tickets could be used for this purpose, as it will auto close the tickets after mentioned number of days.

---

### DNS

Always make sure to renew ip configurations in end devices after changing dns in ONT. End devices won't automatically acquire new IP configurations.

Best way is to:
ipconfig/release
ipconfig/renew

Or switching wifi off/on for mobile devices (resolution not confirmed)
Or resetting network config in mobile devices

As per systems, old backend DNS are not to be used. We used to manually update DNS in ONTs way back. Old DNS won't resolve all the destinations now. We need to use nee Anycast DNS.

Infact, its better to remove DNS, for good, in the ONT config, so that updated DNS is fetched by ONT directly from BRAS. Updating Anycast DNS in ONT would cause same issue in future when anycast DNS would probably change at network end.

It is never a good practice to add any DNS in ONT statically. ONT should be allowed to fetch DNS from BRAS.
