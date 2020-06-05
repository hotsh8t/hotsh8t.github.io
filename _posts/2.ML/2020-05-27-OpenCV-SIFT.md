---
title: "ML : SIFT(Scale-Invarient Feature Transform "
excerpt: "OpenCV를 활용한 SIFT 사용  " 
date: 9999-12-31
author_profile: false
toc: true
toc_sticky: true
categories:
  - ML
tags:
  - DL
  - ML
---
  

# 0. 내용
 


SIFT에서 하나의 특징점에 대한 정보(설명자)는 128차원의 실수 벡터

SIFT(Scale-Invariant Feature Transform)은 특징점의 크기와 각도까지 같이 계산하여 이미지의 크기가 변하거나 회전해도 동일한 특징점을 찾을 수 있도록 하는 방법이다. 또한 특징점 근처의 이미지 특성(히스토그램)도 같이 계산해서 특징점 이미지의 모양도 구별할 수 있도록 한다.

먼저 크기에 불변한 특징점을 추출하기 위해서, 스케일 피라미드(Scale-Pyrimid)를 만든다. 스케일 피라미드란 이미지의 원본 이미지에서 2배, 1배, 1/2배, 1/4배 점차 줄인 이미지이다.
이렇게 만든 스케일 피라미드의 각 이미지에서 특징점을 찾는다. 이렇게 찿은 특징점은 스케일 불변(Scale-Invariant)이다. 하지만 이미지의 회전에는 불변이 아니다.
회전 불변 특성을 위해 특징점 주변의 그레디언트 방향과 크기를 수집한다. 특징점을 중심으로 윈도우를 설정하여 그 안의 픽셀에 대한 그레디언트의 크기와 방향을 구한다.
360도를 36등분하여 36개의 bin을 가진 그레디언트 벡터 히스토그램을 만든다. 가장 값이 큰 bin이 해당 특징점의 방향, 그 bin의 크기가 특징점의 크기가 된다.
다음 코드는 이미지에 대해 SIFT 특징을 찾고, 변환된 이미지에서 같은 특징점 끼리 매칭하는 작업을 수행한다.

#### kp1, des1 = self.sift.detectAndCompute(cv_image_input,None)   


#### self.flann.knnMatch(des1,self.des_construction,k=2)


 
#### FLANN :Fast Libarary for Approximate Nearest Neighbor

큰 이미지에서 특성들을 **매칭**할 때 성능을 위해 최적화 된 라이브러리모음  
**FLANN based Matche**
FLANN은 Approximate Nearest Neighbors의 Fast Library를 나타냅니다. 대규모 데이터 세트 및 고차원features에서 nearest neighbor search 을 위해 최적화 된 알고리즘 모음이 포함되어 있습니다. 대규모 데이터 세트의 경우 BFMatcher보다 더 빠르게 작동합니다. FLANN 기반 matcher로 두 번째 예제를 보게 될 것입니다.

FLANN 기반 매처의 경우 사용할 알고리즘, 관련 매개 변수 등을 지정하는 두 개의 사전을 전달해야합니다. 먼저 IndexParams입니다. 다양한 알고리즘에 대해 전달할 정보는 FLANN 문서에 설명되어 있습니다. 요약하면 SIFT, SURF 등과 같은 알고리즘의 경우 다음을 전달할 수 있습니다.
```
index_params = dict(algorithm = FLANN_INDEX_KDTREE, trees = 5)
ORB를 사용하는 동안 다음을 전달할 수 있습니다. 주석 값은 문서별로 권장되지만 경우에 따라 필요한 결과를 제공하지 않습니다. 다른 값은 잘 작동했습니다.

index_params= dict(algorithm = FLANN_INDEX_LSH,
                   table_number = 6, # 12
                   key_size = 12,     # 20
                   multi_probe_level = 1) #2     

```
두 번째 사전은 SearchParams입니다. 인덱스의 트리를 재귀 적으로 탐색해야하는 횟수를 지정합니다. 값이 높을수록 정확도가 높아지지만 시간이 더 많이 소요됩니다. 값을 변경하려면 search_params = dict (checks = 100)를 전달하십시오.

이러한 정보를 통해 이제 우리는 잘 할 수 있습니다.





``` python
FLANN_INDEX_KDTREE = 0 
index_params = dict(algorithm=FLANN_INDEX_KDTREE, tree=5)
search_params = dict(checks=50)

```

FLANN 기반 매칭을 위해 두개의 DICT이 필요함(index_params, search_params)
index_params = dict(algorithm=FLANN_INDEX_LSH, table_number=6, key_size=12, multi_probe_level=1)


searchParams는 특정매칭을 위한 반복회수(tradeoff 정확한결과값<->속도는 느려짐) ex :checks=100, check=50 등



``` python
flann = cv2.FlannBasedMatcher(index_params,search_params)
matches = flann.knnMatch(des1,des2,k=2)
```

