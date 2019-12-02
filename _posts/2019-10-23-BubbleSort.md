---
layout: post
title: 버블정렬(Bubble Sort)
tags:
  - java
  - bubble
categories: [Java,Algorithm]
---
## 버블정렬(Bubble Sort) 알아보기

1. 첫 번째 자료와 두 번째 자료를, 두 번째 자료와 세 번째 자료를, 세 번째와 네 번째를, … 이런 식으로 (마지막-1)번째 자료와 마지막 자료를 비교하여 교환하면서 자료를 정렬한다. -> 서로 인접한 두 원소를 비교한다.
2. 1회전을 수행하고 나면 가장 큰 자료가 맨 뒤로 이동하므로 2회전에서는 맨 끝에 있는 자료는 정렬에서 제외되고, 2회전을 수행하고 나면 끝에서 두 번째 자료까지는 정렬에서 제외된다. 이렇게 정렬을 1회전 수행할 때마다 정렬에서 제외되는 데이터가 하나씩 늘어난다. -> 인접한 두 원소가 순서대 되어있지 않으면 교환한다.
<hr>
## 버블정렬의 특징
* 장점
  - 구현이 간단하고 <u>안전 정렬</u>이다.
  - 데이터를 하나씩 비교하여 정밀하다.
* 단점
  - 하지만 비교횟수가 너무 많아지고 비효율적이여서 잘 쓰이지 않는다.

**<i class="fa fa-question-circle"></i> `안전 정렬과 불안정 정렬`**
> <b> 안정 정렬 </b>: 동일한 값에 대해 기존의 순서가 유지되는 정렬 방식  
> <b>불안정 정렬 </b>: 동일한 값에 대해 기존의 순서가 유지되지 않는 정렬 방식

<hr>
## 버블정렬 구현
```java
import java.util.Arrays;

public class BubbleSort {

  public static void main(String[] args){
    int[] array = {8, 4, 5, 1};

    bubbleSort(array);
  }

  private static void bubbleSort(int[] array){
    int temp = 0;
    int size = array.length -1;
    for(int i=0; i<size; i++){
      for(int j=0; j<size-1; j++){
        if(array[j] > array[j+1]){
          temp = array[j];
          array[j] = array[j+1];
          array[j + 1] = temp;
        }
      }
      System.out.println((i+1) + "회전 후 : " + Arrays.toString(array));
    }
  }

}
```
