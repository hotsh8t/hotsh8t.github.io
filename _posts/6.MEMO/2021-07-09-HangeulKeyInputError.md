---
title: "VSCODE HOTKEYS"
categories:
  - MEMO
tags:
  - content
  - css
  - edge case fff DD Ddddg
  - lists
  - markup
---

Nested and mixed lists are an interesting beast. It's a corner case to make sure that
## CS코드 주요 단축키
* UBUNTU에는 snap형식의 설치파일과 deb 형식의 설치파일이 존재함
* SNAP 형식파일은 UBUNTU의 입력기인 IBus와 충돌한다고 함
* 따라서 vscode를 지우고 직접 deb 형식의 설치파일을 받아 다시 설치

'''
$ sudo snap remove code

$ sudo dpkg -i code_1.58.0-1625728071_amd64.deb





'''

### Ordered -- Unordered -- Ordered

1. ordered item
2. ordered item 
   * **unordered**
   * **unordered** 
     1. ordered item
     2. ordered item
3. ordered item
4. ordered item

### Ordered -- Unordered -- Unordered

1. ordered item
2. ordered item 
   * **unordered**
   * **unordered** 
     * unordered item
     * unordered item
3. ordered item
4. ordered item

### Unordered -- Ordered -- Unordered

* unordered item
* unordered item 
  1. ordered
  2. ordered 
     * unordered item
     * unordered item
* unordered item
* unordered item

### Unordered -- Unordered -- Ordered

* unordered item
* unordered item 
  * unordered
  * unordered 
    1. **ordered item**
    2. **ordered item**
* unordered item
* unordered item

### Task Lists

- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request
