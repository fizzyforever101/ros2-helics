# ros2-helics
Files Required to Link HELICS and ROS2 + Instructions to Run Sample

## Installation

1. Follow the tutorial [here](https://docs.helics.org/en/latest/user-guide/installation/linux.html) to build HELICS from source. Be sure to export your installation path to your .bashrc file.
Example:
![image](https://github.com/fizzyforever101/ros2-helics/assets/67799193/5be8046f-804e-4b20-b10c-c5bde81d1fec)


3. Assuming you followed the ROS2 humble tutorial (https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Colcon-Tutorial.html) and built all of the examples, you can navigate to ~/ros2_ws/src/examples/rclcpp/topics/ in your terminal to find the minimal_subscriber and minimal_publisher directories.

4. Replace the `member_function.cpp` and `package.xml` files in the "minimal_publisher" directory with the ones included in this repository and update the `CMakeLists.txt file` there with `include(~/path/to/HELICSConfig.cmake)`, `target_link_libraries(publisher_member_function HELICS::helics)`, and `target_include_directories(publisher_member_function PRIVATE ~/path/to/HELICS/build/lib)`. These additions are required to link the header-only HELICS C++ library with ROS2.
![image](https://github.com/fizzyforever101/ros2-helics/assets/67799193/72566a29-62db-482b-9315-df787adc5f92)

## Running Example

1. Navigate to ~/ros2_ws (the name of your ROS2 overlay folder) and source the environment (source install/setup.bash). Run (ros2 run examples_rclcpp_minimal_subscriber subscriber_member_function) where examples_rclcpp_minimal_subscriber is the package name and subscriber_member_function is the node name).

2. In another terminal window, navigate to ~/ros2_ws (the name of your ROS2 overlay folder) and source the environment (source install/setup.bash). Run (ros2 run examples_rclcpp_minimal_publisher publisher_member_function) where examples_rclcpp_minimal_publisher is the package name and publisher_member_function is the node name).

Example Expected Output:
![image](https://github.com/fizzyforever101/ros2-helics/assets/67799193/83eb99a9-4a9e-43b8-952e-4b9b03c707f4)

## Resources

- HELICS C++98 API documentation: https://docs.helics.org/en/latest/doxygen/helicsCore_8h.html#a09ce7e2dda0bdee3fb77602c1f451554
- Sabina's VIP Notebook for Troublehshooting Documention: https://github.com/cps-vip/cps-cosimulation-env/wiki/Sabina-Sokol's-Notebook
- ROS2 Humble Tutorial on Colcon: https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Colcon-Tutorial.html
- ROS2 Humble Tutorial on Creating Packages: https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Creating-Your-First-ROS2-Package.html
- ROS2 Humble Tutorial on Creating Publishers/Subscribers: https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Writing-A-Simple-Cpp-Publisher-And-Subscriber.html
