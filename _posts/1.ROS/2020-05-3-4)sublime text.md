---
title: "ROS개발환경-4: Sublime text 설치 "
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

### 1.3 sublime text 정상설치 확인 

``` python
>~/catkin_ws$ rosed turtlesim Color.msg
```

### 1.4 혹시 roseb turtlesim Color.msg 안될시
`
* source ~/.bashrc 명령을 한 번 실행 할 것    
`

``` python
>source ~/.bashrc
```



` 
This post is based on [pinkwink](https://github.com/PinkWink) and [wiki.ros](http://wiki.ros.org/rosdep#INstalling_rosdep)

`
