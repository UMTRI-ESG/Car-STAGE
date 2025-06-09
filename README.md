# Car-Stage
## Run CARLA simulations, fatser. 



Car-Stage is an one-stop solution to run CARLA simulation faster, easier, and and more efficiently.

## Features
- User-friendly GUI to run and manage simulation scenarios
- Three scenario modes supported:Random, Deterministic, Custom scenario-based
- Optimized data generation:Achieves 97.14% faster performance compared to standard CARLA implementation
- Sensor placement configurable directly from the GUI
- Camera annotations provided in KITTI format
- Calibration data included for all sensors
- Motion data available for the ego vehicle
- Weather conditions adjustable through the GUI
- Map switching supported from the GUI
- Mcity map included by default




## Installation

Download files from [Download v0.1](https://github.com/UMTRI-ESG/Car-STAGE/releases/tag/v0.1) and make sure all of them are in the same folder and unzip only the CarStageDist.zip file, the rest will be prpocesed by shell script file. 

### Files are:
- CarStageDist.zip: the Car-Stage GUI
- Config.zip: config files
- McityMap.zip: Mcity Map files
- prepare_carla.sh: shell script to download CARLA 0.9.15, unzip it, unzip Config.zip and McityMap.zip as well as move files to appropriate location. 

```sh
cd zip_files_folder
chmod +x prepare_carla.sh
./prepare_carla.sh "optional_new_carla_folder"
```

The shell script will do the following:
1-download CARLA 0.9.15
2-Unzip config.zip file
3- Unzip McityMap.zip file and move it to CARLA maps subfolder.


## Run
1- Go to CARLA folder and run CARLA server. It is best if you run CARLA server in RenderOffScreen mode
```sh
./CarlaUE4.sh -RenderOffScreen
```
2- Run GUI by clicking on CarStageGUI file inside CarStageDist/dist folder ![Car-Stage GUI](https://github.com/UMTRI-ESG/Car-STAGE/blob/main/CarStageGUI.png)

The first thing to do is to set CARLA folder path in GUI, you have to do that once, then Car-Stage will save the setting for future use.



## Scenarios:
- TM-Random: random using CARLA traffic manager
- TM-Deterministic: accept 7 values with space between them. Seed start_x start_y start_z end_x end_y end_z
- Scenario : using Scenic syntax...still in tetsing

#### Note:
In TM-Deterministic mode, it is recommended to increase the duration time in the GUI. The Car-Stage will stop either when the specified duration is reached or when the ego vehicle reaches its destination.


