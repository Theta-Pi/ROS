### ROS basic concepts

Start [here](http://wiki.ros.org/ROS/Concepts){:target="_blank"} and explain to yourself
- ROS master
- nodes
- topics and services. Whats the difference? 

### First steps
- [Creating a workspace for catkin](http://wiki.ros.org/catkin/Tutorials/create_a_workspace){:target="_blank"}

source setup.bash in order to use the catkin workspace:
```markdown
source ~/catkin_ws/devel/setup.bash
```

- [Creating a catkin Package](http://wiki.ros.org/catkin/Tutorials/CreatingPackage){:target="_blank"} 
```markdown
catkin_create_pkg <package_name>```

### Basic commands

- roscore: starts a new ROS master
- rosnode list: lists nodes in a ROS computation graph
- rostopic list: lists topics ina ROS computation graph

Run a new node: rosrun [package name] [node name]
```markdown rosrun turtlesim turtlesim_node```
turtle_teleop_key

get info of node: ```markdown rosnode info /turtlesim```
get info of topic: ```markdown rostopic info /turtle1/cmd_vel```
show the contents os a message: ```markdown rosmsg show geometry_msgs/Twist ```

Publish message on a topic using CMD:
rostopic pub -r 10
/turtle1/cmd_vel
geometry_msgs/Twist
{linear: {x: 0.1, y: 0.0, z: 0.0}, angular {x: 0.0, y: 0.0, z: 0.0}}
this will move the robot repeatedly (-r) for 10sec with x velocity = 1
Show the ROS computation graph: ```markdown rosrun rqt_graph rqt_graph```

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown

Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Theta-Pi/ROS/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
