# Dynamic_logistics_Warehouse
Gazebo simulation of dynamics environment in warehouses.An extensive model of AWS-robomaker-small-warehouse.


![test2](https://user-images.githubusercontent.com/27731036/125345353-06dc6b00-e38b-11eb-9d00-1f5a59baee65.gif)





## Building and Launching the Gazebo World with your ROS Applications

* Create or update a **.rosinstall** file in the root directory of your ROS workspace. Add the following line to **.rosintall**:

 

* Change the directory to your ROS workspace and run `rosws update`

* Add the following include to the ROS launch file you are using:

  ```xml
  <launch>
  <!-- Launch World -->
  <include file="$(find dynamic-logistics-warehouse)/launch/logistics-warehouse.launch"/>
  ...
  </launch>
  ```

* Build your application using `colcon`

  ```bash
  rosws update
  rosdep install --from-paths . --ignore-src -r -y
  colcon build
  ```

## Example: Running this world directly in Gazebo without a ROS application

To open this world in Gazebo, change the directory to your ROS workspace root folder and run:

```bash
cd dynamic-logistics-warehouse
export GAZEBO_MODEL_PATH=`pwd`/models
gazebo worlds/logistics-warehouse.world
```




  

## Example: Running this world directly using ROS without a simulated robot

To launch this base Gazebo world without a robot, clone this repository and run the following commands. **Note: ROS and gazebo must already be installed on the host.** 

```bash
# build for ROS
rosdep install --from-paths . --ignore-src -r -y
colcon build

# run in ROS
source install/setup.sh
roslaunch dynamic-logistics-warehouse logistics-warehouse.launch
```
