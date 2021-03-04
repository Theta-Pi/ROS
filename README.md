### ROS basic concepts

Start [here](http://wiki.ros.org/ROS/Concepts){:target="_blank"} and explain to yourself
- what is ROS master?
- what are ROS nodes?
- what are topics and services? Whats the difference? 

### First steps
- [Creating a workspace for catkin](http://wiki.ros.org/catkin/Tutorials/create_a_workspace){:target="_blank"}

source setup.bash in order to use the catkin workspace: 
`source ~/catkin_ws/devel/setup.bash`

- [Creating a catkin Package](http://wiki.ros.org/catkin/Tutorials/CreatingPackage){:target="_blank"} 
- `catkin_create_pkg <package_name>`

- roscore: starts a new ROS master
- rosnode list: lists nodes in a ROS computation graph
- rostopic list: lists topics ina ROS computation graph

Run a new node: rosrun [package name] [node name]
`rosrun turtlesim turtlesim_node`

`turtle_teleop_key`

get info of node: `rosnode info /turtlesim`

get info of topic: `rostopic info /turtle1/cmd_vel`

get info on message `rosmsg show geometry_msgs/Twist`

show the contents os a message: `rosmsg show geometry_msgs/Twist`

Publish message on a topic using CMD:

``` rostopic
pub -r 10 
/turtle1/cmd_vel
geometry_msgs/Twist
'{linear: {x: 0.1, y: 0.0, z: 0.0}, angular {x: 0.0, y: 0.0, z: 0.0}}' 
```

this will move the robot repeatedly (-r) for 10sec with x velocity = 1

Show the ROS computation graph: `rosrun rqt_graph rqt_graph`

`rostopic` to list available rostopic commands
`rostopic echo /turtle1/cmd_vel` will echo cmd_vel messages

- [Publisher / Subscriber](http://wiki.ros.org/rospy/Overview/Publishers%20and%20Subscribers){:target="_blank"} 

Creating custom messages:
- [ROS wiki link here](http://wiki.ros.org/action/show/msg){:target="_blank"} 

in package.xml add:
<build_depend>message_generation</build_depend>
<exec_depend>message_runtime</exec_depend>

in CMakeLists.txt add inside:
find_package(catkin REQUIRED COMPONENTS
  ...
  message_generation
)
add_message_files(
   ...
   IoTSensor.msg 
) 
catkin_package(
  ...
  CATKIN_DEPENDS ... message_runtime
  ...
)
dont forget to complile by using catkin_make in catkin_ws
### Resources
- [Markdown cheatlist](https://aksakalli.github.io/jekyll-doc-theme/docs/cheatsheet/){:target="_blank"} 
- [jekyll-theme](https://github.com/topics/jekyll-theme){:target="_blank"} 
