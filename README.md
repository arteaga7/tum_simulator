tum_simulator on ROS Kinetic and Gazebo 7
--------------------------

These packages are used to simulate the flying robot Ardrone in ROS environment using gazebo simulator. Totally they are 4 packages. Their functions are descript as below:

1. cvg_sim_gazebo: contains object models, sensor models, quadrocopter models, flying environment information and individual launch files for each objects and pure environment without any other objects.

2. cvg_sim_gazebo_plugins: contains gazebo plugins for the quadrocopter model. quadrotor_simple_controller is used to control the robot motion and deliver navigation information, such as: /ardrone/navdata. Others are plugins for sensors in the quadrocopter, such as: IMU sensor, sonar sensor, GPS sensor.

3. message_to_tf: is a package used to create a ros node, which transfers the ros topic /ground_truth/state to a /tf topic.

4. cvg_sim_msgs: contains message forms for the simulator.

Some packages are based on the tu-darmstadt-ros-pkg by Stefan Kohlbrecher, TU Darmstadt.

This package depends on ardrone_autonomy package and gazebo7 so install these first.

How to install the simulator:

1. Install ardrone_autonomy package

   $ sudo apt-get install ros-kinetic-ardrone-autonomy

2. Create a workspace for the simulator

    $ mkdir -p ~/tum_simulator/src
    
    $ cd  ~/tum_simulator/src
    
    $ catkin_init_workspace

2. Download package

    $ git clone https://github.com/arteaga7/tum_simulator.git

3. Build the simulator

    $ cd ..
    
    $ catkin_make

4. Source the environment

    $ source devel/setup.bash

How to run the simulation:

1. Run a simulation by executing a launch file in cvg_sim_gazebo package:

    $ roslaunch cvg_sim_gazebo ardrone_testworld.launch


