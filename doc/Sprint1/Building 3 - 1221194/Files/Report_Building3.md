
# Building 3  - Structured Cabling Deployment Pan#

#### Building measures:
* Width = 30 m
* Length = 30 m
* Total Area = 30 * 30 = 900 m2

## Floor 0 ##
#### Cabling System Design
![cabling_system_floor0.png](..%2FImages%2FFloor%200%2Fcabling_system_floor0.png)
#### Legend:
![legend_floor0.png](..%2FImages%2FFloor%200%2Flegend_floor0.png)

#### Measurements
![Measurements_floor0.png](..%2FImages%2FFloor%200%2FMeasurements_floor0.png)

### Relevant Justifications ###

#### Specifications ####

* The ground floor has an underfloor cable raceway connected to the external ditch.
* The access to the underfloor cable raceway is available at points marked over the plan.
* Cable passageways to the above floor are also available.
* The ceiling height on this floor is 4 meters.
* Common areas (e.g. entrance hall, restrooms,etc.) and storage room 3.0.14 require no network outlets.

#### Outlets ####

* The outlets distribution was made taking into account the most suitable locations so that the space room was not
  too compromised, also avoiding their placement close to doors.
* When positioning the outlets, it was also considered that the maximum distance between them should be 3 meters, facilitating the connection to user´s equipment.
* The number of outlets per room was determined based on a proportion of 2 outlets for every 10 m2 of area,
  however in rooms 3.0.1, 3.0.2 and 3.0.3 there was only required 2 outlets near each floor cable passageway,
* All outlets are placed on the walls, close to the floor.

#### Copper Cables ####

* All the copper cables are placed on the wall.

#### Access Points ####

* In this floor was installed two access point, one in room 3.0.2 and the other in 3.0.12
* Each access point is responsible for managing an area of radio coverage around
  it called a cell. Due to emission power legal restrictions, the maximum effective
  reach of the signal is roughly less than 30 meters, thus, in practice, the cell
  diameter is around 50 meters.

#### Floor Distributor (FD) ####

* The floor distributor is located in the room 3.0.14.

#### Building Distributor (BD) ####

* The Building distributor receives the optical fiber connection from the external ditch and distributes the signal for
  the Floor Distributors on this building, using a monomode optical fiber cable.
* The Building Distributor is located in the room 3.0.14.

#### Consolidation Points (CP) ####

* Due to the reduced number of outlets, there´s is no need to use consolidation points.

#### Cable types used ####

* To connect the outlets to the Floor Distributor (FD) is used copper cable CAT7.
* To connect the Floor Distributor (FD) to the Building Distributor (BD) it was used optical fiber monomode 10,
  since it allows to a more efficient and higher data transaction.

#### Quantities ####

|  Room  | A(m2)  | Width(m) | Length(m) | Number of Outlets | CAT7 Cables(m) |
|:------:|:------:|:--------:|:---------:|:-----------------:|:--------------:|
| 3.0.1  | 65.33  |   7.47   |   54.96   |         8         |   8 x 39.22    |
| 3.0.2  | 67.41  |   7.47   |   9.02    |         6         |   6 x 32.35    |
| 3.0.3  | 86.28  |   7.47   |   11.55   |        10         |   10 x 39.3    |
| 3.0.4  | 58.84  |   7.20   |   8.17    |        12         |   12 x 35.5    |
| 3.0.5  | 22.44  |   3.38   |   6.64    |         6         |   6 x 27.92    |
| 3.0.6  | 22.44  |   3.38   |   6.64    |         6         |   6 x 25.67    |
| 3.0.7  | 22.44  |   3.38   |   6.64    |         6         |   6 x 24.69    |
| 3.0.8  | 22.44  |   3.38   |   6.64    |         6         |   6 x 27.72    |
| 3.0.9  | 22.44  |   3.38   |   6.64    |         6         |   6 x 22.03    |
| 3.0.10 | 22.44  |   3.38   |   6.64    |         6         |   6 x 20.25    |
| 3.0.11 | 22.44  |   3.38   |   6.64    |         6         |   6 x 19.08    |
| 3.0.12 | 22.44  |   3.38   |   6.64    |         6         |   6 x 18.98    |
| 3.0.13 | 22.44  |   3.38   |   6.64    |         6         |   6 x 19.92    |
| 3.0.14 |  8.75  |   2.64   |   3.32    |         0         |       0        |
| 3.0.15 | 14.25  |   4.29   |   3.32    |         4         |   4 x 10.82    |

