# router

This configures routing (iptables) and HA (keepalived) on router nodes

## What does it do?
One of the nodes gets IPv4 and IPv6 of via keepalived. Each node's IPTables is configured for simple firewalling, have a look at `defaults/main.yml` for defaults.

If you remove the last DROP rule in FORWARDING and set it's policy to accept you
can quickly use this machine as a gateway to the internet (if your IPMI needs
this for some update or something).
