---
title:  "[flutter&dart] map 메소드"

categories:
  - flutter&dart
tags:
  - map method

date: 2021-02-18 12:00:00
---

# 1. map 메소드

문제에 해당하는 답 버튼을 나타내려고할때, 반복 가능한 집단내에서 map method를 사용하여 요소수만큼 리턴한다.

```dart
var questions = [
    {
      'questionText': 'What\'s your favorite color?',
      'answers': ['Black', 'Red', 'Green', 'White'],
    },
    {
      'questionText': 'What\'s your favorite animal?',
      'answers': ['Cow', 'Rabbit', 'Dog', 'Lion'],
    },
    {
      'questionText': 'what\'s your favorite Game?',
      'answers': ['LOL', 'FIFA', 'OVERWATCH', 'MAPLESTORY'],
    },
  ];
```

위의 자료형에 접근하려고한다.

```dart
...(questions[_questionIndex]['answers'] as List<String>)
                .map((answer) {
              return Answer(_answerQuestion, answer);
            }).toList()
```

```
questions[_questionIndex]['answers']은 List<String>인데, dart에서 인식하지 못해서 () 감싸준다음 as LIst<String>으로 dart에게 알려줄 수 있다.
그리고 List<String>은 iterable 하기에 map method 사용할수있다.
반복가능한 집단에서 map method 사용 가능

(answer) {return Answer(_answerQuestion, answer);} 에서 answer는 .map()의 인자이고, 그 인자를 넣은 Answer함수를 반환한다는 뜻

() {} 에서 () 안에 익명함수를 사용 {} 안에는 리턴할 함수를 사용한다.
익명 함수를 사용하는 이유는 여기에만 해당 함수가 필요하고 다른 곳에서는 필요하지 않기 때문이다.

map method 안에서 여기서 만들 수 있는 명명 된 함수를 사용할 수 있다.
여기에서 함수를 정의하고 그 함수는 자동으로 인수 자체를 받는다.

.toList()는 List안에 List가 들어가는 경우 안에 있는 List를 해제한다.

맨앞의 ...은 spread operator인데, 현재 이 구문 밖은 List로 감싸져있다.
List 안의 List이기에 spread operator를 통해서 그 밖의 List의 값이 되도록 해준다.
```