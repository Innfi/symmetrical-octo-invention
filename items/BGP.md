#Network #Protocol 

>[!tip]
>Border Gateway Protocol
>L7

# Capabilities of Autonomous System
- find the best route
- discover network connection changes
- administrator network policies
- add a layer of network security
# How the protocol works
- route discovery
- route storage
- route selection
# Handling scale
- route reflector
- confederation
- route aggregation

## **Example BGP Routing Table Output**

From a Cisco router using `show ip bgp`:

```
BGP table version is 6, local router ID is 10.0.96.2
Status codes: s suppressed, d damped, h history, * valid, > best, i - internal
Origin codes: i - IGP, e - EGP, ? - incomplete

Network          Next Hop      Metric   LocPrf   Weight   Path
*> 10.0.0.0      192.168.12.2    0       100        0      2 4 i
*  10.0.0.0      192.168.13.3    0       100        0      3 4 i
```

## **What the fields mean:**

- **Network**: The destination prefix (e.g., 10.0.0.0/24)
- **Next Hop**: IP address of the next router in the path
- **Metric (MED)**: Multi-Exit Discriminator - preference value
- **LocPrf**: Local preference (higher = more preferred)
- **Weight**: Cisco-specific attribute
- **Path (AS_PATH)**: Sequence of autonomous system numbers the route traversed [NetworkLessons](https://networklessons.com/bgp/how-to-read-the-bgp-table)
- **Status codes**:
    - `*` = valid route
    - `>` = best route selected
    - `i` = internal BGP

## Reference
---
https://aws.amazon.com/what-is/border-gateway-protocol/
https://www.nobgp.com/info/understanding-bgp-backbone-of-the-internet
https://blog.naver.com/taeheon714/222384978033
https://networklessons.com/bgp/how-to-read-the-bgp-table

