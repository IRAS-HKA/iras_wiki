[Back to Home](../../README.md) / [1.4 Introductions](1.4-introductions.md) / [Markdown](markdown_instructions.md) / **Standard ROS README File**

<hr>

# ROS Package Name

Example structure from move_base (ROS1) [here](http://wiki.ros.org/move_base?distro=noetic)

Summary of repo function and general infos

## Interface:
- `first_node` (ROS Distro language)

    Node1 description

- `second_node` (ROS2 Foxy python)

    Node2 description

![node_graph](docs/node_graph.svg)

### Node1 Name
---

#### Topics
- subscribed `namespace/topic` (msg/type)
- published `namespace/topic` (custom type)
    ```bash
    # Type.msg
    std_msgs/Header header
    msg_type name
    ```

#### Services
- offered service (type definition)
- required service (type definition)

#### Actions
- offered action server (type definition)
- required action (type definition)

#### Parameters 
Change in `config/params.yaml`

```bash
parameter1: int # default integer value of param1
parameter1: "string # explanation
```

### Node2 Name
---
Description of Node2 interfaces (same as above)

## How to run:
### Dependencies
- package_name
- library

### Installation
```bash
# dependency installation instructions
pip3 install package_name
```

Make python skripts executable

    chmod +x <python_script>.py

Build packages with ros

    colcon build --symlink-install

### Start the nodes
```bash
# most important command
ros2 launch package_name launch_file.launch.py
```

### Launch files
- launch file 1
    List of launch files and explanation of node combination
- launch file 2

## Testing:
```bash
ros2 topic echo <topic_name>
```

## Todo:
- [x] create example README
- [ ] add to example packages
