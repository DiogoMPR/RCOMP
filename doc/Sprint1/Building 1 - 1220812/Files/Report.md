
# Building 1 - Structured Cabling Deployment Plan #

Building measures:
* Width = 20 m
* Length = 20 m
* Total Area = 20 * 20 = 400 m2

## Floor 0 ##

### Measurements ###

![Measurements.png](..%2FImages%2FFloor%200%2FMeasurements.png)

### Cabling system design ###

![CablingSystemDesign.png](..%2FImages%2FFloor%200%2FCablingSystemDesign.png)

### Relevant Justifications ###

#### Specifications ####

* The ground floor has an underfloor cable raceway connected to the external ditch.
* The access to the underfloor cable raceway is available at points marked over the plan.
* Cable passageways to the above floor are also available.
* The ceiling height on this floor is 4 meters.
* Common areas (e.g. entrance hall, restrooms, etc.) require no network outlets.

#### Outlets ####

* The outlets distribution was made taking into account the most suitable locations so that the room space was not
too compromised, also avoiding their placement too close to doors.
* When positioning the outlets, it was also considered that the maximum distance between them should be 3 meters, facilitating the connection to user´s equipment.
* The number of outlets per room was determined based on a proportion of 2 outlets for every 10 m2 of area.
* All outlets are placed on the walls, close to the floor.
* For each work area outlet, longer patch cords should be provided, up to 5 meters long.

#### Copper Cables ####

* All the copper cables are placed on the wall.

#### Access Points ####

* In this floor was installed one access point.
*  Each access point is responsible for managing an area of radio coverage around
   it called a cell. Due to emission power legal restrictions, the maximum effective
   reach of the signal is, in practice, around 50 meters (diameter).

#### Floor Distributor (FD) ####

* The floor distributor is located in the room 1.0.4.

#### Consolidation Points (CP) ####

* Due to the reduced number of outlets, there´s no need for consolidation points.

#### Cable types used ####

* To connect the outlets to the Floor Distributor (FD) is used copper cable CAT7.
* To connect the Floor Distributor (FD) to the Building Distributor (floor 1) it was used optic fiber monomode 8, since it contributes to a most efficient and higher data transaction.

#### Quantities ####

| Room  | Length (m) | Width (m) | Area (m2) | Outlets number | CAT7 cable length (m)                          | 
|-------|------------|-----------|-----------|----------------|------------------------------------------------|
| 1.0.1 | 5.15       | 4.89      | 25.18     | 6              | 6 x (1.39 + 9.28 + 3.87 + 5.44 + 4.91)         |   
| 1.0.2 | 3.86       | 4.89      | 18.88     | 4              | 4 x (1.39 + 9.28 + 3.87 + 4.91)                |   
| 1.0.3 | 4.62       | 4.89      | 22.59     | 6              | 6 x (1.39 + 9.28 + 4.91)                       |  
| 1.0.4 | 4.92       | 7.10      | 34.93     | 8              | 8 x (0.69 + 4.91 + 4.92)                       | 
| 1.0.5 | 5.72       | 4.36      | 24.94     | 6              | 7 x (0.69 + 4.91 + 5.65 + 1.89)                | 
| 1.0.6 | 5.72       | 7.07      | 40.58     | 10             | 10 x (0.69 + 4.91 + 4.76 + 7.35 + 5.84 + 4.42) |  
| Total | ---------  | --------- | --------- | 40             | 776.46                                         |   

* In the room 1.0.5. we considered 7 CAT7 cables because the wireless access point for this floor is located in this room.

### Telecommunications enclosures ###

##### Room 1.0.4 ####

* Since there are 40 outlets in this floor, it's necessary to install two path panels CAT7 with 24 ports, each. Which results in a size of 2U (1U for each patch panel).
* The enclosure will reach 6 times the U size for the patch panels, so that, the total size for this telecommunication enclosure will be 12U.
* Copper CAT7 patch cords required for each telecommunication enclosure equals the number of patch panel ports in each, so that we need 48 short length patch cords.

## Total inventory for the floor 0 ##

* In a fiber patch panel, each cable connection requires two fibres, so two connectors must be used.

| Equipment                          | Quantity |
|------------------------------------|----------|
| Access Points                      | 1        |
| Copper Cable cat7 (m)              | 776.46   |
| Copper Patch Cords (0.5 m)         | 48       |
| Copper Patch Cords (5 m)           | 40       |
| Copper Patch Panel 1U (24 entries) | 2        |
| Optic fiber cable (m)              | 8.72     |
| Fiber Patch Cords (0.5 m)          | 8        |
| Fiber Patch Panel 1U (24 entries)  | 1        |
| Outlets                            | 40       |
| Telecommunication Enclosures 12U   | 1        |

## Floor 1 ##

### Measurements ###

![Measurements.png](..%2FImages%2FFloor%201%2FMeasurements.png)

### Cabling system design ###

![CablingSystemDesign.png](..%2FImages%2FFloor%201%2FCablingSystemDesign.png)

### Relevant Justifications ###

#### Specifications ####

* The ceiling height on this floor is 3 meters, however there´s a removable dropped ceiling, placed 2.5 meters from the ground, covering the entire floor.
* The space over the ceiling is perfect to install cable raceways and wireless access-points.
* This floor has no underfloor cable raceways.
* Common areas (e.g. entrance hall, restrooms, etc.) require no network outlets.

#### Outlets ####

* The outlets distribution was made taking into account the most suitable locations so that the space room was not
  too compromised, also avoiding their placement close to doors.
