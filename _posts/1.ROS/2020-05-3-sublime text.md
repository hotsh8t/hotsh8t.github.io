---
title: "ROS개발환경: Sublime text 설치 "
excerpt: "ROS 개발을 위한 sublime text 설치" 
date: 9999-12-31
categories:
  - ROS
tag :
  - ROS, sublime text
---


### 1.1 sublime text설치
 

``` python
>~/catkin_ws$ wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
>~/catkin_ws$ sudo apt-add-repository "deb https://download.sublimetext.com/ apt/stable/"4
>~/catkin_ws$ sudo apt install sublime-text
```


### 1.2 bashrc 파일을 sublime text로 열기
``` python
>~/catkin_ws$ subl ~/.bashrc
```


### 1.3 bashrc 파일에 내용 추가
``` python
#추가 
export EDITOR='subl'
soruce /opt/ros/melodic/setup.bash
source ~/catkin_ws/devel/setup.bash
```

### 1.3 catkin_ws 초기화
* 반드시 catkin_ws 폴더에서 catkin init 를 해야 한다. 

``` python
>cd catkin_ws
>cd catkin init
```

` 
This post is based on [pinkwink](https://github.com/PinkWink) and [wiki.ros](http://wiki.ros.org/rosdep#INstalling_rosdep)

`
