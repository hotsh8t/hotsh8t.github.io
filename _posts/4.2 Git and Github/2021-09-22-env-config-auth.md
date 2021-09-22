---
title: "[env]git commit 시 비밀번호 관리하기"
categories:
  - GIT
tags:
  - content
  - css
  - edge case
  - lists
  - markup
---
---
# GIT commit 시 비밀번호 관리하기
- git repository를 public으로 관리하는 경우 비밀번호가 공개될 위험이 있다. 이러한 경우 어떻게 해결할 수 있는지 확인해보자. 

- os.getenv를 통해 변수 접근하는 방법 설명

# dotenv 설치
- pip install python-dotenv 설치

# .env를 만들고 from dotenv import load_dotenv로 함