---
title: 자료구조 스터디_문제 2_2차원 배열에서 검색하기
tags: Study Data-Structures Binary-Search
---

# 문제

![m times n](https://latex.codecogs.com/svg.latex?m\times%20n)배열에서 특정한 값 ![key](https://latex.codecogs.com/svg.latex?key)의 존재 여부를 반환하는 함수 `searchMatrix`함수를 작성하세요.

배열은 다음과 같이 정렬되어 있습니다:

1. 한 행(left to right)의 숫자들은 오름차순으로 정렬되어 있습니다.
2. 한 열(top to bottom)의 숫자들은 오름차순으로 정렬되어 있습니다.

## 입력

위의 2가지 정렬 규칙을 만족하는 2차원 배열과 찾고자 하는 값 ![key](https://latex.codecogs.com/svg.latex?key).

## 출력

값 ![key](https://latex.codecogs.com/svg.latex?key)의 존재 여부를 나타내는 Boolean 값.

# 입출력 예시

## 입력 1

### 배열

```c
{
    {1, 4, 7, 11, 15},
    {2, 5, 8, 12, 19},
    {3, 6, 9, 16, 22},
    {10, 13, 14, 17, 24},
    {18, 21, 23, 26, 30}
};
```

### key

`5`

## 출력 1

`true`

## 입력 2

### 배열

```c
{
    {1, 4, 7, 11, 15},
    {2, 5, 8, 12, 19},
    {3, 6, 9, 16, 22},
    {10, 13, 14, 17, 24},
    {18, 21, 23, 26, 30}
};
```

### key

`10`

## 출력 2

`true`

## 입력 3

### 배열

```c
{
    {1, 4, 7, 11, 15},
    {2, 5, 8, 12, 19},
    {3, 6, 9, 16, 22},
    {10, 13, 14, 17, 24},
    {18, 21, 23, 26, 30}
};
```

### key

`20`

## 출력 3

`false`
