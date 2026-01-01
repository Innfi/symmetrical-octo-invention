#Network #Container 

Comparison Summary

| Feature                | Amazon VPC CNI                                                      | Calico                                                                               | Cilium                                                                                                                              |
| ---------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| **Networking Model**   | Native VPC routing                                                  | Overlay or BGP (L3)                                                                  | eBPF (native routing or overlay)                                                                                                    |
| **Policy Enforcement** | Requires separate engine (e.g., Calico or Cilium policy controller) | Robust L3/L4 and advanced L7 (enterprise)                                            | High-performance eBPF L3/L4/L7                                                                                                      |
| **AWS Integration**    | Deepest, default for EKS                                            | Good support via [Tigera](https://www.tigera.io/project-calico/) partner integration | Good support via [Isovalent](https://isovalent.com/blog/post/eks-byocni-cilium/) partner integration, also default for EKS Anywhere |
| **IP Management**      | Uses VPC IPs (potential for exhaustion)                             | More efficient IP usage (less exhaustion)                                            | More efficient IP usage (less exhaustion)                                                                                           |
| **Performance**        | Low latency due to direct routing                                   | Fast routing (BPF data plane)                                                        | Very high performance (eBPF data plane)                                                                                             |

Amazon VPC CNI

This is the default and only supported CNI plugin for Amazon EKS clusters with Fargate nodes. 

- **Key Feature:** It provides native VPC networking by assigning each pod an IP address from the VPC's subnet. This allows pods to be treated like any other EC2 instance in the VPC, making it possible to use existing VPC tools like security groups and flow logs for pods.
- **Pros:** Seamless integration with AWS infrastructure, low latency due to direct routing, and "security groups for pods" feature.
- **Cons:** Can lead to **IP address exhaustion** in subnets more quickly than other solutions because each pod consumes a VPC IP address. It also does not natively support Kubernetes Network Policies on its own; a separate policy engine is required. 

Calico

Calico is a widely adopted solution for container networking and security, especially known for its comprehensive network policy engine. 

- **Key Feature:** It provides robust network policy enforcement, including support for standard Kubernetes Network Policies and advanced features like Global Network Policies and BGP routing in its enterprise versions. It often uses BPF for fast routing decisions.
- **Pros:** Excellent for complex, policy-intensive workloads and hybrid cloud environments where consistent network policy across different clouds/on-premise is needed.
- **Cons:** Less native integration with specific AWS features compared to the VPC CNI. 

Cilium

Cilium is a newer, high-performance CNI plugin that leverages **eBPF** (extended Berkeley Packet Filter) technology in the Linux kernel for networking, security, and observability. 

- **Key Feature:** eBPF allows Cilium to perform network and security functions in the kernel datapath with high efficiency, often resulting in faster performance than traditional `iptables` methods. It offers advanced capabilities like L7 (application-layer) filtering, transparent encryption, and deep network observability via Hubble.
- **Pros:** Superior performance and observability, advanced security features, and the ability to manage L4-L7 policies.
- **Cons:** Has a steeper learning curve due to eBPF, and some advanced features might be limited when used in CNI chaining mode with other plugins.