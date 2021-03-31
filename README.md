# Socket & Networking

1. 2-tier C/S 모델 : 클라이언트와 서버가 1:1로 연결 [client - sever]
2. 3-tier 모델 : 서버를 조금더 유연하게 구성, 응용서버와 데이터서버로 구성하는 경우, 데이터베이스를 분리시킴 [client - sever - DB]

### 소켓
+ TCP/IP 수준의 통신 방식을 제공하는 소켓을 이용해 서버에 연결가능
+ 일반적인 프로그래밍에서는 대부분 TCP연결 사용
+ 비연결성 특성으로 인해 실시간으로 데이터를 처리하는 애플리케이션의 경우, 응답 속도를 높이기 위해 HTTP보다 Socket연결 선호
+ 안드로이드에서는 표준 자바의 소켓을 그대로 사용이 가능함.
+ 서버쪽에서는 서버소켓을 만들어 실행함(포트 지정)
+ 클라이언트쪽에서는 소켓을 만들어 서버소켓과 연결함(IP와 포트 지정)
+ Stream 객체를 이용해 데이터를 주고받을 수 있음

## 네트워크 사용시 주의점
+ 네트위킹을 사용할 때는 반드시 Thread 사용
+ Thread를 사용하기 때문에 UI 업데이트를 위해서는 반드시 Handler 사용(post메소드)


## 임의로 안드로이드상에서 서버와 소켓 만들어서 보내보기
[Server_example](https://github.com/h0keun/server_example)
```
2021-03-31 19:08:55.018 18828-18950/com.grow.sever_example D/ServerThread: intput : 안녕!
2021-03-31 19:08:55.023 18828-18950/com.grow.sever_example D/ServerThread: output 보냄.
```
[Socket_example](https://github.com/h0keun/socket_example/tree/main)
```
2021-03-31 19:08:55.015 17894-18977/com.grow.socket_example D/ClientThread: 서버로 보냄.
2021-03-31 19:08:55.024 17894-18977/com.grow.socket_example D/ClientThread: 받은 데이터 : 안녕! from server.
```
