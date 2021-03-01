---
title: "[flutter&dart] card 예제 "

categories:
  - flutter&dart
tags:
  - card

date: 2021-03-01 12:00:00
---

# 1. 예제

크기는 부모 위젯의 것을 가지는 듯.

```dart
/// Flutter code sample for Card

// This sample shows creation of a [Card] widget that can be tapped. When
// tapped this [Card]'s [InkWell] displays an "ink splash" that fills the
// entire card.

import 'package:flutter/material.dart';

void main() => runApp(MyApp());

/// This is the main application widget.
class MyApp extends StatelessWidget {
  static const String _title = 'Flutter Code Sample';

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: _title,
      home: Scaffold(
        appBar: AppBar(title: const Text(_title)),
        body: MyStatelessWidget(),
      ),
    );
  }
}

/// This is the stateless widget that the main application instantiates.
class MyStatelessWidget extends StatelessWidget {
  MyStatelessWidget({Key key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Row(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        SizedBox(
          width: 300,
          height: 210,
          child: Card(
            child: Column(
              children: [
                ListTile(
                  title: Text('Papunica',
                      style: TextStyle(fontWeight: FontWeight.w500)),
                  subtitle: Text('My City, Nia village'),
                  leading: Icon(
                    Icons.restaurant_menu,
                    color: Colors.blue[500],
                  ),
                ),
                Divider(),
                ListTile(
                  title: Text('010-1234-5678',
                      style: TextStyle(fontWeight: FontWeight.w500)),
                  leading: Icon(
                    Icons.contact_phone,
                    color: Colors.blue[500],
                  ),
                ),
                ListTile(
                  title: Text('ark@naver.com'),
                  leading: Icon(
                    Icons.contact_mail,
                    color: Colors.blue[500],
                  ),
                ),
              ],
            ),
          ),
        ),
      ],
    );
  }
}

```

# 2. 결과 

<img width="307" alt="스크린샷 2021-03-01 오후 5 37 02" src="https://user-images.githubusercontent.com/20227720/109471887-c43d8480-7ab4-11eb-97a7-631b4e642e04.png">
