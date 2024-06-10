# Building 4

## Specifications

- IPv4 networks:

  - End user outlets on the ground floor: 120 nodes
  - End user outlets on floor one: 150 nodes
  - Wi-Fi network: 190 nodes
  - DMZ (Servers, administration workstations, and network infrastructure devices): 40 nodes
  - VoIP (IP-phones): 170 nodes

## VLAN database and IPv4 network

![IPv4_Building4.png](..%2FImages%2FIPv4_Building4.png)


|       VLAN_name       | VLAN_ID | Total_Nodes | Space_size | Prefix | Number_Of_Valid_Networks |    Network_IP     | First_Valid_IP |  Last_Valid_IP  |   Broadcast    | Subnet mask     |
|:---------------------:|:-------:|:-----------:|:----------:|:------:|:------------------------:|:-----------------:|:--------------:|:---------------:|:--------------:|-----------------|
|    **VLAN-Wi-Fi4**    |   380   |     190     |    256     |   24   |           254            |  172.22.104.0/24  |  172.22.104.1  | 172.22.104.254  | 172.22.104.255 | 255.255.255.0   |
|    **VLAN-VoIP4**     |   382   |     170     |    256     |   24   |           254            |  172.22.105.0/24  |  172.22.105.1  | 172.22.105.254  | 172.22.105.255 | 255.255.255.0   |
|  **VLAN-FloorOne4**   |   379   |     150     |    256     |   24   |           254            |  172.22.106.0/24  |  172.22.106.1  | 172.22.106.254	 | 172.22.106.255 | 255.255.255.0   |
| **VLAN-GroundFloor4** |   378   |     120     |    128     |   25   |           126            |  172.22.107.0/25  |  172.22.107.1  | 172.22.107.126  | 172.22.107.127 | 255.255.255.128 |
|     **VLAN-DMZ4**     |   381   |     40      |     64     |   26   |            62            | 172.22.107.128/26 | 172.22.107.129 | 172.22.107.190  | 172.22.107.191 | 255.255.255.192 |

### Relevant justification

- The networks were organized in descending order of nodes, thus filling as many addresses as possible without them being wasted.
- Although the distribution of IPv4 network addresses is adequate, there are still IPs that can be assigned to new nodes that may be introduced in the future.


## Packet Tracer Simulation

### Building 4

![Building4_Installation.png](..%2FImages%2FBuilding4_Installation.png)

### Relevant justification

- The approach adopted is in accordance with what was established in Sprint1.
- All switches were configured to have the number of ports necessary to establish the connections specified in the statement (FFE ports for fiber optic cables and CFE ports for copper cables).
- All connections between switches were changed to trunk mode, the VTP domain changed to the given domain (r2324ddg2) and the CD switch configured in server mode, the rest were configured in client mode, allowing all switches in all buildings to have all configured VLANs in their VLAN database.

###


## Network Configuration

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


### Specifications

- The implementation of the proposed requirements for Building 4 starts from the switch with host name B4 BD, which establishes a connection with two other switches representing floors 0 and 1 (B4 FD0 and B4 FD1, respectively).
- All ports that are not connected to end devices are configured in trunk mode, being the port type indicated for establishing connections with multiple VLANs. On the other hand, ports that connect to end devices are configured in access mode since they only connect to a single VLAN.
- In the configurations of the two Floor Distributors in the building, the following VLANs were associated with the end devices:

|  **VLAN_Name**   | **VLAN_ID** |                      **Device(s)**                       |
|:----------------:|:-----------:|:--------------------------------------------------------:|
| VLAN-GroundFloor |     378     |                          B4 PC0                          |
|  VLAN-FloorOne   |     379     |                          B4 PC1                          |
|    VLAN-Wifi     |     380     | B4 Laptop0.1 , B4 Laptop0.2, B4 Laptop1.1 , B4 Laptop1.2 |
|     VLAN-Dmz     |     381     |                          B4 DMZ                          |
|    VLAN-VoIP     |     382     |                  B4 VoIP0 and B4 VoIP1                   |

