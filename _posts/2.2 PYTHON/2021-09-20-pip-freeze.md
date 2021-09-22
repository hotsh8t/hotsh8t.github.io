---
title: "[pip freeze]환경변수 및 패스워드 관리"
date: 2021-9-20
author_profile: true 
sidebar:
  nav: "main_sidebar"
toc: true
toc_sticky: true
categories:
  - PYTHON
---

# 파이선 환경설정
현재 가상환경에서 쓰고 있는 파이썬 라이브러리 목록을 확인

# pip freeze    

- pip freeze 사용 법
```  
pip freeze > requirements.txt
``` 

- 배포 시   
```  
 pip install -r requirements.txt
```

# .env 파일로 환경변수 설정
- 계정 정보를 python 소스코드에 그대로 넣으면 보안 문제가 생김
  - 보안사고 예 : Github public repository 를 검색해서 AWS access key 탈취, GPU많이 달린 서버를 렌트한 뒤 비트코인 채굴 등
- 보안이 필요한 정보는 **.env**로 관리할 수 있다. 