---
title: "[flutter&dart] 버튼 누를때마다 문자 크기 커지는 앱 "

categories:
  - flutter&dart
tags:
  - AppPractice

date: 2021-02-25 16:00:00
---

# 1. 버튼 누를때마다 문자 크기 커지는 앱
![ezgif com-video-to-gif](https://user-images.githubusercontent.com/20227720/109119525-28480c00-7788-11eb-840b-dc789caf5d61.gif)

# 1-1. main.dart

```dart
import 'package:flutter/material.dart';

import './MyButton.dart';
import './MyText.dart';

void main() => runApp(MyApp());

class MyApp extends StatefulWidget {
  @override
  _MyAppState createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  double _textSize = 10;

  void _setSize(double size) {
    setState(() {
      _textSize = size;
    });
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('The Challenge'),
          backgroundColor: Colors.redAccent,
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              MyText(_textSize),
              MyButton(_textSize, _setSize),
            ],
          ),
        ),
      ),
    );
  }
}

```

# 1-2. MyText.dart

```dart
import 'package:flutter/material.dart';

class MyText extends StatelessWidget {
  double textSize = 1;

  MyText(this.textSize);

  @override
  Widget build(BuildContext context) {
    return Text(
      'HI',
      style: TextStyle(
        color: Colors.red,
        fontSize: textSize,
      ),
    );
  }
}

```

# 1-3. MyButton.dart

```dart
import 'package:flutter/material.dart';

class MyButton extends StatelessWidget {
  double textSize;
  Function setSize;

  MyButton(this.textSize, this.setSize);

  @override
  Widget build(BuildContext context) {
    return Row(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        ElevatedButton(
          style: ElevatedButton.styleFrom(
            primary: Colors.red,
            onPrimary: Colors.white,
          ),
          child: Text(
            'Plus',
            style: TextStyle(fontSize: 20),
          ),
          onPressed: () {
            textSize += 5;
            setSize(textSize);
            print(textSize);
          },
        ),
        ElevatedButton(
          style: ElevatedButton.styleFrom(
            primary: Colors.blue,
            onPrimary: Colors.white,
          ),
          child: Text(
            'Minus',
            style: TextStyle(fontSize: 20),
          ),
          onPressed: () {
            if (textSize >= 10) {
              textSize -= 5;
              setSize(textSize);
            }
            print(textSize);
          },
        ),
      ],
    );
  }
}

```
