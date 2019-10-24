---
layout: post
title: 삽입정렬(Insert Sort)
tags:
  - java
  - insert
categories: [Java,Algorithm]
---
## 삽입정렬(Insert Sort)을 알아보기

1. 두 번째 자료부터 시작하여 그 앞(왼쪽)의 자료들과 비교하여 삽입할 위치를 지정한 후 자료를 뒤로 옮기고 지정한 자리에 자료를 삽입하여 정렬하는 알고리즘이다.
2. 즉, 두 번째 자료는 첫 번째 자료, 세 번째 자료는 두 번째와 첫 번째 자료, 네 번째 자료는 세 번째, 두 번째, 첫 번째 자료와 비교한 후 자료가 삽입될 위치를 찾는다. 자료가 삽입될 위치를 찾았다면 그 위치에 자료를 삽입하기 위해 자료를 한 칸씩 뒤로 이동시킨다.
<hr>
## 삽입정렬의 특징
* 장점
  - 삽입정렬은 기본적으로 버블정렬의 비교횟수를 줄인다, 안정 정렬이다.
  - 비교적 크기가 작은 데이터 집합의 정렬에 유리하고, 이미 정렬되어 있는 경우 최적의 경우이다.
* 단점
  - 비교적 이동 횟수가 많다.
  - 데이터 집합이 많고 길수록 효율이 떨어진다.
<hr>
## 삽입정렬 구현
```java
import java.util.Arrays;

public class InsertSort {

    public static void main(String[] args) {
        int[] array = {8, 5, 6, 2, 4};

        insertSort(array);
    }

    private static void insertSort(int[] array) {
        int temp = 0;
        int j = 0;

        for(int i=1; i<array.length; i++){
            temp = array[i]; // Key값 = 삽입대상
            j = i;
            while(j > 0 && temp < array[j-1]){
                array[j] = array[j-1];    // 이동
                j--;
            }
            array[j] = temp;
            System.out.println((i)+"회전 후 : " + Arrays.toString(array));

        }
    }
}
```
