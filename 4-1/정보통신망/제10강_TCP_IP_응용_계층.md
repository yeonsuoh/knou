# 10강 TCP/IP 응용 계층

## 1. 응용 계층

### 응용 계층 개요

- 컴퓨터에서 웹 사이트에 접속할 때 필요한 프로토콜과 프로그램(서비스)이 있는 계층
- 클라이언트의 요청을 전달하기 위해 서버가 이해할 수 있는 메시지(데이터)로 변환하고 전송 계층으로 전달
- 서비스를 요청하는 측을 클라이언트
- 서비스를 제공하는 측을 서버

### 응용 계층 프로토콜의 종류

- 응용 계층 프로토콜은 TCP 및 UDP를 통해 유용한 기능을 수행
- 일반 사용자들은 TCP/UDP에 직접 접속하지 않고, 응용 계층을 통해 통신 서비스를 사용
- TCP 응용 계층 프로토콜에는 FTP, HTTP, TELNET, SMTP, POP3, IMAP
- UDP 응용 계층 프로토콜에는 DHCP, SNMP

### 응용 계층 프로토콜

- 프로토콜을 사용하기 위해서는 포트 번호가 있어야 함
- 포트(port)란 IP 주소에서 프로그램 상호 구분(프로세스 구분)을 위해 사용하는 번호

## 2. 웹서비스

### HTTP 프로토콜

- 웹 서비스
    - 보편적인 인터넷 서비스로 확대
        - 1989년 유럽물리입자연구소의 팀 버너스리가 WWW(World Wide Web : 웹) 개발
    - 웹은 TCP/IP의 의해 동작하며, 응용계층의 HTTP 프로토콜 사용
    - HTML(Hyper Text Markup Language) 문서를 전송

- HTTP 개념
    - Hyper Text Transfer Protocol
    - 클라이언트가 사이트 정보를 요청하는 것에 대해 서버가 응답하는 방식
    - 클라이언트는 HTML 파일 등 정보를 얻고 싶은 파일의
      URL(Uniform Resource Locator) 등의 요청 정보를 전송
    - 서버는 해당 정보를 받아 데이터를 반환
    - MIME(Multipurpose Internet Mail Extensions) 정보

- HTTP의 특징
    - 무상태(Stateless)와 비연결성(Connectionless)
        - 모든 요청과 응답은 이전의 것들과는 상관없이 독립적
        - 해당 요청에 필요한 모든 정보를 처음부터 보내야 함
        - 무상태의 단점을 보완하기 위해 쿠키, 세션 등 사용
    - 불특정 다수를 대상으로 하는 서비스에 적합

- HTTP 메시지 형식
    - 요청 메시지와 응답 메시지로 구분
        - 요청(상태) 라인, 헤더, 공백 라인(필수), 메시지 보디로 구성

### HTTPS 프로토콜

- HTTPS(HyperText Transfer Protocol over Secure Socket Layer)
- HTTP의 보안이 강화된 버전
- SSL이나 TLS 프로토콜을 통해 세션 데이터를 암호화
- HTTPS의 기본 포트는 443

- HTTP 보안키
    - 대칭키
        - 암호화와 복호화시 키가 같음
        - 클라이언트와 서버가 모두 공유키를 가짐
    - 공개키
        - 공개키와 개인키를 함께 사용
        - 암호화할 때는 공개키, 복호화할 때는 개인키
    - SSL(Secure Socket Layer) 적용
        - 인증서 필요
        - 인증서에 서비스의 정보 및 서버측의 공개키가 포함
    - CA(Certificate Authority)
        - 인증서 발급 기업
        - 브라우저는 CA 리스트를 가짐
        - CA 존재 확인후 CA의 공개키를 이용해 인증서를 복호화

- HTTPS 동작방식
    - 대칭키와 공개키 모두 사용
        - 데이터 전송을 위해 대칭키 사용
        - 대칭키를 안전하게 전달하기 위해 공개키 사용

## 3. 파일 전송 서비스

### 파일 전송 서비스 개요

- 클라이언트와 서버 사이에 파일 전송을 위한 서비스
- HTTP 프로토콜로 인해 FTP는 사용이 줄어들고 있음

### FTP 프로토콜

- FTP 동작 과정
    - FTP 서버와 FTP 클라이언트 간에 접속
    - FTP(File Transfer Protocol)는 21번/20번 포트를 사용

- 능동 모드 active mode
- 수동 모드 passive mode
    - 1024~65535 사이의 랜덤 비특권 포트를 사용

### SFTP 프로토콜

- SSH File Transfer Protoco
- SSH(Secure Shell) 파일 전송 프로토콜
- SFTP는 하나의 연결만 필요 (연결이 안정적임)
- SSH 키의 유효성 검사 및 관리 복잡

## 4. 원격 접속 서비스

### TELNET 프로토콜

- 원격 접속 서비스
    - 클라이언트에서 사용 권한을 가진 서버 시스템에 접속하여 작업을 수행하는 서비스
- TELNET(텔넷)은 원격지의 컴퓨터를 이용하는 가상 단말 기능을 실현하기 위한 프로토콜

### TELNET 동작 방식

- NVT
    - 터미널과 호스트와의 일대일 대칭적인 관계
    - Network Virtual Terminal

### SSH 프로토콜

- SSH의 정의
    - 기존의 유닉스 시스템 셸은 보완에 취약
    - SSH(Secure SHell)는 서버(원격지 호스트)에 접속하기 위해 사용되는 인터넷 프로토콜
    - 셸에 암호화가 추가된 버전

### SSH 동작 방식

## 5. 메일 서비스

### 메일 서비스 개요

- 메일 주소를 이용하여 인터넷을 통해 이메일을 주고받을 수 있도록
  서비스를 제공

### 메일 관련 프로토콜

- SMTP, POP3, IMAP 등 크게 3가지 프로토콜이 사용
    - SMTP: 메일을 송신할 때 사용하는 프로토콜
    - POP3: 메일을 전송받을 때 사용하는 프로토콜
    - IMAP: 메일을 전송받을 때 사용되는 또 하나의 프로토콜
      (POP3의 비동기성을 보완한 방식)