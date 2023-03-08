---
description: 02-HTTP Client
---

# HTTP Client

### TCP/IP 통신

인터넷 프로토콜 스위트(Internet Protocol Suite)를 보통 TCP/IP 라고 부른다. 즉 TCP 프로토콜을 말하는게 아니다. 집합을 말한다.&#x20;

### TCP와 UDP

TCP 는 전달 및 순서를보장하고 UDP 는 전달 및 순서를 보장하지 않는다.

### Socket과 Socket API 구분

나는 일단 Socket과 Socket API 구분전에 Socket과 Web Socket을 구분하자. 둘이 혼용되어서 헷갈렸는데 둘은 엄연히 다르다. 일단 기본 Socket은 TCP/IP 4계층에서 전송 계층 위에 놓이는 거고 Web Socket은 HTTP 레이어에서 작동하는 소켓으로 두 개념은 다른 개념이다.&#x20;

Socket 과 Socket API 를 구분해보면 Socket 은 엔드포인트 개념이고 이 연결된 소켓을 프로그래밍할때 사용되는 API 가 Socket API 이다.

### TCP 통신 순서

1. 서버는 접속 요청을 받기 위한 소켓을 연다 -> Listen
2. 클라이언트는 소켓을 만들고, 서버에 접속을 요청한다. -> Connect
3. 서버는 접속 요청을 받아서 클라이언트와 통신할 소켓을 따로 만든다. -> Accept
4. 소켓을 통해 서로 데이터를 주고 받는다. -> Send & Receive -> 반복
5. 통신을 마치면 소켓을 닫는다.  -> Close -> Receive로 인지할 수 있다.

### URI 와 URL

URI 는 웹 에서의 자원을 식별하기 위한 식별자이고 URL 은 자원 식별을 주소로 하는것을 말한다.

### 호스트(host)

![](<../.gitbook/assets/Screenshot from 2023-03-08 01-24-48.png>)

URL 은 위와 같이 이루어져 있는데 호스트는 해당 부분을 말한다.&#x20;

소켓 통신을 할 때 호스트에 IP 주소를 넣어 줘도 되고 도메인 네임을 넣어줘도 된다. 도메인의 경우 DNS를 활용하기 때문에 제대로 하려면 복잡하지만 자바에서알아서 처리해준다.

### 포트(port)

포트는 같은 IP주소로 들어오는 요청을 구분하기 위한것으로 HTTP의 기본 포트 번호는 80이다.

### path(경로)

경로는 위 그림에서 포트 옆에 부분을 나타내는데 원래는 / 를 붙여주는게 맞으나 도메인 네임 뒤에 생략하면 / 가 붙은 상태로 기본적으로 브라우저에서 해석되어 처리해준다.

### Java text blocks

`String message = """`\
&#x20;   `GET / HTTP/1.1`\
&#x20;   `HOST: example.com`\
&#x20;   `"""`

위와 같은 방식으로 사용 가능하다. 자바스크립트의 템플릿 리터럴 이랑 비슷하다.

### Java InputStream 과 OutputStream

연결된 소켓에서 InputStream 과 OutputStream 을 통해서 스트림을 얻을 수 있다. 해당 스트림을 통해서 읽고 보내는게 가능하다.

### Java try-with-resources

자바에서 사용한 리소스를 자동으로 반납해줘야 할 때 try-with-resources를 사용 가능하다.\
