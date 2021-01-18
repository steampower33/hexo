---
title: "[algorithm] 유니온 파인드"
excerpt: "[algorithm] 유니온 파인드"

categories:
  - algorithm
tags:
  - Python
  - UnionFind
date: 2020-02-05 21:30:00
---

## 0. 출처
- 이 게시글은 [동빈 나 블로그](https://m.blog.naver.com/PostView.nhn?blogId=ndb796&logNo=221230967614&referrerCode=0&searchKeyword=실전%20알고리즘%20강좌(Algorithm%20Programming%20Tutorial)%20%2318)를 참조했습니다.

## 1. 유니온 파인드
- 여러 노드가 존재할때 두개의 노드를 선택해서, 서로 연결되어있는지 확인하는 알고리즘

## 2. 구현
- 아래 코드의 주석만 읽어도 이해가 될것이다.

```python
# 부모 노드 가져오기.
def getParent(parent, x):
    # 위치와 값이 같다? => 부모노드.
    if parent[x] == x: return x
    # 계속해서 거슬러 올라간다.
    parent[x] = getParent(parent, parent[x])
    return parent[x]

# 각 부모노드 합치기.
def unionParent(parent, a, b):
    # 부모노드를 찾고.
    a = getParent(parent, a)
    b = getParent(parent, b)
    # 그 작은쪽이 부모노드가 됨.
    if a < b: parent[b] = a
    else: parent[a] = b

# 같은 부모인지 확인.
def findParent(parent, a, b):
    # 부모노드를 찾고.
    a = getParent(parent, a)
    b = getParent(parent, b)
    # 둘다 같으면 같은 집합.
    if a == b: return True
    else: return False

if __name__ == "__main__":
    parent = [0 for i in range(11)]
    for i in range(1, 11):
        parent[i] = i

    unionParent(parent, 1, 2)
    unionParent(parent, 2, 3)
    unionParent(parent, 3, 4)
    unionParent(parent, 5, 6)
    unionParent(parent, 6, 7)
    unionParent(parent, 7, 8)

    print("1과 5는 연결되어있나요? ", findParent(parent, 1, 5))
    unionParent(parent, 1, 5)
    print("1과 5는 연결되어있나요? ", findParent(parent, 1, 5))
```

## 3. 리뷰
- 참고한 동빈나 님 이분은 설명은 참 잘하신다.