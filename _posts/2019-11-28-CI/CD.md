---
layout: post
title: CI와 CD에 대해서
tags:
  - CI
  - CD
categories: [Etc]
---
## CI와 CD란 무엇일까?
> CI/CD란 애플리케이션 개발 단계를 <b>자동화</b>하여 애플리케이션을 보다 짧은 주기로 사용자에게 제공하는 방법.

CI/CD의 기본 개념은 지속적인 통합, 지속적인 서비스 제공, 지속적인 배포를 말한다.
<hr>
## CI
> 지속적인 통합 수행(Continuous Integration)

개발자가 개발한 소스코드를 모아서 한꺼번에 빌드하는 통합 빌드의 과정 주기적으로 수행하는 것을 말한다. 소프트웨어가 거대하고 복잡해지면서 팀 단위로 개발이 이루어지고, 분업과 협업은 필수가 되었다. 이 때 소스 코드의 Merge 과정중 발생할 수 있는 문제를 해결하기 위한 기법이다. 즉 개발자간 코드 충돌을 방지하기 위해 <u>정기적인 빌드 및 테스트</u>를 하는 것을 말한다.

Agile 방법론이 표준화되고, 이를 통해 배포를 위한 빌드 단계, 테스팅 단계 등에서 시간을 절약할 수 있으며, 빠르게 변화하는 시장 변화 속도에 대응하여 속도와 품질을 보장할 수 있게 된다.
## CI 구성요소

#### CI Server
빌드 프로세스를 관리하는 서버<br>
EX) Jenkins, Travis CI

#### Source Code Management(SCM)
각 개발자의 성과물을 일괄적으로 버전 관리하고, 각 개발자가 언제든 최신 코드를 추출할 수 있게한다. <br>
Ex) Git, SubVersion

#### Build Tool
컴파일, 테스트 정적 분석 등을 실시해 동작가능한 소프트웨어를 생성하는 도구이다.

빌드는 형상 관리 시스템에 있는 소스코드를 가져와서 실행 가능한 파일로 만드는 일련의 과정을 말한다. <br>
Ex) Maven, Gradle, Ant

#### Test Tool
작성된 테스트 코드에 따라 자동으로 테스트를 수행하는 도구로 빌드 도구의 스크립트에서 실행된다. <br>
Ex) JUnit, Mocha
<hr>
## CD
> 지속적인 서비스 제공 또는 지속적인  포(Continuous Deploy/Delivery)

소프트웨어가 항상 신뢰 가능한 수준에서 배포될 수 있도록 지속적으로 관리하자는 개념이다.

CI의 연장선으로 생각하면 된다. 즉, CI 프로세스를 거친 코드에 대해 테스트 서버와 운영서버에 곧바로 그 내용을 배포해 반영하는 것이다.
<hr>
## 출처
[https://www.redhat.com/ko/topics/devops/what-is-ci-cd](https://www.redhat.com/ko/topics/devops/what-is-ci-cd)
[https://judo0179.tistory.com/47](https://judo0179.tistory.com/47)
[https://asfirstalways.tistory.com/303](https://asfirstalways.tistory.com/303)
[https://galid1.tistory.com/459](https://galid1.tistory.com/459)
