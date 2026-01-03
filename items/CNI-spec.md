#CNI #Network #Container 

## Core Concept

CNI defines a standard interface between container runtimes (like containerd, CRI-O) and network plugins. When a container is created or destroyed, the runtime calls the CNI plugin to set up or tear down networking.

## Basic Operation

The runtime executes the CNI plugin as a standalone binary, passing configuration via stdin and environment variables. The plugin performs network setup (creating veth pairs, assigning IPs, configuring routes) and returns results in JSON format.

**Key environment variables:**

- `CNI_COMMAND` - ADD, DEL, CHECK, or VERSION
- `CNI_CONTAINERID` - unique container identifier
- `CNI_NETNS` - path to network namespace
- `CNI_IFNAME` - interface name to create inside container
## Configuration Structure


```json
{
  "cniVersion": "0.4.0",
  "name": "mynet",
  "type": "bridge",
  "bridge": "cni0",
  "ipam": {
    "type": "host-local",
    "subnet": "10.244.0.0/16"
  }
}
```

## Plugin Types

- **Main plugins** - create network interfaces (bridge, macvlan, ipvlan, ptp) 
- **IPAM plugins** - handle IP address allocation (host-local, dhcp, static) 
- **Meta plugins** - modify behavior of other plugins (bandwidth, portmap, tuning)




## Reference
https://github.com/containernetworking/cni