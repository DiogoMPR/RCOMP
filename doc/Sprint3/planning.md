# Sprint 3 - Planning #

###  Sprint Master: 1220772 ###

## 1. Sprint backlog and task's assignment ##
| Task ID | Task                                                                                                                                                                                                                                                        | Task's assignment |
|:-------:|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------:|
|  T.3.1  | Update the building1.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building 1.                                                                                                    |      1220812      |
|  T.2.2  | Update the building2.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building 2. Final integration of each member’s Packet Tracer simulation into a single simulation (campus.pkt). |      1220772      |
|  T.2.3  | Update the building3.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building 3.                                                                                                    |      1221194      |
|  T.2.4  | Update the building4.pkt layer three Packet Tracer simulation from the previous sprint, to include the described features in this sprint for building 4.                                                                                                    |      1220917      |

## 2. Specifications ##

* The team use the Packet Tracer version 8.2.1.0118.

* The main output is the Packet Tracer simulation file for the corresponding building, it should be named BuildingN.pkt, with N being the number which identifies the building.

* The team member is charge of building 2 has the additional final subtask of integrating all members work for this sprint into a single final overall simulation (campus.pkt).

### 2.1. OSPF area ids

| **OSPF area id** |  **area**  |
|:----------------:|:----------:|
|        0         |  Backbone  |
|        1         | Building 1 |
|        2         | Building 2 |
|        3         | Building 3 |
|        4         | Building 4 |

### 2.2. VoIP prefixes

| **Building** | **Prefix** |
|:------------:|:----------:|
|  Building 1  |     1      |
|  Building 2  |     2      |
|  Building 3  |     3      |
|  Building 4  |     4      |

### 2.3. DNS names

* The highest level DNS domain will be part of Building 1, naming rcomp-23-24-dd-g2. It will be used as if it was the DNS root domain.

* The other DNS domains will be created locally in each building, naming building-X.rcomp-23-24-dd-g2. The letter X will identify the building's number.

* In each building, all DNS servers will have the unqualified DNA name as ns. While Building 1 will have ns.rcomp-23-24-dd-g2, the others will have ns.building-X.rcomp-23-24-dd-g2.

#### 2.3.1. IPv4 node address for each DNS name server

|  **Building**  |            **Name**             | **DMZ name** |  **address**   |
|:--------------:|:-------------------------------:|:------------:|:--------------:|
| **Building 1** |      ns.rcomp-23-24-dd-g2       |    B1-DMZ    |  172.22.108.0  |
| **Building 2** | ns.building-2.rcomp-23-24-dd-g2 |    B2-DMZ    | 172.22.98.128  |
| **Building 3** | ns.building-3.rcomp-23-24-dd-g2 |    B3-DMZ    | 172.22.103.128 |
| **Building 4** | ns.building-4.rcomp-23-24-dd-g2 |    B4-DMZ    | 172.22.107.128 | 