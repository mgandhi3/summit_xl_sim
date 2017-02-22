# summit_xl_common
Common packages of the Summit XL: URDF description of the Summit XL and Summit XL HL, platform messages and other files for simulation.

![Image of Summit XL](http://www.robotnik.es/web/wp-content/uploads/2014/03/summit-xl-robots-moviles-robotnik_s01.jpg)

<h2>summit_xl_description</h2>

The urdf, meshes, and other elements needed in the description are contained here. The standard camera configurations have been included (w/wo sphere_camera, w/wo axis_camera, etc.). This package includes the description of the Summit XL, Summit XL OMNI (and HL versions) mobile platforms.
The package includes also some launch files to publish the robot state and to test the urdf files in rviz.

<h2>summit_xl_localization</h2>

This package contains launch files to use the EKF of the robot_localization package with the Summit XL robots. It contains a node to subscribe to gps data and publish it as odometry to be used as an additional source for odometry.

<h2>summit_xl_navigation</h2>

This package contains all the configuration files needed to execute the AMCL and SLAM navigation algorithms in simulation.

<h2>summit_xl_pad</h2>

This package contains the node that subscribes to /joy messages and publishes command messages for the robot platform including speed level control. The joystick output is feed to a mux (http://wiki.ros.org/twist_mux) so that the final command to the robot can be set by different components (move_base, etc.)

The node allows to load different types of joysticks (PS4, PS3, Logitech, Thrustmaster). New models can be easily added by creating new .yaml files. If modbus_io node is available, the digital outputs (ligths, axes, etc.) can also be controlled with the pad. If ptz camera is available, the pan-tilt-zoom can also be commanded with the pad. 

launch files that launch the complete simulation of the robot




<h2>Simulating Summit XL</h2>

1) Install the following dependencies:
  - summit_xl_common [link](https://github.com/RobotnikAutomation/summit_xl_common)
  - robotnik_msgs [link](https://github.com/RobotnikAutomation/robotnik_msgs)
  - robotnik_sensors [link](https://github.com/RobotnikAutomation/robotnik_sensors)

2) Launch Summit XL simulation with: <br>
  - roslaunch summit_xl_sim_bringup summit_xl_complete.launch
  
3) Enjoy! You can use the topic "/summit_xl_control/cmd_vel" to control the Summit XL robot.
