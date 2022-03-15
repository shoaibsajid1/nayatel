# L2 VPN

## Basic Troubleshooting

- Status Active ?
- Power in range ?
- Eth ports UP ?
- Eth Sync Rate ?
- MACs swapped ?
- Link Choking ?

---

- Check if both sides are with Nayatel, 2 ONTs will be displayed in the ONT information on CRM with different PONs.

- Check status of both ONTs, they should be Active.

- Check powers for both ONTs, they should be in range.

- Check the Ethernet port status of both ONTs on which the L2 VPN VLAN is configured, both sides ports should be UP and MAC should be receiving on them, ask the customer to verify device MAC Addresses.

- Verify MAC swapping on OLT with the help of **Access TAC**, if both MACs are not being received there is probably a physical level issue, visit should be arranged for this.

- Check NMS graph for link choking. If link is choking, tell the customer to either:
    -  increase the bandwidth of the link 
    - check device usage.
 

Only physical parameters can be verified in case of L2 VPNs, you cannot verify packet drops only customer can. Handle the customer as per above points.

---

<h1 align="center"> Prepared by NOC </h1>

## L2 VPN Down

### 1. Point A and B?

> Verify whether both points are at NTL end or single point. This can be checked via:

#### I.	From CRM – installation addresses 
 
As per screenshot provided above, only one point is at Nayatel end whereas second point is at interconnect end.

#### II. From ONT AIDs (2 AIDs for 2 points)
 
One ONT AID as shown above, confirms that only one point is at Nayatel end.
    
#### III. From Installation Admin updates
 

### 2. ONT Status

> Check ONT status: whether Active or Inactive


#### I.ONT Inactive

#### II.ONT Active

## L3 VPN Down

### ONT Inactive

### ONT Active

## L3 VPN Degraded

## L3 VPN Degraded

*coming soon*...