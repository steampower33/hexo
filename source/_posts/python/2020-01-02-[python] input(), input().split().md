---
title: "[python] 파이썬 input() 과 input().split()"

categories:
  - python
tags:
  - Infomation

date: 2020-01-06 17:53:00
---

# input()

### Code
```python
InputNum = input()
InputStr = input()

print(InputNum, InputStr)
```

### 인풋값 넣기.
```
1
Billionaire
```

### 출력값
```
1 Billionaire
```

# input().split()

### Code
```python
a, b = input().split()
c = input().split()
d = input()

print(a, b)
print(c[0], c[1])
print(d[0], d[1], d[2])
```

### 인풋값 넣기.
```
10 20
a b c d
e f g h
```

### 출력값
```
10 20
a b
e f
```
input()으로 문자열을 받으면, 공백까지 포함해서 받게된다.
input().split()의 경우, 공백은 무시하고, 문자만 입력받게된다.
