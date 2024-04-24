# remote_robot_control
here how to connect website from defferant device to our robot

## 1.Frist you need to write your HTML and CSS and javascript for your website 

## 2.Use  `Robot Web Tools` for write javascript for connect to robot via ros bridge

### after done this and test it locally in same pc with simulation 

## Frist in your robot :

1. start your ros master but the master `export` in same  network with :
```bash
export ROS_IP="YOUR_NETWORK_IP" # EX: 192.168.1.17
```
2. start your master

```bash
roscore
```
3. start your robot open to connect from other devices
```bash 
ping 192.168.1.17 # same network 
```
## Second Other device

frist install `ssh_server`
```bash
sudo apt install openssh-server
```

1. start connect to robot with simple line 
```bash
ssh 192.168.1.17
```

#### output will be :

pic

### now from this terminal you in your robot can see files and navigate in it or any thing

## Now we want to start our web site

#### in your robot

just start ros bridge 
```bash
roslaunch rosbridge_server rosbridge_websocket.launch
```
#### in other device 
navigate to your website in your robot with terminal that connected to robot with `cd`

##### start website 
```bash
python3 -m http.server -b 192.168.1.17 7000 # with your real ip
```