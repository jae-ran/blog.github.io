---
layout: post
title: OpenStack에 대해서
tags:
  - openstack
  - cloud
categories: [Etc]
---
## 오픈스택이란?
> [오픈스택 공식 사이트](www.openstack.org)에 따르면 오픈스택이란 `Open Source software for creating private and public clouds`이라고 정의 할 수 있다.

즉, 공용(public) 클라우드와 사설(private) 클라우드 구축을 가능하게 하는 IaaS 역할을 하는 OSS(오픈 소스 소프트웨어)이다.

OpenStack은 서버, 스토리지, 네트워크들과 같은 자원들을 모두 모아 이들을 제어하고 운영하기 위한 클라우드 Operating System이다.
<hr>

## 서비스
오픈스택은 기능에 따라 구성 요소가 분리되어 있다. 주로 사용되는 서비스에 대해 살펴보자.

#### <i class="fa fa-cogs"></i> NOVA(Cloud Compute Service)
>가상머신 라이프사이클 관리자

클라우드 IaaS 구축에 필요한 컴퓨팅 자원을 제공하고 관리하는 서비스이다. 오픈스택에서 가장 핵심적인 프로젝트로 가상머신의 생성, 갱신, 삭제, 생명주기 관리 기능을 제공한다.

다수의 Hypervisor를 지원하여 KVM, Hyper-V, VMWare 등을 사용할 수 있다.

AWS의 EC2와 호환된 API를 제공한다.

**<i class="fa fa-question-circle"></i> Hypervisor?**
쉽게 말하면 가상화OS이다. 호스트 컴퓨터 1대에서 다수의 운영체제를 동시에 실행할 수 있는 가상 플랫폼 기술을 말한다. 가상화 머신 모니터(VMM)라고도 말한다.

#### <i class="fa fa-database"></i> Cinder(Blocked Storage Service)
> 블록(Block)기반 스토리지 서비스.

범용의 저장장치를 기반으로 디스크 볼륨을 제공.

Cinder에 의해 생성된 가상 디스크 볼륨은 가상머신에 마운트 되어 가상머신 사용자의 데이터를 저장하는데 사용될 수 있다.

Nova에서 생성된 인스턴스에 확장하여 사용할 수 있는 저장 공간을 생성 및 삭제하고 인스턴스에 연결할 수 있는 기능을 제공한다.

#### <i class="fa fa-archive"></i> Swift(Cloud Storage Service)
> 오브젝트(Object) 스토리지 서비스.

대용량 데이터를 저장할 수 있는 높은 확장성을 가지는 오브젝트 저장장치를 제공하는 서비스이다.

#### <i class="fa fa-desktop"></i> Horizon(Dashboard Service)
> 웹 기반의 대시보드 서비스.

오픈스택에서 일어나는 서비스에 대한 인터페이스를 웹 베이스로 제공한다. VM을 생성하거나 IP를 지정하는 등의 서비스를 CLI가 아닌 웹에서 사용자가 직접 실행할 수 있도록 도와주는 툴이다.

아파치 웹 서버를 사용하며, 대시보드는 파이썬 장고 프레임워크로 구현되어 있다.

#### <i class="fa fa-unlock-alt"></i> Keysotne(Identity Service Keystone)
> 오픈스택 서비스들을 위한 통합 인증 시스템.

사용자 및 API에 대한 인증 및 권한 설정 서비스를 제공한다.

#### <i class="fa fa-image"></i> Glance(Cloud Image Service)
> 가상 디스크 이미지들을 저장/등록/관리/전달 할 수 있게 하는 오픈 소스.

다양한 하이퍼바이저에서 사용할 수 있는 가상 머신 이미지를 관리하고 가상머신에 설치 된 운영체제를 보관 및 관리한다.

Swift 프로젝트의 오브젝트 저장장치를 포함한 가상 머신 이미지 저장소로부터 가상머신 이미지를 탐색, 등록 및 추출하는 기능을 제공한다.

Nova를 통해 생성되는 가상 머신은 Glance를 통해 가상 머신 이미지를 제공받고 관리한다.

#### <i class="fa fa-network-wired"></i> Neutron(Network Service)
> 소프트웨어 기반의 네트워킹 서비스를 제공.

VLAN, Router등을 생성하고 변경하거나 삭제한다. Load Valancing, 방화벽, VPN 등을 제공하기도 한다.

네트워킹 기능은 Neutron과 연결된 네트워크 프로바이더에 의해 제공된다.
<hr>
## 출처
[https://www.ibm.com/kr-ko/cloud/products#934716](https://www.ibm.com/kr-ko/cloud/products#934716)
[https://sarc.io/index.php/cloud/736-openstack-series-1-openstack](https://sarc.io/index.php/cloud/736-openstack-series-1-openstack)
[https://www.dellemc.com/ko-kr/glossary/object-storage.htm](https://www.dellemc.com/ko-kr/glossary/object-storage.htm)
[http://liwonace.co.kr/openstack/](http://liwonace.co.kr/openstack/)
