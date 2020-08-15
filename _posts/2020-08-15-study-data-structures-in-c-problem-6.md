---
title: 자료구조 스터디_문제 6_좌표 정렬하기
tags: Study Data-Structures Sort
---

## 출처

> 11650, 좌표 정렬하기, baekjoon, [Baekjoon Online Judge](https://www.acmicpc.net/)

## 문제

2차원 평면 위의 점 ![n](https://latex.codecogs.com/svg.latex?N)개가 주어진다. 좌표를 ![x](https://latex.codecogs.com/svg.latex?x)좌표가 증가하는 순으로, ![x](https://latex.codecogs.com/svg.latex?x)좌표가 같으면 ![y](https://latex.codecogs.com/svg.latex?y)좌표가 증가하는 순서로 정렬한 다음 출력하는 프로그램을 작성하시오.

## 입력

첫째 줄에 점의 개수 ![n](https://latex.codecogs.com/svg.latex?N) (1 ≤ ![n](https://latex.codecogs.com/svg.latex?N) ≤ 100,000)이 주어진다. 둘째 줄부터 N개의 줄에는 i번점의 위치 ![x sub i](https://latex.codecogs.com/svg.latex?x_{i})와 ![y sub i](https://latex.codecogs.com/svg.latex?y_{i})가 주어진다. (-100,000 ≤ ![x sub i](https://latex.codecogs.com/svg.latex?x_{i}), ![y sub i](https://latex.codecogs.com/svg.latex?y_{i}) ≤ 100,000) 좌표는 항상 정수이고, 위치가 같은 두 점은 없다.

## 출력

첫째 줄부터 ![n](https://latex.codecogs.com/svg.latex?N)개의 줄에 점을 정렬한 결과를 출력한다.

## 예제 입력 1

```
5
3 4
1 1
1 -1
2 2
3 3
```

## 예제 출력 1

```
1 -1
1 1
2 2
3 3
3 4
```

