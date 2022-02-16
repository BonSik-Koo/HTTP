__URI__
===================
- Uniform: 리소스 식별하는 통일된 방식, Resource: 자원, URI로 식별할 수 있는 모든 것, Identifier: 다른 항목과 구분하는데 필요한 정보
- 인터넷 자원을 나타내는 고유 식별자이다. 
- "URL(Uniform Resource Locator)", "URN(Uniform Resource Name)"이 속해있다.

![image](https://user-images.githubusercontent.com/96917871/154253657-d80b920c-b3fb-4949-8afd-4284959b5c6c.png)

__URL__
===================
- URL-Locator: 리소스가 있는 위치를 지정
- 해당 자원의 위치, Path를 의미한다.
- 보통 URI를 URL과 같은의미로 말한다.

__URN__
============
- 해당 자원의 이을 의미한다.
- URN 이름만으로 실제 리소스를 찾을수 있는 방법은 보편화 되어있지 않다.

![image](https://user-images.githubusercontent.com/96917871/154254458-950eb3dc-a50e-40fa-a1cd-7aa6aa790494.png)

__URL의 문법__
===================
<예>           
__scheme://[userinfo@]host[:port][/path][?query][#fragment]__ -> __https://www.google.com:443/search?q=hello&hl=ko__

__scheme__
-----------------------
- 주로 프로토콜 사용
- 프로토콜: 어떤 방식으로 자원에 접근할 것인가 하는 약속 규칙 -> 예)http, https, ftp등..
- http는 80포트, https는 443포트를 주로 사용한다. -> 포트는 생략이 가능하다!!
- https는 http에 보안이 추가된 프로토콜이다!!

__userinfo__
------------------------
- URL에 사용자정보를 포함해서 인증
- 거의 사용하지 않음

__host__
---------------
- 호스트명 
- 도메인명 또는 IP주소를 직접 사용가능

__port__
------------------
- 접속 포트
- 생략시 -> http는 80, https는 443포트를 사용하여 host에 접속하게 된다!!

__path__
----------
- 리소스의 경로(path), 보통 계층적 구조로 이루어져있다.

__
