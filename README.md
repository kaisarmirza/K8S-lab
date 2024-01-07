Templates for K8S routers which require editing to meet your needs.

Calico configuration - Explanation of optional parameters:

*nodeSelector: Filters nodes for peering based on a label selector.
*password: Specifies a BGP password for authentication.
*keepaliveTime: Sets the interval for BGP keepalive messages.
*holdTime: Sets the duration a BGP peer should wait for a keepalive message before declaring a neighbor down.
*sourceAddress: Defines the source IP address used for BGP peering.
*enableAddressFamilies: Enables specific address families (e.g., ipv4, ipv6).
*prefixAdvertisementMode: Determines how Calico advertises prefixes (e.g., Always, CrossSubnet, or Never).
*peerSelector: Filters peers based on node labels.
*gatewayAddress: Specifies the gateway IP address for the peer.

Customize these parameters based on your specific networking requirements and infrastructure setup. Replace placeholders like VYOS_ROUTER_IP, VYOS_AS_NUMBER, NODE_IP_ADDRESS, and others with your actual configuration details.

Apply this configuration using kubectl apply -f your-config-file.yaml






To apply the configuration after copying it to the working directory and making the ncessary changes to the template. 

**kubectl apply -f your-config-file.yaml**
