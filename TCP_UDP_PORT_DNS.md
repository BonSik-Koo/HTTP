__인터넷 프로토콜 스택의 4계층__
------------------------------------
![image](https://user-images.githubusercontent.com/96917871/154246362-8466a5ba-7124-4a06-afa3-bf368535c737.png)
![image](https://user-images.githubusercontent.com/96917871/154246596-ce1cb1d9-04d1-4c6b-b337-7d5cfc424d05.png)   
- 애플리케이션단에 해당하는 전달하고자 하는 데이터를 "HTTP"프로토콜을 이용하여 생성한다.
- OS단에 해단하는 TCP 프로토콜을 이용하여 출발지 IP,목적지 IP와 PORT정보등의 정보를 생성하여 감싸주게 된다.
- 그후 IP패킷에 필요한 정보를 생성하여 감싸주게 된다.
- 네트워크 인터페이스 단에 해당하는 LAN카드의 이더넷 정보등을 감싸주게 되고 최동적으로 인터넷망을 통해 서버로 전송되게 된다.

__TCP__
----------------
- 전송 제어 프로토콜(Transmission Control Protocal)
- 신뢰할 수 있는 프로토콜 -> 전송하고자 하는 IP와 연결을 맺은후 데이터 전송

__<특징>__
- 연결지향 -TCP 3 way handshake(가상연결)
- 데이터 전달 보증              
- 순서 보장              

![image](https://user-images.githubusercontent.com/96917871/154248351-69ef7bd4-e022-4664-ae7a-5382ac5c6e9e.png)
- 클라이언트에서 (1)"synchronize(SYN)" 접속요청을 서버에게 전송하게 되고 (2)서버 측에서 요청수락(ACK)와 접속 요청을 보내게 된다. (3)마지막으로 클라이언트에서 요청수락(ACK)을 보내게 되어 connect을 맺게된다. -> TCP는 이러한 과정의 연결방식을 하게 된다.
![image](https://user-images.githubusercontent.com/96917871/154248958-ccf94391-ba49-4bf0-a8ea-b5e5d209ba4d.png)

__



 



