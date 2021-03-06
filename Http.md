__Http란?__
===============
- HTML, TEXT, 음성, 영상파일, JSON, XML등 모든 형태의 데이터를 전송하는 애플리케이션 프로토콜이다.
- 초기에는 웹 브라우저와 웹 서버 간의 커뮤니케이션을 위해 디자인되었지만 최근에는 모바일 애플리케이션 및 IoT 등과의 커뮤니케이션과 같이 다른 목적으로도 사용되고 있다. 
- TCP:HTTP/1.1, HTTP/2 -> HTTP1.1, 2 버전은 TCP프로토콜을 기반으로 되어있다. -->TCP프로토콜안에 HTTP프로토콜 존재
- UDP: HTTP/3 

__HTTP 특징__
===================
1. 클라이언트 서버 구조
2. 무상태 프로토콜(스테이스리스), 비연결성
3. HTTP 메시지
4. 단순함, 확장 가능

__1. 클라이언트 서버 구조__
====================================
- Request Response 구조
- 클라이언트는 서버에 요청을 보내고 응답을 대기
- 서버가 요청에 대한 결과를 만들어서 응답

![image](https://user-images.githubusercontent.com/96917871/154285201-1c0ff685-b296-4f74-ba39-27836fd5396f.png)

__2. 무상태 프로토콜(Stateless)__
============================================
- 서버가 클라이언트의 상태를 보존하지 않는다.
- 클라이언트의 상태를 보존하지 않기 때문에 서버를 쉽게 확장시킬수 있다.
- 서버는 클라이언트가 어떤 상태인지 모르기 때문에 클라이언트는 서버에게 추가 데이터를 전송해야된다.       

__<상태(Stateful)>__      
- 클라이언트는 항상 같은 서버에 유지되어야된다. -> 중간에 서버가 장애가 발생한다면 클라이언트가 다시 초기 단계로 돌아가야된다.

![image](https://user-images.githubusercontent.com/96917871/154286125-b172f6f0-65a2-4896-b7ea-b54b8a68ed10.png)

__<무상태 프로토콜의 한계>__    
- 모든것을 무상태로 설계할수 있는것이 아니다 -> 로그인에 따라 바뀌는 구조등
- 로그인이 필요 없는 단순한 서비스 소개화면 -> 무상태로 구현
- 로그인에 따라 바뀌는 서비스의 경우 상태 유지로 구현 -> 로그인한 사용자의 경우 로그인 했다는 상태를 서버에 유지 --> 일반적으로 브라우저 쿠기와 서버 세션등을 사용해서 유지
- 상태유지는 최소한으로 사용해야된다.

__2. 비연결성__
=============================
- HTTP는 기본이 연결을 유지하지 않는 모델 -> 필요한 데이터를 주고받고 클라이언트와 연결을 다시 끊어 버린다.
- 수천명이 서비스를 사용해서 서버에 동시에 처리하는 요청은 수십개이하로 작다 -> 서버의 자원을 효율적으로 사용할 수 있다.
- TCP/IP 연결을 새로 맺어야 함 -> 3 way handshake(시간이 추가된다) --> 지속연결(Persistent Connections)로 문제 해결함 ---> 웹 브라우저로 사이트를 요청할때 HTML뿐만 아니라 자바스크립트, css,이미지등 수많은 자원이 함께 되는데 그렇때마다 TCP/IP 연결을 새로 맺어야 하는데 "지속연결"을 통해 HTTP한계를 극복

__3. HTTP 메시지__
=================================
![image](https://user-images.githubusercontent.com/96917871/154289354-8e3239c0-cf58-438c-a493-2786a3895a4e.png)

__시작 라인(start-line)__        
-----------------------
- "request-line", "status-line"으로 이루어짐

__<요청(Request 메시지)>__      
![image](https://user-images.githubusercontent.com/96917871/154292104-8f8bc353-7183-4237-9125-bfc4dc23121c.png)

- request-lint을 사용 -> "request-line = method SP(공백) request-target SP HTTP-version CRLF(엔터)" --> 구조
- HTTP 메서드 -> GET
- 요청대산 -> /search?q=hello&hl=ko"
- HTTP버전 -> HTTP/1.1

__<응답(Response 메시지)>__     
![image](https://user-images.githubusercontent.com/96917871/154292214-5341d64f-0371-487f-b63f-e5899232c487.png)
   
- status-line으로 사용 -> "status-line = HTTP-version SP status-code SP reason-phrase CRLF"
- HTTP버전 -> HTTP/1.1
- HTTP 상태 코드 -> 요청 성공,실패를 나타냄 --> 200:성공, 400:클라이언트 요청 오류, 500:서버 내부 오류
- 이유 문구(reason-phrase) -> 사람이 이해할수 있는 짧은 상태 코드 설명 글


__HTTP 헤더__
---------------------------------
![image](https://user-images.githubusercontent.com/96917871/154292662-1a65bd3e-9423-4e62-9ade-82847e0de96d.png)

- hearder-field => field-name":" OWS field-value OWS (OWS:띄어쓰기 허용) -> field-name: Host, Context-Type, Context-Length / filed-value: www.google.com, text/html......
- HTTP 전송에 필요한 모든 부가정보 
- 예) 메시지 바디의 내용, 메시지 바디의 크기, 압축, 인증, 요청 클라이언트(브라우저) 정보, 서버 애플리케이션 정보, 캐시 관리 정보..


__HTTP 메시지 바디(message body)__
-------------------------------
- 실제 전송할 데이터
- HTML 문서, 이미지, 영상, JSON 등등 byte로 표현할 수 있는 모든 데이터 전송 가능
