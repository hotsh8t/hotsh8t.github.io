---
title: "ROS: ROS와 의존성 문제해결을 위한 rosdep설치"
excerpt: "HW5_visualization_and_eda" 
date: 9999-12-31
categories:
  - ROS
tag :
  - ROS, rosdep
---


### 1.1 Download
``` python
>sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/
sources.list.d/ros-latest.list'
```


### 1.2 Keys for downloading packages from ROS repository
``` python
>sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key
C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

```


### 1.3 Ubuntu update before installing ROS
``` python
>sudo apt update
```

``` python
>sudo apt-get update && sudo apt-get upgrade -y
```


### 1.4 Install and update rosdep
``` python
>sudo apt-get install python-rosdep
>sudo rosdep update
```


### 1.5 rosdep init
``` python
>sudo rosdep init
>sudo rosdep update
```
 

#1.6 Environment setup
``` python
>echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
>source ~/.bashrc
```


### 1.7 Dependencies for building packages
```python
sudo apt install python-rosinstall python-rosinstall-generator python-wstool build-essential
```
 
This post is based on [pinkwink](https://github.com/PinkWink), [wiki.ros](http://wiki.ros.org/rosdep#INstalling_rosdep)
