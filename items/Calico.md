#Network #CNI 

Calico's networking model uses BGP (Border Gateway Protocol) as its control plane to create a pure Layer 3 routing fabric, which is fundamentally different from traditional overlay networks.

## Core Architecture

**IP-in-IP Overlay Mode**

When Calico operates in overlay mode, it encapsulates pod traffic inside IP-in-IP packets. Each node acts as a BGP peer that:

- Advertises pod CIDR blocks it's responsible for
- Learns routes to other pods via BGP route exchange
- Encapsulates packets when crossing network boundaries that don't understand pod IPs

**BGP as the Control Plane**

BGP handles the route distribution. Each Calico node runs the BIRD BGP daemon (via calico-node), which:

- Forms BGP peering sessions with other nodes (full mesh by default, or route reflector topology for scale)
- Advertises locally hosted pod subnets to peers
- Installs received routes into the Linux kernel routing table
- Dynamically updates routes as pods are created/destroyed

## How Packets Flow

In overlay mode:

1. Pod sends packet to another pod
2. Source node checks routing table (populated by BGP)
3. If destination is on another node, packet gets IP-in-IP encapsulated
4. Outer IP header uses node IPs (which the underlay network understands)
5. Destination node decapsulates and delivers to target pod

In non-overlay mode (if your network supports it):

- BGP advertises pod CIDRs directly to upstream routers
- No encapsulation needed - pure routed network
- Much better performance, but requires network infrastructure cooperation

## Key Advantages for EKS

- **No dependency on cloud provider routing**: Unlike VPC CNI which relies on ENIs and AWS route tables
- **Better multi-cluster networking**: BGP can peer across VPC boundaries
- **Fine-grained network policies**: Calico's NetworkPolicy implementation is more feature-rich than standard Kubernetes
- **Flexibility**: Can switch between overlay and non-overlay based on environment