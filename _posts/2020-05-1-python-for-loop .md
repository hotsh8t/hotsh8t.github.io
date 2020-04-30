---
title: "python:for LOOP 완벽정리 "
date: 2020-531
categories:
  - Python
---

#python for 문 정리 
우선, Python에서 for loop를 돌릴 수 있는 자료형은 int, float 등 단일 변수에 대해서는 당연히 가능하나 
list, tuple, dict,, series 등에 대해서는 헷갈려 정리 하였다. 
1. 숫자형
2. 문자열
3. 리스트
4. 튜플
5. 딕셔너리
6. 집합자료형
7. 불 자료형

Python에서 존재하는 총 변수들은 위 7개이며 각 자료형을 선언하고 for i in 자료형 을 한 후 print(i)로 찍어보겠다. 

'''python

import networkx as nx
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
'''

'''python
list_int =[5, 4, 3, 2, 1]
list_char = ['다섯', '넷', '셋', '둘', '하나']
tuple = (

'''
This post lives in the future and is dated {{ page.date | date: "%c" }}. When building Jekyll with the `--future` flag it should appear.
