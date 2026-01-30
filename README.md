# Weekly-Lab-2-Redundant-Enterprise-Edge-Secure-Access-Architecture
This lab simulates a high-availability enterprise environment featuring a redundant distribution layer and a secured access layer. The design focuses on redundancy (HSRP, OSPF), security (DHCP Snooping, DAI, SSH), and network services (NAT, DHCP, NTP in WAT timezone)

## Replicating This Lab
1. Import the `topology.gns3` or `eve-ng.unl` file.
2. Ensure your IOSv-L2 and IOSv images match the versions in the configs.
3. Apply configurations in this order:
   - NAT/Services first.
   - Core/Distribution routing.
   - Access Layer Security last (to avoid being locked out).

## Overview
This repository contains the configuration files and architecture details for a multi-vlan enterprise network lab. 

## Tech Stack
- **Routing:** OSPF, HSRP, Static NAT
- **Switching:** VTP (Off), 802.1Q Trunking, Spanning-Tree (PVST+)
- **Security:** DHCP Snooping, Dynamic ARP Inspection (DAI), SSHv2
- **Services:** Cisco IOS DHCP Server, NTP (WAT Timezone)

## Topology
The design utilizes a two-tier collapsed core/distribution model with redundant uplinks to an Edge Router providing Internet Access.

## Key Configurations
- `configs/DIST-R1.txt`: HSRP Primary, OSPF area 0.
- `configs/SW1.txt`: Access Layer Security and VLAN definitions.
- `configs/NAT-SERVER.txt`: PAT and NTP Master.

## How to Verify
1. `show standby brief` to verify HSRP states.
2. `show ip dhcp snooping binding` to verify secure client entries.
3. `show ntp status` to ensure WAT time sync.