- Since the main objective of the sprint is to present a logical implementation plan for the network and for reasons of interpretation, it was decided not to present the total number of nodes indicated in the statement. Thus, each two final devices (one on each floor and one laptop per Access Point represented) presented in the simulation represents the totality of devices that would be needed:

|                      **Device(s)**                       | **Total nodes** |
|:--------------------------------------------------------:|:---------------:|
|                          B4 PC0                          |       120       |
|                          B4 PC1                          |       150       |
| B4 Laptop0.1 , B4 Laptop0.2, B4 Laptop1.1 , B4 Laptop1.2 |       190       |
|                          B4 DMZ                          |       40        |
|                  B4 VoIP0 and B1 VoIP1                   |       170       |

### Pings

- To confirm that everything works correctly, several images are displayed that show the success of ping tests between end devices in the same building and between different buildings, including the ISP.

#### Between B4 PC0 and the Building 4

![B4 PC0.png](..%2FImages%2FB4%20PC0.png)

#### Between B4 PC1 and the Building 4

![B4 PC1.png](..%2FImages%2FB4%20PC1.png)

#### Between B4 Laptop0.1 and the Building 4

![B4 Laptop0.1.png](..%2FImages%2FB4%20Laptop0.1.png)

#### Between B4 Laptop0.2 and the Building 4

![B4 Laptop0.2.png](..%2FImages%2FB4%20Laptop0.2.png)

#### Between B4 Laptop1.1 and the Building 4

![B4 Laptop1.1.png](..%2FImages%2FB4%20Laptop1.1.png)

#### Between B4 Laptop1.2 and the Building 4

![B4 Laptop1.2.png](..%2FImages%2FB4%20Laptop1.2.png)

#### Between B4 DMZ and the Building 4

![B4 DMZ.png](..%2FImages%2FB4%20DMZ.png)

#### Between B4 Router and the Building 4

![B4 Router.png](..%2FImages%2FB4%20Router.png)

#### Between B4 PC0 and the other buildings, including the ISP

![B4 PC0 OtherBuildings.png](..%2FImages%2FB4%20PC0%20OtherBuildings.png)

#### Between B4 PC1 and the other buildings, including the ISP

![B4 PC1 OtherBuildings.png](..%2FImages%2FB4%20PC1%20OtherBuildings.png)

#### Between B4 Laptop0.1 and the other buildings, including the ISP

![B4 Laptop0.1 OtherBuildings.png](..%2FImages%2FB4%20Laptop0.1%20OtherBuildings.png)

#### Between B4 Laptop0.2 and the other buildings, including the ISP

![B4 Laptop0.2 OtherBuildings.png](..%2FImages%2FB4%20Laptop0.2%20OtherBuildings.png)

#### Between B4 Laptop1.1 and the other buildings, including the ISP

![B4 Laptop1.1 OtherBuildings.png](..%2FImages%2FB4%20Laptop1.1%20OtherBuildings.png)

#### Between B4 Laptop1.2 and the other buildings, including the ISP

![B4 Laptop1.2 OtherBuildings.png](..%2FImages%2FB4%20Laptop1.2%20OtherBuildings.png)

#### Between B4 DMZ and the other buildings, including the ISP

![B4 Laptop0.1 OtherBuildings.png](..%2FImages%2FB4%20Laptop0.1%20OtherBuildings.png)

#### Between B4 Router and the other buildings, including the ISP

![B4 Router OtherBuildings.png](..%2FImages%2FB4%20Router%20OtherBuildings.png)


### Switches and Routers configuration files

- The configuration files for all switches and routers necessary for the correct functioning of the Building 4 structured cabling project can be found at this link: [Config_Files](..%2FConfig_Files)

### Routing Tables

#### Building 4  - B4 Router (172.22.110.4/24)

| **Building** |   **Network**   |   **Mask**    | **Next Hop** |
|:------------:|:---------------:|:-------------:|:------------:|
|      1       | 172.22.108.0/23 | 255.255.254.0 | 172.22.110.1 |
|      2       | 172.22.96.0/22  | 255.255.252.0 | 172.22.110.2 |
|      3       | 172.22.100.0/22 | 255.255.252.0 | 172.22.110.3 |
|   Default    |    0.0.0.0/0    |    0.0.0.0    | 172.22.110.1 |