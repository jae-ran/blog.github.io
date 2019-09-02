---
layout: post
title: 자바 Iterator에 대해서
tags:
  - java
  - Iterator
  - 이터레이터
categories: [Java]
---
## Iterator란?
> Iterator는 Java Collection Framework에서 컬렉션에 저장되어 있는 요소들을 읽어오는 방법을 표준화 한 것.

Collection Framework란 데이터를 저장하는 클래스들을 표준화한 설계이다.
Iterator는 <u>반복자</u>라고 부르며 컬렉션이 보관하고 있는 자료들을 순차적으로 접근해 처리할 수 있다.

## Iterator method
* hasNext() : 다음에 읽어올 요소가 남아있는지 확인하는 메소드, 있다면 true 없으면 false반환.
* next(): 다음 요소 반환.
* remove(): next()로 읽어온 요소 삭제.

## Iterator 장단점
<b>장점</b>
1. 자동으로 Index를 관리해주어 사용하기 편리
2. 컬렉션 종류에 관계없이 일관성있게 접근 할 수 있다.(polymorphism)

<b>단점</b>
1. 객체를 만들어 사용하기 때문에 느리다.

## Iterable? Iterator?
> Iterable 인터페이스는 내부에 Interator 인터페이스를 리턴하는 메소드를 정의하고 있다.

Iterable 인터페이스는 for-each Loop를 사용할 수 있도록 해준다.

구조를 살펴보면 List,Set은 Collection을 상속받고 있고, Collection은 Iterable을 상속받고 있다.
![ListIterator]({{site.url}}/images/Iterator.png){: width="400" height="400"}

<b>Iterable:</b>
+ public Iterator iterator();  메소드를 구현하게 강제하기 위한 인터페이스.

<b>Iterator:</b>
+ public boolean hasNext();   /  public E next(); 와 같은 메소드를 구현하게 강제하기 위한 인터페이스

## ListIterator<E>란?
> ListIterator 인터페이스는 Iterator 인터페이스를 상속받아 여러 기능을 추가한 인터페이스이다.

Iterator 인터페이스는 컬렉션의 요소에 접근할 때 한 방향으로만 이동할 수 있다.

하지만 JDK 1.2부터 제공된 ListIterator 인터페이스는 컬렉션 요소의 대체, 추가 그리고 인덱스 검색 등을 위한 작업에서 양방향으로 이동하는 것을 지원한다.

단, ListIterator 인터페이스는 List 인터페이스를 구현한 List 컬렉션 클래스에서만 listIterator() 메소드를 통해 사용할 수 있다.

![ListIterator]({{site.url}}/images/ListIterator.JPG){: width="550" height="400"}

## 참조
[https://m.blog.naver.com/writer0713/220877874725](https://m.blog.naver.com/writer0713/220877874725)
[http://tcpschool.com/java/java_collectionFramework_iterator](http://tcpschool.com/java/java_collectionFramework_iterator)
