---
layout: post
title: BufferedReader와 BufferedWriter
tags:
  - IO
  - BufferedReader
  - BufferedWriter
categories: [Java]
---
Java를 처음 접하면서 쭉 데이터를 입력받을 때 <b>Scanner</b>를 사용하였다. Scanner는 <u>Space(띄어쓰기)와 Enter(개행문자)를 입력값의 경계로 인식</u>하기 때문에 데이터를 가공하기 매우 편하다. 게다가 데이터 타입이 입력 받는 시점에 결정되어 별도의 <u>Casting이 필요하지 않다</u>는 장점이 있다.
## Scanner
```java
Scanner sc = new Scanner( System.in );
int N = sc.nextInt();
```
이러한 편리함으로 Scanner만 사용해도 되지 않을까.. 싶었지만 입력값이 커질수록 더 빠른 연산이 필요할때는 상대적으로 속도가 빠른 <b>BufferedReader</b>를 사용하는 것이 좋다!

BufferedReader는 사용자가 요청할 때마다 데이터를 읽어 오는 것이 아니라 일정한 크기의 데이터를 한번에 읽어와 버퍼에 보관 한 후, 사용자의 요청이 있을 때 버퍼에서 데이터를 읽어오는 방식으로 동작한다. 때문에 <u>속도가 향상되고 시간 부하가 적다</u>는 장점이 있다.

BufferedReader는 입력을 <u>라인단위</u>로 입력 받기 때문에 공백의 경우에도 String으로 인식하여 받아들이고, 입력받은 데이터 타입이 String 타입이므로 다른 타입의 데이터라면 이후 <u>형변환이 필요</u>하다는 특징이 있다. 또한 <u>예외처리</u>를 따로 해줘야 한다.
## BufferedReader
```java
BufferedReader br = new BufferedReader( new InputStreamReader( System.in ) );
int N = Integer.parseInt( br.readLine() );
```
여기서 InputStreamReader는 문자열을 <u>Character 단위(한 글자씩)로 읽어 들인다.</u>길이가 긴 문자열을 읽어들일 경 상당히 불편하고 비효율적이기 때문에 이점을 보완하고자 버퍼링 기능이 추가된 BufferedReader 클래스가 있는 것이다.
## StringTokenizer
```java
BufferedReader br = new BufferedReader( new InputStreamReader( System.in ) );
StringTokenizer st = new StringTokenizer( br.readLine() );

int N = Integer.parseInt( st.nextToken() );
int T = Integer.parseInt( st.nextToken() );
```
StringTokenizer를 이용하면 nextToken() 함수를 이용해 입력받은 값을 공백단위로 구분하여 토큰을 읽어온다. 공백을 기본으로 구분하지만 선언시 두번째 파라미터로 별도의 구분자를 추가할 수도 있다.
## BufferedWriter
```java
BufferedWriter bw = new BufferedWriter( new OutputStreamWriter( System.out ) );
bw.write( "Hello World!!\n" );   // 출력
bw.flush();   // 남아있는 데이터 모두 출력
bw.close();   // 스트림 닫기
```
마찬가지로 BufferedWriter 함수 또한 버퍼를 이용하기 때문에 많은 양의 출력이 필요할 때 성능이 더 좋다. System.out.println처럼 자동 줄바꿈을 해주지 않기때문에 개행을 원하면 별도의 와일드카드(\n)로 처리해야 한다.
다만, 주의할 점은 flush()함수나 close()함수를 통해 버퍼에 남아 있는 데이터를 출력해 없애고, 스트림을 닫아줘야 한다!!

## 참조
[공부하자] 블로그 [https://carpediem0212.tistory.com/11](https://carpediem0212.tistory.com/11)  
몰랑이말랑이 블로그[https://jhnyang.tistory.com/92](https://jhnyang.tistory.com/92)
