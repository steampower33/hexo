---
title: "flutter widget 사용 예시"

categories: 
- flutter
tags: 
- flutter_widget.zip

date: 2021-02-17 12:50:00
---

# 1. ElevatedButton

```dart
ElevatedButton(child: Text('Answer 1'), onPressed: () => print('Answer 1 chosen!')),
ElevatedButton(
    child: Text('Answer 1'), 
    onPressed: () {
        print('Answer 1 chosen!'),
    },
),
```

