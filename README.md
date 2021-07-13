
# Dynamic_logistics_Warehouse

Gazebo simulation of dynamics environment in warehouses. An extensive model of AWS-robomaker-small-warehouse.

### Specifications:
* 9 Actors following different waypoints to perform trajectory path.
* 5 Light sources 
* Shelves
* PalletJack
* Desks
* Trashcan
* Cluttering


  


![test](https://user-images.githubusercontent.com/27731036/125352251-98e87180-e393-11eb-8feb-56853ab26f72.gif)
  <launch>








## Building and Launching the Gazebo World with your ROS Applications

* Create or update a **.rosinstall** file in the root directory of your ROS workspace. Add the following line to **.rosintall**:

 

* Change the directory to your ROS workspace and run `rosws update`

* Add the following include to the ROS launch file you are using:

  ```xml

  <!-- Launch World -->
  <include file="$(find dynamic_logistics_warehouse)/launch/logistics_warehouse.launch"/>
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
gazebo worlds/warehouse.world
```




  

## Example: Running this world directly using ROS without a simulated robot

To launch this base Gazebo world without a robot, clone this repository and run the following commands. **Note: ROS and gazebo must already be installed on the host.** 

```bash
# build for ROS
rosdep install --from-paths . --ignore-src -r -y
colcon build

# run in ROS
source install/setup.sh
roslaunch dynamic_logistics_warehouse logistics_warehouse.launch
```
### You can buy me a coffee via:
<a href="https://www.buymeacoffee.com/beraru" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-blue.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>
