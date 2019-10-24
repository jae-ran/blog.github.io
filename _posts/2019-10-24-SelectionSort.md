---
layout: post
title: 선택정렬(Selection Sort)
tags:
  - java
  - selection
categories: [Java,Algorithm]
---
## 선택정렬(Selection Sort) 알아보기

1. 주어진 자료에서 첫 번째 자료를 가지고 두 번째 자료부터 마지막 자료까지 최솟값을 찾는다.
2. 그리고 첫번째 위치한 값과 교환한다.(1회전)
3. 다음 회전에서 두번째 자료를 남은 값 중에서 비교하고 최솟값과 교환한다.
4. 이러한 과정을 반복한다.
<hr>
## 선택정렬의 특징
* 장점
  - 구현이 쉽다고 불안정 정렬이다.
  - 작은 값을 선택하기 위해 비교 횟수는 많지만 교환 횟수는 매우 적은것이 장점이다.
  - 따라서 데이터량이 적거나 내림차순에서 오름차순을 하는 자료상태에 성능이 좋다.
* 단점
  - 데이터량이 많으면 속도가 매우 떨어진다.

> 안정 정렬 - 동일한 값에 대해 기존의 순서가 유지되는 정렬 방식 ( 버블 정렬, 삽입 정렬 )

  불안정 정렬 - 동일한 값에 대해 기존의 순서가 유지되지 않는 정렬 방식
<hr>
## 선택정렬 구현
```java
import java.util.Arrays;

public class SelectionSort{

  public static void main(String[] args){
    int[] array = {9, 6, 5, 3, 1};
    int index = 0;
    int temp = 0;

    for(int i=0; i<array.length-1; i++){
      index = i;
      for(int j=i+1; j<array.length; j++){
        if(array[index] > array[j]){
          index = j;
        }
      }

      temp = array[i];
      array[i] = array[index];
      array[index] = temp;

      System.out.println((i+1)+"회전 후 : " + Arrays.toString(array));
    }
  }

}
```