### Telecommunications enclosures ###

* Since there are 94 outlets on this floor, it's necessary to install two patch panels CAT7 with 48 ports each. This results in a size of 4U (2U for each patch panel).
* The enclosure will reach 6 times the U size of the patch panels, so that, the total size for this telecommunication enclosure will be 24U.
* Copper CAT7 patch cords required for each telecommunication enclosure equal the number of patch panel ports in each, meaning we need 96 short length patch cords.

## Total Inventory of Floor 0 ##

* In a fiber patch panel, each cable connection requires two fibers, so two connectors must be used.

|             Equipment              | Quantity |
|:----------------------------------:|:--------:|
|           Access Points            |    2     |
|       Copper Cable CAT7 (m)        | 2609.92  |
|     Copper Patch Cords (0.5 m)     |    96    |
|      Copper Patch Cords (5 m)      |    94    |
| Copper Patch Panel 2U (48 entries) |    2     |
|       Optic fiber cable (m)        |   1.01   |
|     Fiber Patch Cords (0.5 m)      |    8     |
| Fiber Patch Panel 1U (24 entries)  |    1     |
|              Outlets               |    94    |
|  Telecommunication Enclosures 24U  |    1     |

------------------------------------------------------

## Floor 1 ##

#### Cabling System Design
![cabling_system_floor1.png](..%2FImages%2FFloor%201%2Fcabling_system_floor1.png)
#### Legend:
![legend_floor1.png](..%2FImages%2FFloor%201%2Flegend_floor1.png)
#### Measurements
![Measurements_floor1.png](..%2FImages%2FFloor%201%2FMeasurements_floor1.png)

### Relevant Justifications ###

#### Specifications ####

* The ceiling height on this floor is 3 meters, but there’s a removable dropped ceiling, placed 2.5 meters from the ground, covering this entire floor.
* The space over the ceiling is perfect to install cable raceways and wireless access-points.
* This floor has no underfloor cable raceways.
* Common areas (e.g. entrance hall, restrooms, etc.) require no network outlets.

#### Outlets ####

* The outlets distribution was made taking into account the most suitable locations so that the space room was not
  too compromised, also avoiding their placement close to doors.
* When positioning the outlets, it was also considered that the maximum distance between them should be 3 meters, facilitating the connection to user´s equipment.
* The number of outlets per room was determined based on a proportion of 2 outlets for every 10 m2 of area.
* All outlets are placed on the walls, close to the floor.
*
#### Copper Cables ####

* All the copper cables are placed on the wall.

#### Access Points ####

* In this floor was installed two access points, one in room 3.1.10 and the other in 3.1.16
* Each access point is responsible for managing an area of radio coverage around
  it called a cell. Due to emission power legal restrictions, the maximum effective
  reach of the signal is roughly less than 30 meters, thus, in practice, the cell
  diameter is around 50 meters.

#### Floor Distributor (FD) ####

* The floor distributor is located in the room 3.1.8

#### Consolidation Points (CP) ####

* Due to the reduced number of outlets, there´s is no need to use consolidation points.

#### Cable types used ####

* To connect the outlets to the Floor Distributor is used copper cable CAT7.
  30.8
#### Quantities ####

