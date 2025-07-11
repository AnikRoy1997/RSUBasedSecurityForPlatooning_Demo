# RSUBasedSecurityForPlatooning_Demo
This repository contains video demonstrations of the experiments done in our work titled ["Optimizing RSU Placements for Securing Vehicle Platoon Against False Data Injection Attacks"](https://dl.acm.org/doi/10.1145/3576841.3589621).

## 1. A 4-Vehicle Platoon
The video below demonstrates a simulation of a platoon consisting of 4 vehicles crusing along a 4 lane highway using DSRC communication protocol and equipped with CACC controller. The setup consists of SUMO and OMNeT++ simulators. SUMO is an open source road traffic simulator that models and visuializes road traffic in uban scenario. OMNeT++ is a network simulator that contains the necessary network protocol libraries for wireless communication. Additionally, for cooperative driving such as platooning using the DSRC communication, we use Veins and Plexe libraries for OMNeT++.

https://user-images.githubusercontent.com/85755568/220275406-57839c83-7f7d-44c5-8431-79f9eab5191d.mp4

## 2. Platooning Under FDI Attack
With reference to the video below, the 2nd vehicle in the platoon is the attacker. The bottom right screen of the video shows the falsified velocity data that the attacker sends to the trailing vehicles. As an immediate effect of this attack, the space between the 2nd and 3rd (victim) vehicles increases and goes beyond the performance bound(8m). This is evident from the bottom left screen of the video which shows the measured inter-vehicle distance by the victim vehicle.

https://user-images.githubusercontent.com/85755568/220275815-e00a9045-86ed-4949-b0c4-64762dc0b0f8.mp4

## 3. RSU-based Attack Detection and Mitigation (using 3 RSUs) for Platoons under FDI Attack
The video below demostrates RSU-based attack detection and mitigation for platoons under FDI attack. As seen in the video below, We place 3 RSUs at an inter-RSU distance of 400m along the road such that every vehicle in the platoon comes within the 200m communication range of at least one RSU. The broadcasted information of the platoon vehicles are recorded by the RSUs within communication range. The platoon vehicles receive this recorded information from the RSU as a redundant source of knowledge. The bottom left screen in the video shows the detection procedure in the 3rd platoon vehicle. It raises an alarm whenever the difference between the inter-vehicle distances calculated using the data received from the predecessor and data received from the RSU crosses a certain threshold (0.5m). Whenever an alarm is raised, the victim vehicle comprehends a possible data falsification attempt by the predecessor vehicle and switches to Adaptive Cruise Control (ACC) mode. In this mode, the victim vehicle uses the actual spacing computed by using the RSU data (instead of using the data received from the predecessor) and approaches to maintain a safe desired spacing of 5m. This allows the platoon to be within performance bound.

https://user-images.githubusercontent.com/85755568/220276367-7405f6f7-9608-4c19-b625-c0072ad9be48.mp4

## 3. RSU-based Attack Detection and Mitigation (using 2 RSUs) for Platoons under FDI Attack
The video below demostrates RSU-based attack detection and mitigation for platoons under FDI attack, with reduced number of RSUs. As seen in the video below, we reduce the number of RSUs to 2, where at an inter-RSU distance is 800m. The communication range of each RSU is same as the previous simulation, i.e., 200m. The blind spot between the two RSUs is approximately 400m. The bottom right screen in the video below depicts that the CACC controller under attack in the 3rd vehicle can keep the platoon performance and safety within desired range even if the victim vehicle is not within the communication range of the RSU-based attack detection for a certain distance (blind spot).

https://user-images.githubusercontent.com/85755568/220276447-df5ddd01-8891-4ef9-a966-2d3f83015876.mp4

### Poster

[AnikRoy_ICCPS_23_posterFinal.pdf](https://github.com/user-attachments/files/21177994/AnikRoy_ICCPS_23_posterFinal.pdf)


## Citation
```shell
@inproceedings{OptRSUplacement,
author = {Roy, Anik and Koley, Ipsita and Adhikary, Sunandan and Dey, Soumyajit},
title = {Optimizing RSU Placements for Securing Vehicle Platoon Against False Data Injection Attacks},
year = {2023},
isbn = {9798400700361},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3576841.3589621},
doi = {10.1145/3576841.3589621}
booktitle = {Proceedings of the ACM/IEEE 14th International Conference on Cyber-Physical Systems (with CPS-IoT Week 2023)},
pages = {251–252},
numpages = {2},
location = {San Antonio, TX, USA},
series = {ICCPS '23}
}
```
