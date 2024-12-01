# **f1tenth_race_stack**

The autonomous racing stack for the HMCar team at HMCL.

---

## **Setup Instructions**

Follow the steps below to set up the workspace and build the project:

### **1. Create the Workspace**
```bash
mkdir -p ~/f1tenth_ws/src
cd ~/f1tenth_ws/src
```

### **2. Clone the Repository**
```bash
git clone --recursive https://github.com/jsryu118/f1tenth_race_stack.git
```


### **3. Update Submodules**
```bash
cd f1tenth_race_stack
git submodule update --remote --init --recursive
```

### **4. Install Dependencies**
```bash
cd ~/f1tenth_ws
rosdep install --from-paths src --ignore-src -r -y
```

### **5. Build the Workspace**
```bash
colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release
# or
colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release --packages-select <package_name>
```

### **6. Multi Agent System**
```bash
# This sets the namespace and frame ID for the vehicle.
export F1TENTH_CAR_NAME='carname'

# Additionally, the joy_node should be executed as follows to ensure proper topic remapping:
ros2 run joy joy_node --ros-args -r /joy:=/carname/joy

```