|  Room  | A(m2)  | Width(m) | Length(m) | Number of Outlets | Cables (m) |
|:------:|:------:|:--------:|:---------:|:-----------------:|:----------:|
| 3.1.1  | 40.46  |   7.79   |   5.19    |        10         | 10 x 50.49 |
| 3.1.2  | 17.44  |   3.36   |   5.19    |         4         | 4 x 44.61  |
| 3.1.3  | 17.44  |   3.36   |   5.19    |         4         | 4 x 42,31  |
| 3.1.4  | 17.44  |   3.36   |   5.19    |         4         | 4 x 39.98  |
| 3.1.5  | 17.44  |   3.36   |   5.19    |         4         | 4 x 37.62  |
| 3.1.6  | 17.44  |   3.36   |   5.19    |         4         | 4 x 35.33  |
| 3.1.7  | 17.44  |   3.36   |   5.19    |         4         | 4 x 34.16  |
| 3.1.8  | 13.50  |   6.99   |   1.93    |         4         | 4 x  9.98  |
| 3.1.9  | 17.44  |   3.36   |   5.19    |         4         | 4 x 34.51  |
| 3.1.10 | 17.44  |   3.36   |   5.19    |         4         | 4 x 34.51  |
| 3.1.11 | 17.44  |   3.36   |   5.19    |         4         | 4 x 32.23  |
| 3.1.12 | 17.44  |   3.36   |   5.19    |         4         | 4 x 32.23  |
| 3.1.13 | 17.44  |   3.36   |   5.19    |         4         | 4 x 29.96  |
| 3.1.14 | 17.44  |   3.36   |   5.19    |         4         | 4 x 29.96  |
| 3.1.15 | 17.44  |   3.36   |   5.19    |         4         |  4 x 27.6  |
| 3.1.16 | 17.44  |   3.36   |   5.19    |         4         |  4 x 27.6  |
| 3.1.17 | 17.44  |   3.36   |   5.19    |         4         | 4 x 25.33  |
| 3.1.18 | 17.44  |   3.36   |   5.19    |         4         | 4 x 25.33  |
| 3.1.19 | 17.44  |   3.36   |   5.19    |         4         | 4 x  22.72 |
| 3.1.20 | 17.44  |   3.36   |   5.19    |         4         | 4 x 22.72  |


### Telecommunications enclosures ###

* Since there are 86 outlets on this floor, it's necessary to install two patch panels CAT7 with 48 ports each. This results in a size of 4U (2U for each patch panel).
* The enclosure will reach 6 times the U size of the patch panels, so that, the total size for this telecommunication enclosure will be 24U.
* Copper CAT7 patch cords required for each telecommunication enclosure equal the number of patch panel ports in each, meaning we need 96 short length patch cords.

## Total Inventory of Floor 1 ##

* In a fiber patch panel, each cable connection requires two fibers, so two connectors must be used.

|             Equipment              | Quantity |
|:----------------------------------:|:--------:|
|           Access Points            |    2     |
|       Copper Cable CAT7 (m)        | 2768.87  |
|     Copper Patch Cords (0.5 m)     |    96    |
|      Copper Patch Cords (5 m)      |    86    |
| Copper Patch Panel 2U (48 entries) |    2     |
|       Optic fiber cable (m)        |   0.53   |
|     Fiber Patch Cords (0.5 m)      |    8     |
| Fiber Patch Panel 1U (24 entries)  |    1     |
|              Outlets               |    86    |
|  Telecommunication Enclosures 24U  |    1     |

## Final Inventory ##

|             Equipment              |       Quantity        |
|:----------------------------------:|:---------------------:|
|           Access Points            | 4 (two in each floor) |
|      Optical fiber cable (m)       |         5.53          |
|         Copper cable CAT7          |        5378.79        |
|              Outlets               |          180          |
|     Copper Patch Cords (0.5 m)     |          192          |
|      Copper Patch Cords (5 m)      |          180          |
| Copper Patch Panel 2U (48 entries) |           4           |
|  Telecommunication Enclosure 24U   |           2           |
|     Fiber patch Cords (0.5 m)      |          16           |
| Fiber Patch Panel 1U (24 entries)  |           2           |






