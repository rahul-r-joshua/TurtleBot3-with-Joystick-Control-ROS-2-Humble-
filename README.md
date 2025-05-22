
# 🐢 TurtleBot3 Joystick SSH Launch Guide

Easily control your TurtleBot3 remotely using SSH and a joystick with these steps.

---

## 🔌 Step 1: Connect via SSH and Launch the Robot (Terminal 1)

```bash
ssh ubuntu@192.168.0.229  # 📡 Connect to your TurtleBot via SSH

export TURTLEBOT3_MODEL=burger  # 🧠 Set the model type

ros2 launch turtlebot3_bringup robot.launch.py  # 🚀 Launch bringup
```

---

## 🎮 Step 2: Enable Joystick Input (Terminal 2)

```bash
ssh ubuntu@192.168.0.229  # 📡 Same IP as Terminal 1

export TURTLEBOT3_MODEL=burger

# ✅ Give read/write access to joystick devices
sudo chmod +rw /dev/input/js0
sudo chmod +rw /dev/input/event0

# 🚀 Start the joystick node
ros2 run joy joy_node
```

---

## 🕹️ Step 3: Start Stick Control (Terminal 3)

```bash
ssh ubuntu@192.168.0.229  # 📡 Same IP again

export TURTLEBOT3_MODEL=burger

# 🛠️ Run your custom stick control node
ros2 run stick_control stick_control
```

---

## 🌐 Find Your TurtleBot3 IP Address

If you're not sure of the IP address, run this on the TurtleBot:

```bash
ifconfig
```

🔍 Look for the `inet` address:
```
inet xxx.xxx.x.xxx   # ← This is your TurtleBot's IP for SSH
```

---

✅ Now you're ready to drive your TurtleBot3 using the joystick over SSH!
