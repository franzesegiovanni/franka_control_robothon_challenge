# Franka Human Friendly Controllers
To install:
- Create a workspace containing a src directory.
- Inside the src directory, clone the franka_ros repository by frankaemika.
- Inside the repository, clone this repository.
- Return to the workspace main directory (cd ../..).
- Source your version of ROS (e.g. ```source /opt/ros/melodic/setup.bash```).
- Build the project, calling: 
 ```
 catkin_make -DMAKE_BUILD_TYPE=Release -DFranka_DIR:PATH=/path/to/libfranka/build 
 ```

To run the controller:
- Switch on your Panda robot (make sure the gripper is initialized correctly), unlock its joints (and activate the FCI if necessary).
- Open a terminal, in every terminal: ```source devel/setup.bash```
- ```roslaunch franka_human_friendly_controllers cartesian_variable_impedance_controller.launch robot_ip:=ROBOT_IP load_gripper:=True```
- In a different terminal (don't forget to source again): ``` rosrun franka_human_friendly_controllers franka_gripper_online ```
# Disagreement-aware Variable Impedance controller (DAVI)
To run the demo of teaching the robot where and how to place a paper cup:
- Open a new terminal in src/franka_human_friendly_controllers/python/DAVI
- Run the main file: ```python3 main.py```

The robot will move to make the gripper face down, and then switch to gravity compensation.
The robot can now be moved to the desired initial end-effector position.
Upon pressing enter, the model is further initialized and the Episodes can be started and quit via the keyboard.

Watch our demo here: https://youtu.be/toIUuFguFgM

  
  
