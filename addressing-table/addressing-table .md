# Network Addressing Table

| Device | Interface | IP Address | Subnet Mask | Description |
| :--- | :--- | :--- | :--- | :--- |
| **NAT-SERVER** | Gi0/1 | 10.10.254.1 | 255.255.255.252 | Internal Link to Edge |
| **EDGE-R1** | Gi0/0 | 10.10.254.2 | 255.255.255.252 | External Link to NAT |
| **DIST-R1** | Gi0/0.10 | 172.16.10.2 | 255.255.255.0 | VLAN 10 Gateway (HSRP-P) |
| **DIST-R2** | Gi0/0.10 | 172.16.10.3 | 255.255.255.0 | VLAN 10 Gateway (HSRP-S) |
| **DHCP-SRV** | Gi0/0 | 10.10.50.2 | 255.255.255.252 | Primary DHCP/DNS |