* When positioning the outlets, it was also considered that the maximum distance between them should be 3 meters, facilitating the connection to user´s equipment.
* The number of outlets per room was determined based on a proportion of 2 outlets for every 10 m2 of area.
* All outlets are placed on the walls, close to the floor.
* This building has the datacenter (room 1.1.4), that also contains the Campus Distributor (CD) to the cable system.

#### Copper Cables ####

* All the copper cables are placed on the ceiling and on the walls.

#### Access Points ####

* In this floor was installed one access point.
* Each access point is responsible for managing an area of radio coverage around
  it called a cell. Due to emission power legal restrictions, the maximum effective
  reach of the signal is, in practice, around 50 meters (diameter).

#### Campus Distributor (CD) ####

* The CD receives the optic fiber connection from the exterior and distributes the signal for the 4 Building Distributors, 
one en each building, using a monomode optic fiber cable.
* The Campus Distributor is located in the room 1.1.4.

#### Building Distributor (BD) ####

* The Building distributor receives the optic fiber connection from the Campus Distributor and distributes the signal
for the Floor Distributors on this building, using a monomode optic fiber cable.
* The Building Distributor is located in the room 1.1.4.

#### Floor Distributor (FD) ####

* The floor distributor is located in the room 1.1.4.

#### Consolidation Points (CP) ####

* Due to the reduced number of outlets, there´s no need for consolidation points.

#### Cable types used ####

* To connect the outlets to the Floor Distributor is used copper cable CAT7.
* To connect the FD to the Building Distributor (floor 1) it was used optic fiber monomode 10, since it allows to a most efficient and higher data transaction.

#### Quantities ####

| Room    | Length (m) | Width (m) | Area (m2) | Outlets number | CAT7 cable length (m)                                                           |
|---------|------------|-----------|-----------|----------------|---------------------------------------------------------------------------------|
| 1.0.1   | 7.06       | 3.52      | 24.85     | 6              | 6 x (2.5 + 4.09 + 8.80 + 3.65 + 3.65 + 4.46 + 2.5)                              |                                 
| 1.0.2   | 7.06       | 3.52      | 24.85     | 6              | 6 x (2.5 + 4.09 + 8.80 + 3.65 + 4.46 + 2.5)                                     |                                 
| 1.0.3   | 7.06       | 3.52      | 24.85     | 6              | 6 x (2.5 + 4.09 + 8.80 + 4.46 + 2.5)                                            |                                 
| 1.0.4   | 7.06       | 7.63      | 53.87     | 12             | 12 x (2.5 + 4.90 + 7.06 + 2.5)                                                  |                                 
| 1.0.5   | 4.34       | 5.43      | 23.57     | 6              | 6 x (2.5 + 4.09 + 2.53 + 2.83 + 4.52 + 3.94 + 2.5)                              |                                 
| 1.0.6   | 7.06       | 5.73      | 40.45     | 10             | 10 x (2.5 + 4.09 + 2.53 + 2.83 + 4.52 + 7.47 + 5.62 + 5.50 + 2.5)               |                                
| 1.0.7   | 4.63       | 6.04      | 27.97     | 6              | 6 x (2.5 + 4.09 + 2.53 + 2.83 + 4.52 + 13.31 + 2.63 + 5.78 + 4.44 + 5.74 + 2.5) |
| * extra | ---------- | --------- | --------- | -------------- | 2.5 + 4.09 + 2.53 + 2.83 + 4.52 + 3.94 + 3.57 + 2.5                             |
| Total   | ---------- | --------- | --------- | 52             | 1516.28                                                                         |                               

* extra - The measurements on this line corresponds to the length of the copper cable CAT7 required to
connect the wireless access point located in the middle of this floor.

### Telecommunications enclosures ###

#### Room 1.1.4 ####

* Since there are 52 outlets in this floor, it's necessary to install two path panels CAT7 with 48 ports, each. Which results in a size of 4U (2U for each patch panel).
* The enclosure will reach 6 times the U size for the patch panels, so that, the total size for this telecommunication enclosure will be 24U. 
* Copper CAT7 patch cords are required for each telecommunication enclosure equals the number of patch panel ports in each, so that we need 96 short length patch cords.

## Total inventory for the floor 1 ##

* In a fiber patch panel, each cable connection requires two fibres, so two connectors must be used.

| Equipment                          | Quantity |
|------------------------------------|----------|
| Access Points                      | 1        |
| Copper Cable CAT7 (m)              | 1516.28  |
| Copper Patch Cords (0.5 m)         | 96       |
| Copper Patch Cords (5 m)           | 52       |
| Copper Patch Panel 2U (48 entries) | 2        |
| Optic fiber cable (m)              | 3.45     |
| Fiber Patch Cords (0.5 m)          | 64       |
| Fiber Patch Panel 3U (72 entries)  | 1        |
| Outlets                            | 52       |
| Telecommunication Enclosures 24U   | 1        |


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Final Inventory ##

| Equipment                          | Quantity              |
|------------------------------------|-----------------------|
| Access Points                      | 2 (one in each floor) |
| Optic fiber cable                  | 12.17 m               |
| Copper cable CAT7                  | 2292.74 m             |
| Outlets                            | 92                    |
| Telecommunication Enclosure 12U    | 1                     |
| Telecommunication Enclosure 24U    | 1                     |
| Copper Patch Cords (0.5 m)         | 144                   |
| Copper Patch Cords (5 m)           | 92                    |
| Copper Patch Panel 2U (48 entries) | 2                     |
| Copper Patch Panel 1U (24 entries) | 2                     |
| Fiber patch Cords (0.5 m)          | 72                    |
| Fiber Patch Panel 3U (72 entries)  | 1                     |
| Fiber Patch Panel 1U (24 entries)  | 1                     |