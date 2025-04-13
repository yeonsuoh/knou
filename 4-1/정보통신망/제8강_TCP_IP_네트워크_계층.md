# 8강 TCP/IP 네트워크 계층

# 1. IP

## 1-1 IP 개요

- 인터넷 프로토콜(IP) : OSI 모델의 네트워크 계층의 기능
- 사용자에게 복잡한 인터넷의 개별 네트워크들의 구조를 숨겨 모든 호스트들을 연결하는 1개의 가상 네트워크로 보이도록 함.
- 네트워크 계층의 투명성(transparency)을 제공함

## 1-2 비연결형 서비스 (Connectionless)

- 인터넷 계층의 투명성
    - IP 역할 : 호스트의 주소 지정 및 데이터그램 전송
    - 경유해야 하는 데이터 링크 및 라우터 정보를 무시
    - 신뢰성이 없는 데이터 전송

## 1-3 데이터그램

- IP 계층의 패킷
    - 버전
    - 헤더길이
    - 서비스 유형
    - 전체 길이
    - 식별자
    - 플래그
    - 단편 오프셋
    - TTL
    - 프로토콜
    - 헤더 검사합

## 1-4 IP 단편화

- IP 데이터그램의 분할
- MTU (Maximum Transfer Unit)
    - 네트워크 링크에서 허용하는 프레임당 데이터의 최대 길이
- IP 데이터그램은 전송 중 각 네트워크의 MTU에 적합한 크기로 분할되었다가 목적지 호스트에서 각 fragment들을 재조립함.

## 1-5 인터넷상에서의 라우팅

- 라우팅
    - IP 데이터그램이 목적지 호스트까지 진행하면서 경유할 경로를 결정하는 것
- 비교
    - IP : 송신자, 수신자 그리고 그 사이의 경로 상에 있는 모든 라우터들이 IP 데이터그램 전달에 관여
    - TCP : 송신자와 수신자만 TCP 세그먼트 전달에 관여
- 라우팅 테이블
- 동일한 물리적 네트워크에서의 데이터그램 전송

# 2. 주소변환

## 2-1 ARP (Address Resolution Protocol)

- 상대방 호스트의 IP 주소를 알고 데이터 통신을 위해 그 호스트의 물리주소를 알고자 할 때 사용하는 프로토콜
- IP 주소를 물리주소로 매핑해 주는 프로토콜

- 동적 바인딩
    - ARP는 호스트의 IP 주소를 대응하는 물리 주소로 변환하여 실제 데이터 통신이 가능하게 해줌
    - ARP 요청 : broadcasting
    - ARP 응답 : unicasting

## 2-2 RARP (Reverse Address Resolution Protocol)

- 물리주소만 알고 있는 호스트가 자신의 IP 주소를
  찾을 때 사용되는 프로토콜
- 일반적으로는 호스트의 IP 주소는 디스크에 저장된 구성 파일에서 확인
- 디스크가 없는 호스트는 물리주소만 알고 있으므로 이를 이용하여 IP 주소를 얻고자 함

# 3. ICMP (Internet Control Message Protocol)

## 3-1 ICMP 프로토콜

- 인터넷 계층 프로토콜
- 전송 오류 제어
    - IP 데이터그램의 전송과정에서 발생하는 오류를 라우터나 발신지 호스트에게 보고하는 메커니즘을 제공
    - IP의 전송 실패를 대신 처리해줌

## 3-2 ICMP 메시지

## 3-3 ICMP 메시지 유형

- 오류 보고 메시지 (error reporting)
    - 발신지 억제
    - 시간 초과
    - 목적지 도달 불가
    - 재지정
- 질의 메시지 (simple query)
    - 에코 요청 및 응답
    - 주소 마스크 요청 및 응답
    - 타임 스탬프 요청 및 응답
    - 라우터 요청 및 응답

# 4. IGMP (Internet Group Management Protocol)

## 4-1 IP 멀티캐스트

- 인터넷 계층 프로토콜
- 인터넷에서 multicast 서비스를 위해 사용되는 프로토콜
- IP 호스트가 어떤 멀티캐스트 그룹에 참가하고 있는지를 멀티캐스트 라우터에 통보하는 프로토콜
- 멀티캐스트
    - 하나의 그룹에 속한 호스트들에게 메시지 전송 (1-to-many)
    - 참고 : unicast (1-to-1), broadcast (1-to-all)

## 4-2 IGMP 메시지

- 유형
- 최대 응답시간
- 검사합
- 그룹 주소

## 4-3 IGMP 프로토콜

# 5 DHCP

## 5-1 IP 주소관리

- IP 주소 관리 방법
    - 기억하기 어려움 → IP 주소 관리 방법의 필요
        - Host Table
        - DNS (Domain Name System)
        - BOOTP (Bootstrap Protocol)
        - DHCP (Dynamic Host Configuration Protocol)

- 호스트 테이블
    - 모든 IP 주소와 이와 mapping되는 호스트 이름으로 구성된 테이블
- DNS (Domain Name System)
    - 계층적 구조 및 분산 관리 특성
    - 분산 관리의 문제
        - name server는 특정 네트워크 영역만의 정보를 가지며 다른 영역에 대해서는 다른 name server의 정보를 참조
    - name server 데이터의 복잡성
        - 수작업에 의한 데이터의 오류 가능성
- BOOTP (Bootstrap Protocol)
    - 기존의 방식은 IP 주소를 수작업으로 할당 (정적 할당)
    - BOOTP는 동적으로 IP 주소를 할당
    - 디스크가 없는 호스트(X 터미널)에 대해 주소 및 설정 정보를 자동적으로 할당하고 관리하는 프로토콜

## 5-2 DHCP 메시지 형식

- Dynamic Host Configuration Protocol
    - 응용계층 프로토콜
    - BOOTP에서 발전된 동적 주소 할당 프로토콜로서 IP 주소 재사용이 가능함
    - DHCP 메시지 형식은 BOOTP와 동일함
- 동적 주소 할당 프로토콜
    - IP 주소 pool에서 사용 가능한 IP 주소를 선택하여 원하는 호스트에게 일정기간 임대해 줌

## 5-3 DHCP 프로토콜

- IP 주소 자동 할당
    - DHCPDISCOVER
    - DHCPOFFER
    - DHCPREQUEST
    - DHCPACK