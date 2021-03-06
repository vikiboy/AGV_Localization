====================================================================================================================================================================================================================
||										Robot_Localization_Package										  ||
====================================================================================================================================================================================================================
Documentation for robot_localization package

Code structure:
  Headers:

  Header files consist of ekf.h, filter_base.h, filter_common.h, ros_filter.h and ros_filter_types.h. The package has two types of filters- ekf and ukf. We'll be using ekf.filter_base.h declares the methods of FilterBase class, ekf.h declares the structure of the class Ekf that inherits from FilterBase, filter_common.h declares the memebers of the namespace RobotLocalization that are common to all. ros_filter.h contains most of the implementation details, including debug handling, error handling and RosFilter methods.All the publisher and subscriber calls are made in ros_filter.h. ros_filter_types.h merely typedefs RosFilter<Ekf> and RosFilter<Ukf>.

  Source: 

  The source files of importance to us consist of ekf.cpp, ekf_localization_node.cpp, filter_base.cpp and filter_base.cpp.set_pose. filter_base.cpp contains the definitions of methods declared in filter_base.h for the FilterBase class. ekf.cpp contains the implementation of ekf by defining the methods of class Ekf (declared in ekf.h). ekf_localization_node.cpp merely runs the runs the ekf_navigation_node.

Publishers/Subscribers:

  Subscribers:
     1. "set_pose": subscriber to set_pose data usually published by rviz
     2. odomTopic: subscriber to odometry data
     3. twistTopic: subscriber to twist data
     4. imuTopic: subscriber to imu data

  Publishers:
     1."odometry/filtered": publishes the filtered odometry data


====================================================================================================================================================================================================================
====================================================================================================================================================================================================================
