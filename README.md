# Templates for K8S BGP peer networking

## Calico configuration - Explanation of optional parameters: 

- nodeSelector: Filters nodes for peering based on a label selector.
- password: Specifies a BGP password for authentication.
- keepaliveTime: Sets the interval for BGP keepalive messages.
- holdTime: Sets the duration a BGP peer should wait for a keepalive message before declaring a neighbor down.
- sourceAddress: Defines the source IP address used for BGP peering.
- enableAddressFamilies: Enables specific address families (e.g., ipv4, ipv6).
- prefixAdvertisementMode: Determines how Calico advertises prefixes (e.g., Always, CrossSubnet, or Never).
- peerSelector: Filters peers based on node labels.
- gatewayAddress: Specifies the gateway IP address for the peer.

Customize these parameters based on your specific networking requirements and infrastructure setup. Replace placeholders like VYOS_ROUTER_IP, VYOS_AS_NUMBER, NODE_IP_ADDRESS, and others with your actual configuration details.

Apply this configuration using ***kubectl apply -f your-config-file.yaml***


## Kube-router configuration - Explanation of some optional parameters:

- --run-firewall: Disables the internal firewall managed by kube-router.
- --enable-ipv4 and --enable-ipv6: Enable or disable support for IPv4 and IPv6 respectively.
- --ip-masq: Enable or disable IP masquerade.
- --bgp-address-families: Specifies BGP address families to use (e.g., ipv4-ucast, ipv6-ucast).
- --cluster-as: Set the BGP AS number for the Kubernetes cluster.
- --node-as: Set the BGP AS number for the node.
- --peer-router-ips: Specifies the IP addresses of BGP peers (replace with your peers' IPs).
- --bgp-tolerance-timeout, --bgp-hold-time, --bgp-keepalive-time: Adjust BGP timers as needed.
- --enable-external-ips: Enables support for external IPs.

Customize these parameters based on your network topology, AS numbers, IP addresses, and other specific configurations. Replace placeholders like VYOS_ROUTER_IP, KUBE_API_SERVER_URL, and others with your actual details.

Apply this configuration as a DaemonSet in the kube-system namespace using kubectl apply -f your-config-file.yaml. Adapt the settings to your infrastructure to ensure proper BGP peering between Kube-router and your routers.
