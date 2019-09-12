---
layout: post
title: 자바 Collection에 대해서
tags:
  - java
  - Collection
categories: [Java]
---
## Java Collection Framework(JCF)란 ?
> 자바에서 컬렉션 프레임워크(collection framework)란 다수의 데이터를 쉽고 효과적으로 처리할 수 있는 표준화된 방법을 제공하는 클래스의 집합을 의미한다.

즉, 데이터를 저장하는 자료 구조와 데이터를 처리하는 알고리즘을 구조화하여 클래스로 구현해 놓은 것입니다.

컬렉션 프레임워크는 자바의 인터페이스(interface)를 사용하여 구현된다.

다음은 Java Collection Framework의 구조이다.
![CollectionFramework]({{site.url}}/images/CollectionFramework.JPG){: width="550" height="400"}

List와 Set은 객체 추가, 삭제 검색하는 방법에 많은 공통점이 있기 때문에 이 인터페이스들의 공통된 메소드들만 모아 Collection 인터페이스로 정의해 두고 있다. Map은 키와 값을 하나의 쌍으로 묶어서 관리하는 구조로 되어있어 List및 Set과는 사용방법이 완전히 다르다.
<hr>
## Collection Framework Interface
컬렉션 프레임워크에서는 데이터를 저장하는 자료 구조에 따라 핵심이 되는 주요 인터페이스를 정의한다.

![CollectionInterface]({{site.url}}/images/CollectionInterface.JPG){: width="484" height="241"}
**인터페이스에 대해 더 알고싶다면 <i class="fa fa-arrow-right"></i>** [List](/list) [Set](/set) [Map](/map)

<hr>
## Collection Framework Method
컬렉션 프레임워크 인터페이스에서 제공하는 주 메소드 이다.

![CollectionMethod]({{site.url}}/images/CollectionMethod.JPG){: width="482" height="353"}

<hr>
## 참조
[https://minwan1.github.io/2018/07/03/2018-07-03-collection/](https://minwan1.github.io/2018/07/03/2018-07-03-collection/)
[https://shxrecord.tistory.com/74](https://shxrecord.tistory.com/74)
[http://tcpschool.com/java/java_collectionFramework_concept](http://tcpschool.com/java/java_collectionFramework_concept)
