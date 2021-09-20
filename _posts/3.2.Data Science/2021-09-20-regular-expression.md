---
title: "[Regular Expression] 파이썬 정규식 정리"
#date: 2020-5-1
categories:
  - DS
tags:
  - Python
  - DS
  - RegularExpression
---

# Regular Expression(RegEx)

 텍스트데이터를 다루기 위해서는 반드시 해야함. 특히 비정형데이터를 다루고 머신러닝하기 위해서는 필수 요소임

참고 [https://regexr.com/](https://regexr.com/)




### Special characters

- .(dot) : matches any character
- \w : word character
- \s : empty space
- \+ : resulting RE to match 1 or more repetitions
- \* : resulting RE to match 0 or more repetitions
- ^(caret) : beginning of string
- $(dollar) : end of string

- [] : set of characters
abc중 한 글자를 매칭, 즉 이루어진 한 단어, [abc]+ abc가 들어간 단어 
- () : indicates a group 
- | : A|B indicates A or B
