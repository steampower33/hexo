---
title: "[python] pyinstaller로 exe 실행 파일 만들기, 에러 해결"

categories:
  - python
tags:
  - HowTo
  - Python
  - pyinstaller
  - MakeRunFile
  - SolveError
  - PyToExe

date: 2020-01-25 03:00:00
---

## 0. 환경
- 오류가 발생하면, 목차의 [end. 문제발생] 으로 넘어가주세요.

|:--------:|:--------:|
| 개발 OS | 윈도우 |
| python | 3.8 |

## 1. pyinstaller 설치

```
pip install pyinstaller
```

## 2. python 모듈 체크
- 예시 파일이며, import 혹은 from 되어있는 모듈, 패키지가 pip에 설치되어있지않다면, 나중에 실행파일을 생성해도 정상적으로 작동하지않습니다.
- 그러니 import 혹은 from 되어있는 모듈, 패키지가 pip에 설치되어있지않다면, 아래와 같이 모두 설치해주시기 바랍니다.
```
pip install "모듈, 패키지 이름"
```
<img width="339" alt="스크린샷 2020-01-25 오전 3 19 47" src="https://user-images.githubusercontent.com/20227720/73094291-a56cd600-3f23-11ea-928c-3511bc0031e4.png">
<img width="281" alt="스크린샷 2020-01-25 오전 3 20 07" src="https://user-images.githubusercontent.com/20227720/73094292-a56cd600-3f23-11ea-8ffb-c3b948871668.png">

## 3. 실행 파일 생성하기
- 파일 생성 기본 명령어는 아래와 같습니다.  
- 해당 파일이름.py 가 있는 디렉토리로 가서 실행합니다.

```
pyinstaller 파일이름.py
```

- 이번에는 아래와 같이 네이밍 할수있는 옵션을 사용합니다.
- 옵션에 대해서 더 알고싶으시다면, [이곳](https://pyinstaller.readthedocs.io/en/stable/usage.html)을 참고하세요.

<img width="330" alt="스크린샷 2020-01-25 오전 3 21 45" src="https://user-images.githubusercontent.com/20227720/73094293-a56cd600-3f23-11ea-90bd-f2f5260c3375.png">

- 해당 디렉토리로 가면 뭐가 많이 생겨있습니다.

<img width="719" alt="스크린샷 2020-01-25 오전 3 21 53" src="https://user-images.githubusercontent.com/20227720/73094294-a6056c80-3f23-11ea-9f15-ba6ad52b8706.png">

- dist 디렉토리로 가면 네이밍한 exe파일이 있습니다.

<img width="756" alt="스크린샷 2020-01-25 오전 3 22 20" src="https://user-images.githubusercontent.com/20227720/73094297-a6056c80-3f23-11ea-9bc3-4f3e92b6d27c.png">


## end. 문제발생

### pip 버전을 최대로 upgrade
```
python -m pip install --upgrade pip
```

### wheel 설치
- wheel이 없어서 오류가 나는 경우도 간혹 존재합니다.
- pip list 명령어로 list에 wheel의 유무를 체크하십시오.

```
pip install wheel
```

### [중 요] 모듈, 패키지
- pip에는 *.py 에서 사용하는 모듈, 패키지가 설치되어있어야합니다.
- 그리고 그 모듈과 패키지는 현재 파이썬 버전과 호환되어야합니다.