---
title: "ROS:Install ROS, rosdep"
date: 9999-12-31
categories:
  - ROS
---


### 1.1 download
``` python
>sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/
sources.list.d/ros-latest.list'
```

### 1.2 keys for downloading packages from ROS repository
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

#1.4 installing and update rosdep
``` python
>sudo apt-get install python-rosdep
>sudo rosdep update
```

#1.5 rosdep init
``` python
>sudo rosdep init
>sudo rosdep update
```
  
This post is based on [pinkwink](http://www.google.co.kr“구글”), [wiki.ros](http://wiki.ros.org/rosdep#INstalling_rosdep)
