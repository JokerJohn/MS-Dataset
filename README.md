# MS-Dataset
Large scale LiDAR-IMU dataset 

![image (15)](./README/image%20(15).png)

## sensor configuration

- Pandar XT32, +-**0.5cm**
- SBG INS : 100Hz IMU + GNSS + EKF filter
- 3DM-GQ7 INS: 700Hz IMU + dual GNSS-RTK + 30Hz Filter, >= **1.4cm**
- Mono Flir RGB camera (optional), it's hard to collect data with RTK-GNSS and RGB camera at the same time due to USB3.0.
- Ground Truth  RGB Point Cloud Map (indoor -> outdoor, **4mm**), collected by Leica BLK360 and RTC360.

## GT Trajectory

- From INS with cov less than **0.005m**. Users can also generate the gt with my scripts.
- Users can generate GT either from RTK-GNSS 1 or RTK-GNSS 2 with my scripts, but only with x y z yaw .
- KML file which can directly import by google map with my scripts.

|      | 3DM-INS                                                      | GNSS1                                                        | GNSS2                                                        | SBG-GNSS                                                     |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| RB03 | ![image-20240624131357960](./README/image-20240624131357960.png) | ![image-20240624131801414](./README/image-20240624131801414.png) | ![image-20240624131343201](./README/image-20240624131343201.png) | ![image-20240624131412226](./README/image-20240624131412226.png) |
| PK01 |                                                              | ![image-20240627071947142](./README/image-20240627071947142.png) | ![image-20240627072000320](./README/image-20240627072000320.png) |                                                              |
| CP05 | ![image-20240627072713997](./README/image-20240627072713997.png) | ![image-20240627072622052](./README/image-20240627072622052.png) | ![image-20240627072635693](./README/image-20240627072635693.png) | ![image-20240627072730361](./README/image-20240627072730361.png) |
| CP02 | ![image-20240627072854370](./README/image-20240627072854370.png) | ![image-20240627072809607](./README/image-20240627072809607.png) | ![image-20240627072821714](./README/image-20240627072821714.png) | ![image-20240627072834323](./README/image-20240627072834323.png) |
| RD01 | ![image-20240627073000945](./README/image-20240627073000945.png) | ![image-20240627072926561](./README/image-20240627072926561.png) | ![image-20240627072940627](./README/image-20240627072940627.png) |                                                              |
| CP01 | ![image-20240627073107324](./README/image-20240627073107324.png) | ![image-20240627073035768](./README/image-20240627073035768.png) | ![image-20240627073047934](./README/image-20240627073047934.png) |                                                              |
| GC01 | ![image-20240627073207972](./README/image-20240627073207972.png) | ![image-20240627073136950](./README/image-20240627073136950.png) | ![image-20240627073146802](./README/image-20240627073146802.png) | ![image-20240627073157026](./README/image-20240627073157026.png) |
| CC01 | ![image-20240627073243335](./README/image-20240627073243335.png) |                                                              |                                                              |                                                              |

## Data Description

| Dataset              | Description           | Sensors | Download Links | Ground Truth | Comments |
| -------------------- | --------------------- | ------- | -------------- | ------------ | -------- |
| Calib-IMU-Intrinsinc |                       |         |                |              |          |
| Calib-Camera-LiDAR   |                       |         |                |              |          |
| PK01                 | Degenerate parkinglot |         |                |              |          |
|                      |                       |         |                |              |          |
| RB02                 |                       |         |                |              |          |
| RB03                 |                       |         |                |              |          |
| CP05                 |                       |         |                |              |          |



## Issues

### How to adpate to different sensors

`rostopic echo /os1_cloud_node/points/fields -n1`

