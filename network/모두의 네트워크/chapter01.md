# 1장 네트워크 첫걸음

> 네트워크의 기초 지식 익히기



## LESSON 01 네트워크의 구조



### 컴퓨터 네트워크란?

- 두 대 이상의 컴퓨터가 데이터를 주고 받는 것

  > 컴퓨터 간의 파일 전송, 웹 사이트 열람, 메일 송수신

- 인터넷 : 전 세계의 네트워크를 연결하는 네트워크



### 패킷이란?

- 네트워크를 통해 전송되는 데이터의 작은 조각

- 하나의 데이터가 네트워크의 대역폭을 많이 차지해 다른 패킷의 흐름을 막는 것을 방지

  > 대역폭 : 네트워크에서 이용 가능한 최대 전송 속도로 정보를 전송할 수 있는 단위 시간당 전송량

- 전송받은 패킷을 원래 데이터로 복원하는 작업 필요

- 패킷이 전송한 순서대로 도착하지 않을 수 있기에 *패킷에 번호*를 부여



## LESSON 02 정보의 양을 나타내는 단위



### 비트와 바이트란?

- 컴퓨터가 다루는 숫자 0과 1의 집합을 디지털 데이터라고 한다.

- 이 0과 1의 정보를 나타내는 최소 단위를 **비트(bit)**라고 한다.

- 비트 8개가 모인 것의 단위를 **바이트(byte)**라고 한다.

- 문자를 숫자에 대응하여 컴퓨터를  통해 입출력이 가능한데 이 대응표를 **문자 코드**라고 한다.

  > ex) ASCII코드

- 문자 데이터도 사진과 마찬가지로 패킷으로 전송



## LESSON 03 랜과 왠

> 네트워크는 랜(Lan)이라고 하는 좁은 범위의 네트워크와 왠(WAN)이라고 하는 넓은 범위의 네트워크로 구분된다.



- 같은 건물이나 특정 지역을 범위로 하는 네트워크를 **랜(LAN)**이라고 한다.

  > ex) 지리적으로 같은 곳에 위치한 컴퓨터와 프린터를 연결하는 네트워크

- 인터넷 서비스 제공자(ISP)가 제공하는 서비스를 사용하여 구축된 네트워크를 **왠(WAN)**이라고 한다.

  > 랜과 랜을 연결하는 것으로 이해 가능. ex) KT, U+, SK브로드밴드

- 랜은 좁은 범위를 랜 케이블로 연결, 거리가 짧은 만큼 신호가 약해지거나 오류가 발생할 확률이 낮다.

- 속도 또한 랜이 앤보다 빠르다.



## LESSON 04 가정에서 하는 랜 구성



- 랜과 왠을 이용하여 네트워크를 구성
- 인터넷 서비스 제공자(ISP), 인터넷 회선, 인터넷 공유기를 필요
- 인터넷 공유기를 중심으로 내부 인터넷망을 구성하고, 다양한 기기를 연결



## LESSON 05 회사에서 하는 랜 구성



### 소규모 회사의 네트워크 구성

- 가정의 네트워크 구성에 추가적으로 DMZ(외부에 공개하기 위한 네트워크)라는 네트워크 영역이 있다.
- 외부 사용자에게 웹 사이트 공개를 위한 웹 서버, 메일을 주고받기 위한 메일 서버,  도메인 이름을 사용하여 회사 서버에 접속하기 위한 DNS 서버를 공개한다.
- 회사 서버를 운영하기 위해 서버를 1)사내에 설치하거나 2)데이터 센터에 두거나 3)클라우드에 둘 수 있다.
  - 데이터 센터: 대량의 데이터를 보관하기 위해 데이터 센터 서버나 네트워크 기기를 설치한 전용 시설
  - 클라우드: 인터넷을 통해 소프트웨어나 하드웨어 등의 컴퓨팅 서비스를 제공, 인터넷에 접속하기만 하면 언제 어디서든 이용 가능

- 사내에서 서버를 운영하는 경우 서버 장비실을 두는데 이 운영 방법을 온프레미스라고 한다.