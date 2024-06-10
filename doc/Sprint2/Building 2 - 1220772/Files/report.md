# Building 2

## Specifications

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

- IPv4 networks:
  - Wi-Fi network: 220 nodes
  - End user outlets on floor one: 120 nodes
  - VoIP (IP-phones): 110 nodes
  - End user outlets on the ground floor: 90 nodes
  - DMZ (Servers, administration workstations, and network infrastructure devices): 50 nodes

## VLAN Database and IPv4 Network

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![IPv4_Building2.png](../Images/IPv4_Building2.png)

|       VLAN_name       | Total_Nodes | Space_Size | Prefix | Number_Of_Hosts |    Network_IP    | First_Valid_IP | Last_Valid_IP |   Broadcast   |   Subnet Mask   |
|:---------------------:|:-----------:|:----------:|:------:|:---------------:|:----------------:|:--------------:|:-------------:|:-------------:|:---------------:|
|    **VLAN-Wifi2**     |     220     |    256     |   24   |       254       |  172.22.96.0/24  |  172.22.96.1   | 172.22.96.254 | 172.22.96.255 |  255.255.255.0  |
|  **VLAN-FloorOne2**   |     120     |    128     |   25   |       126       |  172.22.97.0/25  |  172.22.97.1   | 172.22.97.126 | 172.22.97.127 | 255.255.255.128 |
|    **VLAN-VoIP2**     |     110     |    128     |   25   |       126       | 172.22.97.128/25 | 172.22.97.129  | 172.22.97.254 | 172.22.97.255 | 255.255.255.128 |
| **VLAN-GroundFloor2** |     90      |    128     |   25   |       126       |  172.22.98.0/25  |  172.22.98.1   | 172.22.98.126 | 172.22.98.127 | 255.255.255.128 |
|     **VLAN-Dmz2**     |     50      |     64     |   26   |       62        | 172.22.98.128/26 | 172.22.98.129  | 172.22.98.190 | 172.22.98.191 | 255.255.255.192 |
|       **Total**       |     590     |    1024    |   22   |      1022       |  172.22.96.0/22  |  172.22.96.1   | 172.22.99.254 | 172.22.99.255 |  255.255.252.0  |

### Relevant justification

- The networks were organized in descending order of nodes, thus filling as many addresses as possible without them being wasted.
- Although the distribution of IPv4 network addresses is adequate, there are still IPs that can be assigned to new nodes that may be introduced in the future.

## Packet Tracer Simulation

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![Building2_PKT.png](../Images/Building2_PKT.png)

### Relevant justification

- The approach adopted is in accordance with what was established in Sprint1.
- All switches were configured to have the number of ports necessary to establish the connections specified in the statement (FFE ports for fiber optic cables and CFE ports for copper cables).
- All connections between switches were changed to trunk mode, the VTP domain changed to the given domain (r2324ddg2) and the CD switch configured in server mode, the rest were configured in client mode, allowing all switches in all buildings to have all configured VLANs in their VLAN database.

## Network Configuration

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Specifications

- The implementation of the proposed requirements for Building 2 starts from the switch with host name B2 BD, which establishes a connection with two other switches representing floors 0 and 1 (B2 FD0 and B2 FD1, respectively).
- All ports that are not connected to end devices are configured in trunk mode, being the port type indicated for establishing connections with multiple VLANs. On the other hand, ports that connect to end devices are configured in access mode since they only connect to a single VLAN.
- In the configurations of the two Floor Distributors in the building, the following VLANs were associated with the end devices:

|  **VLAN_Name**   | **VLAN_ID** |               **Device(s)**               |
|:----------------:|:-----------:|:-----------------------------------------:|
| VLAN-GroundFloor |     368     |                  B2 PC0                   |
|  VLAN-FloorOne   |     369     |                  B2 PC1                   |
|    VLAN-Wifi     |     370     | B2 AP0.1, B2 APO.2, B2 AP1.1 and B2 AP1.2 |
|     VLAN-DMZ     |     371     |                  B2 DMZ                   |
|    VLAN-VoIP     |     372     |           B2 VoIP0 and B2 VoIP1           |

- Since the main objective of the sprint is to present a logical implementation plan for the network and for reasons of interpretation, it was decided not to present the total number of nodes indicated in the statement. Thus, each two final devices (one on each floor and one laptop per Access Point represented) presented in the simulation represents the totality of devices that would be needed:

|                       **Device(s)**                       | **Total Nodes** |
|:---------------------------------------------------------:|:---------------:|
|                          B2 PC0                           |       90        |
|                          B2 PC1                           |       120       |
| B2 Laptop0.1, B2 Laptop0.2, B2 Laptop1.1 and B2 Laptop1.2 |       220       |
|                          B2 DMZ                           |       50        |
|                   B2 VoIP0 and B2 VoIP1                   |       110       |

### Pings

- To confirm that everything works correctly, several images are displayed that show the success of ping tests between end devices in the same building and between different buildings.

#### Between B2 PC0 and the Building 2

![B2 PC0.png](../Images/PC0.png)

#### Between B2 PC1 and the Building 2

![B2 PC1.png](../Images/PC1.png)

#### Between B2 Laptop0.1 and the Building 2

![B2 Laptop0.1.png](../Images/Laptop0.1.png)

#### Between B2 Laptop0.2 and the Building 2

![B2 Laptop1.1.png](../Images/Laptop0.2.png)

#### Between B2 Laptop1.1 and the Building 2

![B2 Laptop0.1.png](../Images/Laptop1.1.png)

#### Between B2 Laptop1.2 and the Building 2

![B2 Laptop1.1.png](../Images/Laptop1.2.png)

#### Between B2 DMZ and the Building 2

![B2 DMZ.png](../Images/DMZ.png)

#### Between B2 Router and the Building 2

![B2 Router.png](../Images/Router.png)

#### Between B2 PC0 and the other routers

![B2 PC0_Routers.png](../Images/PC0 Routers.png)

#### Between B2 PC1 and the other routers

![B2 PC1_Routers.png](../Images/PC1 Routers.png)

#### Between B2 Laptop0.1 and the other routers

![B2 Laptop0.1_Routers.png](../Images/Laptop0.1 Routers.png)

#### Between B2 Laptop0.2 and the other routers

![B2 Laptop0.2_Routers.png](../Images/Laptop0.2 Routers.png)

#### Between B2 Laptop1.1 and the other routers

![B2 Laptop1.1_Routers.png](../Images/Laptop1.1 Routers.jpg)

#### Between B2 Laptop1.2 and the other routers

![B2 Laptop1.2_Routers.png](../Images/Laptop1.2 Routers.png)

#### Between B2 DMZ and the other routers

![B2 DMZ_Routers.png](../Images/DMZ Routers.png)

### Switches and Routers configuration files

- The configuration files for all switches and routers necessary for the correct functioning of the Building 2 structured cabling project can be found at this link: [ConfigFiles](../ConfigFiles)

#### Building 2 Router (172.22.110.2/24)

| **Building** |   **Network**   |   **Mask**    | **Next Hop** |
|:------------:|:---------------:|:-------------:|:------------:|
|      1       | 172.22.108.0/23 | 255.255.254.0 | 172.22.110.1 |
|      3       | 172.22.100.0/22 | 255.255.252.0 | 172.22.110.3 |
|      4       | 172.22.104.0/22 | 255.255.252.0 | 172.22.110.4 |
|   Default    |    0.0.0.0/0    |    0.0.0.0    | 172.22.110.1 |