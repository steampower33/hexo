---
title: "[algorithm] 선형 알고리즘"

categories:
  - algorithm
tags:
  - c++
  - LinearTime

date: 2020-02-14 15:50:00
---

## 1. 주어진 배열에서 가장 많이 등장하는 숫자 반환하기

```c++
#include <iostream>
#include <vector>
#include <time.h>
#include <cstdlib>
#include <ctime>

using namespace std;
// 주어진 배열A에서 가장 많이 등장하는 숫자를 반환한다.
// 만약 두 가지 이상 있을 경우 아무것이나 반환한다.

// O(N^2)
int majority1(const vector<int>& A){
    int N = A.size();
    int majority = -1, majorityCount = 0;
    for(int i = 0; i < N; ++i){
        //A에 등장하는 A[i]의 수를 센다.
        int V = A[i], count = 0;
        for(int j = 0; j < N; ++j){
            if(A[j] == V){
                ++count;
            }
        }
        //지금까지 본 최대 빈도보다 많이 출현했다면 답을 갱신한다.
        if(count > majorityCount){
            majorityCount = count;
            majority = V;
        }
    }
    return majority;
}

// O(N)
int majority2(const vector<int>& A){
    int N = A.size();
    vector<int> count(101, 0);
    for(int i = 0; i < N; ++i){
        count[A[i]]++;
    }
    //지금까지 확인한 숫자 중 빈도수가 제일 큰 것을 majority에 저장한다.
    int majority = 0;
    for(int i = 1; i <=100; ++i){
        if(count[i] > count[majority]){
            majority = i;
        }
    }
    return majority;
}

int main(){
    clock_t start, end;
    vector<int> v;
    int result1 = 0;
    int result2 = 0;

    srand((unsigned int)time(NULL));
    for(int i = 0; i < 100; i++){
        v.push_back((rand() % 100) + 1);
    }

    start = clock();
    result1 = majority1(v);
    end = clock();
    cout << (double)(end - start) << endl;

    start = clock();
    result2 = majority2(v);
    end = clock();
    cout << (double)(end - start) << endl;

    return 0;
}
```

## 1-1. 결과
<img width="618" alt="스크린샷 2020-02-14 오후 5 26 56" src="https://user-images.githubusercontent.com/20227720/74514096-46611680-4f4f-11ea-8987-aa349682b074.png">


## 2. 이동 평균

```c++
#include <iostream>
#include <vector>
#include <time.h>

using namespace std;

// O(N^2)
//실수 배열 A가 주어질때, 각 위치에서의 M-이동 평균 값을 구한다.
vector<double> movingAverage1(const vector<double>& A, int M){
    vector<double> ret;
    int N = A.size();
    for(int i = M-1; i < N; ++i){
        //A[i]까지의 이동 평균 값을 구하자.
        double partialSum = 0;
        for(int j = 0; j < M; ++j)
            partialSum += A[i-j];
        ret.push_back(partialSum / M);
    }
    return ret;
}

// O(N)
// 길이가 N인 실수 배열 A가 주어질 때, 각 위치에서의 M-이동 평균 값을 구한다.
vector<double> movingAverage2(const vector<double>& A, int M){
    vector<double> ret;
    int N = A.size();
    double partialSum = 0;
    for(int i = 0; i < M-1; ++i)
        partialSum += A[i];
    for(int i = M-1; i < N; ++i){
        partialSum += A[i];
        ret.push_back(partialSum / M);
        partialSum -= A[i-M+1];
    }
    return ret;
}

int main(){
    clock_t start, end;
    vector<double> value;
    for(int i = 0; i < 100; ++i){
        int in = i*2 + 3;
        value.push_back(in);
    }
    start = clock();
    vector<double> ret1 = movingAverage1(value, 50);
    end = clock();
    cout << (double)(end - start) << endl;
    
    start = clock();
    vector<double> ret2 = movingAverage2(value, 50);
    end = clock();
    cout << (double)(end - start) << endl;
    return 0;
} 
```

## 2-2. 결과

<img width="666" alt="스크린샷 2020-02-14 오후 5 27 05" src="https://user-images.githubusercontent.com/20227720/74514092-43febc80-4f4f-11ea-9140-c4a24210e93b.png">