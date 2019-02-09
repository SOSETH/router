# portal-lee
This configures routing (iptables) and HA (keepalived) on router nodes

# TODO: Fix readme

## What does it do?
One of the nodes gets IPv4 and IPv6 of portal-lee.ethz.ch via keepalived. Each node's IPTables is configured as following:
* Allow incoming ICMP
* Allow incoming connections for SSH and VPN
* Allow outgoing connections
* Allow routing from the SOS server net to the SOS IPMI network
 * Masquerade the packets so that I don't need to reconfigure the IPMIs
* Allow VPN access to the IPMI network
 * Also masquerade the packets

If you remove the last DROP rule in FORWARDING and set it's policy to accept you can quickly use this machine as a gateway to the internet (if your IPMI needs this for some update or something).
