# Unitree G1 Robot


https://support.unitree.com/home/en/G1_developer



```bach
ssh unitree@192.168.123.164
```

run Nomachin 

```bach
./nomachine.sh 
```

Open Nomachin apps to connect remotly to the robot

## ROS2 

run `ros2 topic list`

Error 

```bach
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
bad_alloc caught: std::bad_alloc
```

To slove the issue run the follwing
```bach
source unitree_ros2/setup.sh 
```

For more dealis follow the Network configuration in https://github.com/MohammadRobot/unitree_ros2 


