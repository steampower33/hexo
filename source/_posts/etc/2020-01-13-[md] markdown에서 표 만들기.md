---
title:  "[md] markdown에서 표 만들기"

categories:
  - md
tags:
  - MarkDown
  - HowTo

date: 2020-01-13 17:30:00
---

## 1. 예시

```
| 이름 | 2019 부자 순위 |
| :------: | :---------------------------------------------------------- |
| 제프 베조스 | 1위 (1310억 달러) |
| 빌 게이츠 | 2위 ( 965억 달러) |
| 워런 버핏 버크셔 | 3위 ( 825억 달러) |
| 베르나르 아르노 | 4위 ( 760억 달러) |
| e카를로스 슬림 | 5위 ( 640억 달러) |
```

| 이름 | 2019 부자 순위 |
| :------: | :---------------------------------------------------------- |
| 제프 베조스 | 1위 (1310억 달러) |
| 빌 게이츠 | 2위 ( 965억 달러) |
| 워런 버핏 버크셔 | 3위 ( 825억 달러) |
| 베르나르 아르노 | 4위 ( 760억 달러) |
| e카를로스 슬림 | 5위 ( 640억 달러) |

## 2. 간단하게.

```
| 왼쪽 정렬 | 가운데 정렬 | 오른쪽 정렬|
| 왼 | 가 | 오 |
```

| 왼쪽 정렬 | 가운데 정렬 | 오른쪽 정렬|
| :------ | :------: | ------: |
| 왼 | 가 | 오 |

## 3. 빠르고, 간편하게 만들기.

테이블 생성기 사이트 : [TablesGenerator](https://www.tablesgenerator.com/markdown_tables#).

<img width="1295" alt="스크린샷 2020-01-13 오후 5 42 58" src="https://user-images.githubusercontent.com/20227720/72242216-32fb1c80-362c-11ea-8fe0-e4147c84a618.png">

사이트를 들어가서, Edit, Table, Column, Row 를 클릭, 수정한 다음  
밑에 <strong>Generate</strong>를 누르면, <strong>Result</strong>에 코드가 생성된다.  