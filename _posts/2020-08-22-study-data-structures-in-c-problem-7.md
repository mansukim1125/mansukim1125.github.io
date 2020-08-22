---
title: 자료구조 스터디_문제 7_집합
tags: Study Data-Structures Set
---

## 출처

> 11723, 집합, baekjoon, [Baekjoon Online Judge](https://www.acmicpc.net/)



## 문제

비어있는 공집합 S가 주어졌을 때, 아래 연산을 수행하는 프로그램을 작성하시오.

- `add x`: ![S](https://latex.codecogs.com/svg.latex?S)에 ![x](https://latex.codecogs.com/svg.latex?x)를 추가한다. (1 ≤ ![x](https://latex.codecogs.com/svg.latex?x) ≤ 20) S에 ![x](https://latex.codecogs.com/svg.latex?x)가 이미 있는 경우에는 연산을 무시한다.
- `remove x`: ![S](https://latex.codecogs.com/svg.latex?S)에서 ![x](https://latex.codecogs.com/svg.latex?x)를 제거한다. (1 ≤ ![x](https://latex.codecogs.com/svg.latex?x) ≤ 20) S에 ![x](https://latex.codecogs.com/svg.latex?x)가 없는 경우에는 연산을 무시한다.
- `check x`: ![S](https://latex.codecogs.com/svg.latex?S)에 ![x](https://latex.codecogs.com/svg.latex?x)가 있으면 1을, 없으면 0을 출력한다. (1 ≤ ![x](https://latex.codecogs.com/svg.latex?x) ≤ 20)
- `toggle x`: ![S](https://latex.codecogs.com/svg.latex?S)에 ![x](https://latex.codecogs.com/svg.latex?x)가 있으면 ![x](https://latex.codecogs.com/svg.latex?x)를 제거하고, 없으면 ![x](https://latex.codecogs.com/svg.latex?x)를 추가한다. (1 ≤ ![x](https://latex.codecogs.com/svg.latex?x) ≤ 20)
- `all`: ![S](https://latex.codecogs.com/svg.latex?S)를 ![set](https://latex.codecogs.com/svg.latex?%5Cleft%20%5C%7B%201%2C%202%2C%20...%2C%2020%20%5Cright%20%5C%7D) 으로 바꾼다.
- `empty`: ![S](https://latex.codecogs.com/svg.latex?S)를 공집합으로 바꾼다. 

## 입력

첫째 줄에 수행해야 하는 연산의 수 ![M](https://latex.codecogs.com/svg.latex?M) (1 ≤ ![M](https://latex.codecogs.com/svg.latex?M) ≤ 3,000,000)이 주어진다.

둘째 줄부터 ![M](https://latex.codecogs.com/svg.latex?M)개의 줄에 수행해야 하는 연산이 한 줄에 하나씩 주어진다.

## 출력

`check` 연산이 주어질때마다, 결과를 출력한다.

## 예제 입력 1

```
26
add 1
add 2
check 1
check 2
check 3
remove 2
check 1
check 2
toggle 3
check 1
check 2
check 3
check 4
all
check 10
check 20
toggle 10
remove 20
check 10
check 20
empty
check 1
toggle 1
check 1
toggle 1
check 1
```

## 예제 출력 1

```
1
1
0
1
0
1
0
1
0
1
1
0
0
0
1
0
```

