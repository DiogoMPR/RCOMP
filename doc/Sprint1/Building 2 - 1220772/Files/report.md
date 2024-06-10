# Building 2 - Structured Cabling Deployment Plan #

Building measures:
* Width = 40 m
* Length = 20 m
* Total Area = 40 * 20 = 800 m2

## Floor 0 ##

### Measurements ###

![measuresF0.png](../Images/Floor%200/measuresF0.png)

### Cabling system design ###

![cableSystemDesignF0.png](../Images/Floor%200/cableSystemDesignF0.png)

#### Specifications ####

* The ground floor has an underfloor cable raceway connected to the external ditch.
* The access to the underfloor cable raceway is available at points marked over the plan.
* The ceiling height on this floor is 4 meters.
* Common areas (e.g. entrance hall, restrooms, etc.) require no network outlets.
* Rooms 2.0.6 and 2.0.7 have a special use and only 5 outlets are required along the underfloor cable raceway.

#### Outlets ####

* The outlets distribution was made taking into account the most suitable locations so that the room space was not
  too compromised while also avoiding their placement too close to doors.
* When positioning the outlets, it was also considered that the maximum distance between the outlet and the user should be 3 meters, facilitating the connection to user´s equipment.
* The number of outlets per room was determined based on a proportion of 2 outlets for every 10 m2 of area.
* All outlets are placed on the walls, close to the floor.

#### Copper Cables ####

* All the copper cables are placed on the wall.

#### Access Points ####

* In this floor, two access points were installed. They are in the rooms 2.0.6 and 2.0.7.
* Each access point is responsible for managing an area of radio coverage around
  it called a cell. If we consider the diameter of the cell to be 50 meters only one access point 
  would be needed, but in this case we are considering the possibility of interference because of the multiple
  walls of the building which led to the installation of two access points.

#### Building Distributor (BD) ####

* The Building distributor receives the optic fiber connection from the Campus Distributor and distributes the signal to the Floor Distributors on this building, using a monomode optic fiber cable.
* The Building Distributor is located in the room 2.0.11.

#### Floor Distributor (FD) ####

* The floor distributor is located in the room 2.0.11.

#### Consolidation Points (CP) ####

* Due to the reduced number of outlets, there's no need for consolidation points.

#### Cable types used ####

* To connect the outlets to the Floor Distributor (FD) the used one is copper cable CAT7.
* To connect the Floor Distributor (FD) to the Building Distributor (Floor 0) it was used optic fiber monomode 8, since it allows to a most efficient and higher data transaction.

#### Quantities ####

|  Room  | Area(m2) | Width(m) | Length(m) | Number of Outlets | CAT7 Cables(m) |
|:------:|:--------:|:--------:|:---------:|:-----------------:|:--------------:|
| 2.0.1  |  19.48   |   5.87   |   3.32    |         4         |   4 x 63.21    |
| 2.0.2  |  19.48   |   5.87   |   3.32    |         4         |   4 x 59.55    |
| 2.0.3  |  19.48   |   5.87   |   3.32    |         4         |   4 x 55.91    |
| 2.0.4  |  19.48   |   5.87   |   3.32    |         4         |   4 x 52.39    |
| 2.0.5  |  43.35   |   8.67   |   5.00    |        12         |   12 x 49.91   |
| 2.0.6  |  108.96  |   9.79   |   11.13   |         5         |   5 x 40.44    |
| 2.0.7  |  108.96  |   9.79   |   11.13   |         5         |   5 x 20.41    |
| 2.0.8  |  28.91   |   3.35   |   8.63    |         6         |   6 x 18.22    |
| 2.0.9  |  28.91   |   3.35   |   8.63    |         6         |   6 x 14.46    |
| 2.0.10 |  15.84   |   3.35   |   4.73    |         4         |    4 x 8.10    |
| 2.0.11 |  12.12   |   3.35   |   3.62    |         0         |       0        |
| Total  | -------- | -------- | --------- |        54         |    2055.89     |

### Telecommunications enclosures ###

* Since there are 54 outlets in this floor, it's necessary to install two patch panels CAT7 with 48 ports each. This results in a size of 4U (2U for each patch panel).
* The enclosure will reach 6 times the U size for the patch panels, so that, the total size for this telecommunication enclosure will be 24U.
* Copper CAT7 patch cords required for each telecommunication enclosure equals the number of patch panel ports in each, meaning we need 96 short length patch cords.

## Total Inventory of Floor 0 ##

* In a fiber patch panel, each cable connection requires two fibres, so two connectors must be used.

|             Equipment              | Quantity |
|:----------------------------------:|:--------:|
|           Access Points            |    2     |
|       Copper Cable CAT7 (m)        | 2055.89  |
|     Copper Patch Cords (0.5 m)     |    96    |
|      Copper Patch Cords (5 m)      |    54    |
| Copper Patch Panel 2U (48 entries) |    2     |
|       Optic fiber cable (m)        |   2.18   |
|     Fiber Patch Cords (0.5 m)      |    8     |
| Fiber Patch Panel 1U (24 entries)  |    1     |
|              Outlets               |    54    |
|  Telecommunication Enclosures 24U  |    1     |

## Floor 1 ##

### Measurements ###

![measuresF1.png](../Images/Floor%201/measuresF1.png)

### Cabling system design ###

![cableSystemDesignF1.png](../Images/Floor%201/cableSystemDesignF1.png)

#### Specifications ####

