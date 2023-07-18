# Robot_Arm_Simulation_on_ROS
### Install ROS melodic with Ubuntu 18.04
http://wiki.ros.org/melodic/Installation/Ubuntu
- Setup the sources list: ```sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'```
- Set up the keys: ```sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654```
- Make sure your Debian package index is up-to-date: ```sudo apt update```
- Install this ros version (Recommended): ```sudo apt install ros-melodic-desktop-full```
- Environment setup: ```echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc 
  source ~/.bashrc```
- Dependencies for building packages: ```sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential```
- Initialize rosdep: ```sudo apt install python-rosdep```
sudo rosdep init
rosdep update
### Create a workspace by using catkin_make:
- ```source /opt/ros/melodic/setup.bash```
- ```mkdir -p ~/catkin_ws/src```
- ```cd ~/catkin_ws/```
- ```catkin_make```
- ```echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc```
### Installing the package arduino_robot_arm
- Add the “arduino_robot_arm” package to “src” folder: 
	```cd ~/catkin_ws/src```
	```sudo apt install git```
	```git clone https://github.com/smart-methods/arduino_robot_arm```
- Install all the dependencies: 
	```cd ~/catkin_ws```
	```rosdep install --from-paths src --ignore-src -r -y```
	```sudo apt-get install ros-melodic-moveit```
	```sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui```
	```sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher```
	```sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control```
- Compile the package: 
 ```catkin_make```
(if you faced an error with catkin_make command in this case run: ```pip3 install -U rosdep rosinstall_generator wstool rosinstall six vcstools```)
### Controlling the motors
- ```roslaunch robot_arm_pkg check_motors.launch```
  
  ![image](https://github.com/Rama-Alyoubi/Robot_Arm_Simulation_on_ROS/assets/128150728/7d1117af-e50a-43bf-afe6-06f2075341eb)
