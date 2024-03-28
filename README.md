# ros2-helics
Files Required to Link HELICS and ROS2 + Instructions to Run Sample

## Installation

1. Install the pre-compiled HELICS libraries from https://github.com/GMLC-TDC/HELICS/releases somewhere in your ROS2 Ubuntu container and export the install path (make sure to do source ~/.bashrc).
   ![image](https://github.com/fizzyforever101/ros2-helics/assets/67799193/5987e384-8382-4bb0-abb0-43c26d3a63f1)

2. If you followed the ROS2 humble tutorial (https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Colcon-Tutorial.html) and built all of the examples, you can navigate to ~/ros2_ws/src/examples/rclcpp/topics/ in your terminal to find the minimal_subscriber and minimal_publisher folders. If not, you can follow the steps in the package creation tutorial (https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Creating-Your-First-ROS2-Package.html) to build your own package.

3. Add/replace the 4 files within the minimal_subscriber folder on the VM with the ones in the subscriberFiles folder provided here. Do the same with the publisher files.

## Running Example

1. Navigate to ~/ros2_ws (the name of your ROS2 overlay folder) and source the environment (source install/setup.bash). Run (ros2 run examples_rclcpp_minimal_subscriber subscriber_member_function) where examples_rclcpp_minimal_subscriber is the package name and subscriber_member_function is the node name).

2. In another terminal window, navigate to ~/ros2_ws (the name of your ROS2 overlay folder) and source the environment (source install/setup.bash). Run (ros2 run examples_rclcpp_minimal_publisher publisher_member_function) where examples_rclcpp_minimal_publisher is the package name and publisher_member_function is the node name).

Example Expected Output:
![image](https://github.com/fizzyforever101/ros2-helics/assets/67799193/83eb99a9-4a9e-43b8-952e-4b9b03c707f4)

NOTE: If you get a ZMQ broker error, just re-run both the publisher and subscriber. It is unclear why this is an issue and is currently being investigated by the HELICS development team.

## Resources

- HELICS C++98 API documentation: https://docs.helics.org/en/latest/doxygen/helicsCore_8h.html#a09ce7e2dda0bdee3fb77602c1f451554
- Sabina's VIP Notebook for Troublehshooting Documention: https://github.com/cps-vip/cps-cosimulation-env/wiki/Sabina-Sokol's-Notebook
- ROS2 Humble Tutorial on Colcon: https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Colcon-Tutorial.html
- ROS2 Humble Tutorial on Creating Packages: https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Creating-Your-First-ROS2-Package.html
- ROS2 Humble Tutorial on Creating Publishers/Subscribes: https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Writing-A-Simple-Cpp-Publisher-And-Subscriber.html