FLANN 기반 매칭 객체를 앞에서 구성한 DICT자료형태의 인자를 이용해 생성, 추후 KNN 매칭을 수행 KNN매칭은 K=2 로 설정하였으므로 
matches는 (1순위매칭결과, 2순위매칭결과)가 멤버인 리스트가 됨


``` python
good=[]
for m,n in matches:
if m.distance >factor*n.distance:
good.append(m)
```


matches의 각 멤버에서 1순위 매칭결과가 2순위 매칭결과의 factor로 주어진 비율보다 더 가까운값만을 취함.
facotr의 값은 0.7이므로 1순위 매칭 결과가 2순위 ㅁ채ㅣㅇ결과의 0.7배보다 더 가까운 값만을 취함


 





====

# 관련 링크  

[FLANN ](https://leechamin.tistory.com/330)
   
[이미지의 특징점 매칭(Feature Matching)장단점 비교](http://www.gisdeveloper.co.kr/?p=6824)

[파라메터(index,search)](https://m.blog.naver.com/PostView.nhn?blogId=samsjang&logNo=220657746860&proxyReferer=https:%2F%2Fwww.google.com%2F)


[DS: 알고리즘비교](https://datascienceschool.net/view-notebook/7eb4b2a440824bb0a8c2c7ce3da7a4e2/)
``` python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

################################################################################
# Copyright 2018 ROBOTIS CO., LTD.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
################################################################################

# Author: Leon Jung, Gilbert

import rospy
import numpy as np
import math
import os
import cv2
from enum import Enum
from std_msgs.msg import UInt8
from sensor_msgs.msg import Image, CompressedImage
from cv_bridge import CvBridge, CvBridgeError

class DetectSign():
    def __init__(self):
        self.fnPreproc()

        self.sub_image_type = "raw" # you can choose image type "compressed", "raw"
        self.pub_image_type = "compressed" # you can choose image type "compressed", "raw"

        if self.sub_image_type == "compressed":
            # subscribes compressed image
            self.sub_image_original = rospy.Subscriber('/detect/image_input/compressed', CompressedImage, self.cbFindTrafficSign, queue_size = 1)
        elif self.sub_image_type == "raw":
            # subscribes raw image
            self.sub_image_original = rospy.Subscriber('/detect/image_input', Image, self.cbFindTrafficSign, queue_size = 1)

        self.pub_traffic_sign = rospy.Publisher('/detect/traffic_sign', UInt8, queue_size=1)

        if self.pub_image_type == "compressed":
            # publishes traffic sign image in compressed type 
            self.pub_image_traffic_sign = rospy.Publisher('/detect/image_output/compressed', CompressedImage, queue_size = 1)
        elif self.pub_image_type == "raw":
            # publishes traffic sign image in raw type
            self.pub_image_traffic_sign = rospy.Publisher('/detect/image_output', Image, queue_size = 1)

        self.cvBridge = CvBridge()

        self.TrafficSign = Enum('TrafficSign', 'divide stop parking tunnel left right no_entry construction')

        self.counter = 1

    def fnPreproc(self):
        # Initiate SIFT detector
        self.sift = cv2.xfeatures2d.SIFT_create()

        dir_path = os.path.dirname(os.path.realpath(__file__))
        dir_path = dir_path.replace('turtlebot3_autorace_construction_detect/nodes', 'turtlebot3_autorace_construction_detect/')
        dir_path += 'file/detect_sign/'

        self.img_construction  = cv2.imread(dir_path + 'construction.png',0)

        self.kp_construction, self.des_construction  = self.sift.detectAndCompute(self.img_construction, None)
      
        FLANN_INDEX_KDTREE = 0
        index_params = dict(algorithm = FLANN_INDEX_KDTREE, trees = 5)
        search_params = dict(checks = 50)

        self.flann = cv2.FlannBasedMatcher(index_params, search_params)

    def fnCalcMSE(self, arr1, arr2):
            squared_diff = (arr1 - arr2) ** 2
            sum = np.sum(squared_diff)
            num_all = arr1.shape[0] * arr1.shape[1] #cv_image_input and 2 should have same shape
            err = sum / num_all
            return err

    def cbFindTrafficSign(self, image_msg):
        # drop the frame to 1/5 (6fps) because of the processing speed. This is up to your computer's operating power.
        if self.counter % 3 != 0:
            self.counter += 1
            return
        else:
            self.counter = 1

        if self.sub_image_type == "compressed":
            #converting compressed image to opencv image
            np_arr = np.fromstring(image_msg.data, np.uint8)
            cv_image_input = cv2.imdecode(np_arr, cv2.IMREAD_COLOR)
        elif self.sub_image_type == "raw":
            cv_image_input = self.cvBridge.imgmsg_to_cv2(image_msg, "bgr8")

        MIN_MATCH_COUNT = 8 #9
        MIN_MATCH_COUNT_P = 15
        MIN_MSE_DECISION = 50000

        # find the keypoints and descriptors with SIFT
        kp1, des1 = self.sift.detectAndCompute(cv_image_input,None)

        matches_construction = self.flann.knnMatch(des1,self.des_construction,k=2)
      
        image_out_num = 1

        good_construction = []
        for m,n in matches_construction:
            if m.distance < 0.7*n.distance:
                good_construction.append(m)
        if len(good_construction)>MIN_MATCH_COUNT:
            src_pts = np.float32([kp1[m.queryIdx].pt for m in good_construction ]).reshape(-1,1,2)
            dst_pts = np.float32([self.kp_construction[m.trainIdx].pt for m in good_construction]).reshape(-1,1,2)

            M, mask = cv2.findHomography(src_pts, dst_pts, cv2.RANSAC,5.0)
            matches_construction = mask.ravel().tolist()

            mse = self.fnCalcMSE(src_pts, dst_pts)
            if mse < MIN_MSE_DECISION:
                msg_sign = UInt8()
                msg_sign.data = self.TrafficSign.construction.value

                self.pub_traffic_sign.publish(msg_sign)
                rospy.loginfo("construction")

                image_out_num = 9
        else:
            matches_construction = None
      
        if image_out_num == 1:
            if self.pub_image_type == "compressed":
                # publishes traffic sign image in compressed type
                self.pub_image_traffic_sign.publish(self.cvBridge.cv2_to_compressed_imgmsg(cv_image_input, "jpg"))

            elif self.pub_image_type == "raw":
                # publishes traffic sign image in raw type
                self.pub_image_traffic_sign.publish(self.cvBridge.cv2_to_imgmsg(cv_image_input, "bgr8"))

            elif image_out_num == 2:
                draw_params_construction = dict(matchColor = (255,0,0), # draw matches in green color
                            singlePointColor = None,
                            matchesMask = matches_construction, # draw only inliers
                            flags = 2)

                final_construction = cv2.drawMatches(cv_image_input,kp1,self.img_construction,self.kp_construction,good_construction,None,**draw_params_construction)

                if self.pub_image_type == "compressed":
                    # publishes traffic sign image in compressed type
                    self.pub_image_traffic_sign.publish(self.cvBridge.cv2_to_compressed_imgmsg(final_construction, "jpg"))
detectAndCompute
                elif self.pub_image_type == "raw":
                    # publishes traffic sign image in raw type
                    self.pub_image_traffic_sign.publish(self.cvBridge.cv2_to_imgmsg(final_construction, "bgr8"))

    def main(self):
        rospy.spin()

if __name__ == '__main__':
    rospy.init_node('detect_sign')
    node = DetectSign()
    node.main()




```

----


A notice displays information that explains nearby content. Often used to call attention to a particular detail.

When using Kramdown `{: .notice}` can be added after a sentence to assign the `.notice` to the `<p></p>` element. 

**Changes in Service:** We just updated our [privacy policy](#) here to better service our customers. We recommend reviewing the changes.
{: .notice}

**Primary Notice:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. [Praesent libero](#). Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--primary}

<div class="notice--primary" markdown="1">
**Primary Notice with code block:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. [Praesent libero](#). Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.

```html
<html>
  <body>Some body.<body>
</html>
```
</div>

**Info Notice:** Lorem ipsum dolor sit amet, [consectetur adipiscing elit](#). Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--info}

**Warning Notice:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. [Integer nec odio](#). Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--warning}

**Danger Notice:** Lorem ipsum dolor sit amet, [consectetur adipiscing](#) elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--danger}

**Success Notice:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at [nibh elementum](#) imperdiet.
{: .notice--success}

Want to wrap several paragraphs or other elements in a notice? Using Liquid to capture the content and then filter it with `markdownify` is a good way to go.

```html
{% raw %}{% capture notice-2 %}
#### New Site Features

* You can now have cover images on blog pages
* Drafts will now auto-save while writing
{% endcapture %}{% endraw %}

<div class="notice">{% raw %}{{ notice-2 | markdownify }}{% endraw %}</div>
```

{% capture notice-2 %}
#### New Site Features

* You can now have cover images on blog pages
* Drafts will now auto-save while writing
{% endcapture %}

<div class="notice">
  {{ notice-2 | markdownify }}
</div>

Or you could skip the capture and stick with straight HTML.

```html
<div class="notice">
  <h4>Message</h4>
  <p>A basic message.</p>
</div>
```

<div class="notice">
  <h4>Message</h4>
  <p>A basic message.</p>
</div>

/home/wia/download/hotsh8t.github.io/_posts/3.DS/2020-05-12-Social Network Analysis.md
This post lives in the future and is dated {{ page.date | date: "%c" }}. When building Jekyll with the `--future` flag it should appear.