* The ceiling height on this floor is 3 meters, however there´s a removable dropped ceiling, placed 2.5 meters from the ground, covering the entire floor.
* The space over the ceiling is perfect to install cable raceways and wireless access-points.
* This floor has no underfloor cable raceways.
* Common areas (e.g. entrance hall, restrooms, etc.) require no network outlets.
* Room 2.1.12 is a storage area and requires no network outlets.

#### Outlets ####

* The outlets distribution was made taking into account the most suitable locations so that the room space was not
  too compromised while also avoiding their placement too close to doors.
* When positioning the outlets, it was also considered that the maximum distance between the outlet and the user should be 3 meters, facilitating the connection to user´s equipment.
* The number of outlets per room was determined based on a proportion of 2 outlets for every 10 m2 of area.
* All outlets are placed on the walls, close to the floor.

#### Copper Cables ####

* All the copper cables are placed on the wall.

#### Access Points ####

* In this floor, two access points were installed. They are in rooms 2.1.6 and 2.1.10.
* Each access point is responsible for managing an area of radio coverage around
  it called a cell. If we consider the diameter of the cell to be 50 meters only one access point
  would be needed, but in this case we are considering the possibility of interference because of the multiple
  walls of the building which led to the installation of two access points.

#### Floor Distributor (FD) ####

* The floor distributor is located in the room 2.1.12.

#### Consolidation Points (CP) ####

* Due to the reduced number of outlets, there's no need for consolidation points.

#### Cable types used ####

* To connect the outlets to the Floor Distributor (FD) the used one is copper cable CAT7.
* To connect the FD to the Building Distributor (Floor 0) it was used optic fiber monomode 8, since it allows to a most efficient and higher data transaction.

#### Quantities ####

|  Room  | Area(m2) | Width(m) | Length(m) | Number of Outlets |   CAT7 Cables(m)   |
|:------:|:--------:|:--------:|:---------:|:-----------------:|:------------------:|
| 2.1.1  |  25.02   |   6.95   |   3.60    |         6         | 6 x (62.39 + 2.50) |
| 2.1.2  |  25.02   |   6.95   |   3.60    |         6         | 6 x (58.22 + 2.50) |
| 2.1.3  |  25.02   |   6.95   |   3.60    |         6         | 6 x (54.42 + 2.50) |
| 2.1.4  |  25.02   |   6.95   |   3.60    |         6         | 6 x (50.44 + 2.50) |
| 2.1.5  |  25.02   |   6.95   |   3.60    |         6         | 6 x (46.44 + 2.50) |
| 2.1.6  |  30.83   |   4.45   |   6.93    |         8         | 8 x (36.84 + 2.50) |
| 2.1.7  |  30.83   |   4.45   |   6.93    |         8         | 8 x (28.95 + 2.50) |
| 2.1.8  |  30.83   |   4.45   |   6.93    |         8         | 8 x (27.49 + 2.50) |
| 2.1.9  |  30.83   |   4.45   |   6.93    |         8         | 8 x (19.63 + 2.50) |
| 2.1.10 |  30.83   |   4.45   |   6.93    |         8         | 8 x (18.49 + 2.50) |
| 2.1.11 |  28.75   |   4.15   |   6.93    |         6         | 6 x (10.37 + 2.50) |
| 2.1.12 |  11.43   |   1.65   |   6.93    |         0         |         0          |
| 2.1.13 |  30.83   |   4.45   |   6.93    |         8         | 8 x (76.73 + 2.50) |
| 2.1.14 |  30.83   |   4.45   |   6.93    |         8         | 8 x (81.42 + 2.50) |
| 2.1.15 |  30.83   |   4.45   |   6.93    |         8         | 8 x (86.12 + 2.50) |
| Total  | -------- | -------- | --------  |        100        |      4898.98       |

### Telecommunications enclosures ###

* Since there are 100 outlets in this floor, it's necessary to install three patch panels CAT7 with 48 ports each. This results in a size of 6U (2U for each patch panel).
* The enclosure will reach 6 times the U size for the patch panels, so that, the total size for this telecommunication enclosure will be 36U.
* Copper CAT7 patch cords required for each telecommunication enclosure equals the number of patch panel ports in each, meaning we need 144 short length patch cords.

## Total Inventory of Floor 1 ##

* In a fiber patch panel, each cable connection requires two fibres, so two connectors must be used.

|             Equipment              | Quantity |
|:----------------------------------:|:--------:|
|           Access Points            |    2     |
|       Copper Cable CAT7 (m)        | 4898.98  |
|     Copper Patch Cords (0.5 m)     |   144    |
|      Copper Patch Cords (5 m)      |   100    |
| Copper Patch Panel 2U (48 entries) |    3     |
|       Optic fiber cable (m)        |   4.45   |
|     Fiber Patch Cords (0.5 m)      |    8     |
| Fiber Patch Panel 1U (24 entries)  |    1     |
|              Outlets               |   100    |
|  Telecommunication Enclosures 36U  |    1     |

## Final Inventory ##

|             Equipment              |          Quantity           |
|:----------------------------------:|:---------------------------:|
|           Access Points            |   4 (two for each floor)    |
|         Optic Fiber Cable          |     2.18 + 4.45 = 6.63      |  
|         CAT7 Copper Cable          | 2055.89 + 4898.98 = 6954.87 |
|              Outlets               |       54 + 100 = 154        |
|     Copper Patch Cords (0.5 m)     |             240             |
|      Copper Patch Cords (5 m)      |             154             |
| Copper Patch Panel 2U (48 entries) |              5              |
|  Telecommunication Enclosure 24U   |              1              |
|  Telecommunication Enclosure 36U   |              1              |
|     Fiber Patch Cords (0.5 m)      |             16              |
| Fiber Patch Panel 1U (24 entries)  |              2              |
