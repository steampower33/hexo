---
title: "[flutter&dart] final과 const "

categories:
  - flutter&dart
tags:
  - final & const

date: 2021-02-22 12:00:00
---

# 1. 컴파일 타임, 런타임

```
컴파일 타임 : 컴파일 과정을 통해 소스코드를 컴퓨터가 인식할 수 있는 기계어 코드로 변환해서 "실행 가능"한 프로그램이 되는 과정을 의미하는데,
소스코드에 이상이 없는지 판단하는 과정이다.

런타임 : 컴파일 이후 프로그램이 실행되는 타임

컴파일 -> 런 순서
```

# 2. final과 const

# 2-1. 상수

final과 const 둘 다 한번 설정하면 변경할 수 없다.

const는 컴파일 타임에서 상수 정의 가능 -> const로 정의된 상수는 런타임에서 설정 불가능
즉 절대 바뀌지않아야하는 상수라면 const를 사용한다.

final은 런타임에서 결정되는 값도 설정가능하다.

```dart
final DateTime now = DateTime.now(); // DateTime.now()의 값이 런타임에서 결정되어도, final은 문제가 없다.

//const DateTime now = DateTime.now(); // 런타임 시에 값이 결정나기때문에 const는 사용 불가능.
```

# 2-2. 배열

```dart
final hello = ['Hello']; // 가능
const hi = ['hi']; // 가능

hello.add('Bye') // 가능
hi.add('See ya') // 불가능

hello.removeAt(0); // 가능

hello = ['What']; // 불가능
hi = ['What']; // 불가능
```

const와 final 둘다 아예 다른 배열로 바꾸는 것은 불가능하다.

const의 경우 추가, 삭제 불가능. 아예 원본을 유지해야한다.
final은 추가, 삭제가 가능하다.