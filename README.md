# drims_summerschool
These are the main repository for the DRIMS Summer School:
 - [drims_cells](https://github.com/CNR-STIIMA-IRAS/drims_cells): Contains robot descriptions, controllers, and launch files for setting up simulations and/or establishing communication with real robots.
 - [easy_motion](https://github.com/CNR-STIIMA-IRAS/easy_motion): Provides APIs, ROS actions, and Behavior Tree nodes for basic robot movements.
 - [drims_dice_simulator](https://github.com/CNR-STIIMA-IRAS/drims_dice_simulator): Offers a simulator for a dice.

For usage instructions and setup details, please refer to each package’s README.

# To use the robots (TEMPORARY FIX for 03/09/2026)

Inside the DRIMS2026 docker:

1. Download [drims_cells](https://github.com/CNR-STIIMA-IRAS/drims_cells) and [ur_utils_ros2_py](https://github.com/MerlinLaboratory/ur_utils_ros2_py) inside the `drims_ws` workspace
   ```bash
   cd /home/drims/drims_ws/src
   git clone https://github.com/CNR-STIIMA-IRAS/drims_cells.git
   git clone https://github.com/MerlinLaboratory/ur_utils_ros2_py.git
   ```
2. Build the workspace
   ```bash
   cd /home/drims/drims_ws
   colcon build
   ```
3. source workspace
   ```bash
   source /home/drims/drims_ws/install/setup.bash
   ```

#### IMPORTANT!!
On every new terminal that connect to the docker, run:

```bash
unset ROS_LOCALHOST_ONLY
export ROS_DOMAIN_ID=<YOUR-GROUP-NUMBER>
```

where `<YOUR-GROUP-NUMBER>` is the number of your group.


### IMPORTANT FOR THE CAMERA

To launch the camera:

```bash
ros2 launch depthai_ros_driver camera.launch.py namespace:=camera
```
