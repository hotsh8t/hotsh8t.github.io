---
title: "ROS개발환경-2: CATKIN 설치 "
excerpt: "ROS 개발을 위한 CATKIN설치" 
date: 9999-12-31
categories:
  - ROS
tag :
  - ROS, catkin
---


### 1.1 catkin tools 설치
* catkin_tools의 설치 안내 [페이지](https://catkin-tools.readthedocs.io/en/latest/installing.html)

``` python
>sudo apt-get install python-catkin-tools
```


### 1.2 catkin_ws 폴더 생성
``` python
>mkdir -p ~/catkin_ws/src

```


### 1.3 catkin_ws 초기화
* 반드시 catkin_ws 폴더에서 catkin init 를 해야 한다. 

``` python
>cd catkin_ws
>cd catkin init
```

 
This post is based on [pinkwink](https://github.com/PinkWink) and [wiki.ros](http://wiki.ros.org/rosdep#INstalling_rosdep)
