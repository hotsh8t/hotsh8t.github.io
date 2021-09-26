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
- Regular Expression 을 사용하는 경우 항상 테스트가 필요함
- 정규 표현식을 잘못 사용하면 돌이킬 수 없는 문제들이 발생 할 수 있음. 
- 정규 표현식 테스트 사이트들

* javascript 기준으로
- 참고 [https://regexr.com/](https://regexr.com/)


* python 기준으로
- 제가 구글링 해 본 바로는 Python 정규표현식 테스트 사이트로 아래 3개의 사이트가 나오더군요.

[https://regex101.com/](https://regex101.com/)

나머지 두 사이트는 파이썬 정규 표현식을 테스트만 할 수 있음

[http://pythex.org/](http://pythex.org/)

[http://www.pyregex.com/](http://www.pyregex.com/)


Cheat Sheet 가 있어서 정규표현식 문법이 생각 안날 때 참조가능 

그런데 첫번째 링크인  https://regex101.com/ 의 경우 테스트 뿐만 아니라 코드 생성도 해 주더군요. 

모든 워드에 _postfix 라는 글자를 넣고 싶은 경우
다음과 같이 정규 표현식을 입력해서 테스트 해보면 모든 워드에 _postfix 를 넣을 수 있습니다.

\w+



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
