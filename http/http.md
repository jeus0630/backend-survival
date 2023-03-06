---
description: 01-HTTP의 이해
---

# HTTP의 이해

### HTTP(Hypertext Transfer Protocol)

웹에서는 HTML, Video, Image 이 모든 것들이 Resource 라고 불린다. 이러한 리소스를 서로 주고 받는 데에 특정한 규약이 필요하다. 택배 보낼때에 정해진 규약에 따라서 송장을 작성하듯 말이다. 이러한 규약을 프로토콜 이라고 불리며 웹에서의 모든 데이터를 교환할 때 사용되는 프로토콜이 HTTP이다.&#x20;

### HTTP와 HTTPS의 차이(TLS)

![](<../.gitbook/assets/Screenshot from 2023-03-06 21-23-27.png>)&#x20;

우리가 네트워크 통신을 할 때에 사용되는 프로토콜 및 디자인을 계층마다 나눠 놓은 것을 OSI 7계층이라고 하는데 그중 HTTP는 7계층인 Application Layer에 위치해 있다. HTTP와 HTTPS는 하위 레이어들의 프로토콜인 IP, TCP 등은 동일하나 HTTPS 에서는 TCP 위에 TLS(예전에는 SSL) 라는 보안계층이추가된 것으로 HTTP를 사용함은 동일하다.

### 클라이언트-서버 모델

클라이언트와 서버는 개별적인 메세지 교환에 의해서 통신을 하게 된다. 클라이언트에 의해 전송되는 메세지를 요청(request) 라고 하며 서버에 의해 전송 되는 메세지를 응답(response) 라고 부른다. 그리고 해당 메세지를 HTTP 메세지라고 부르며 이 해당 메세지를 해석하고 HTML을 보여주는 프로그램이 브라우저이다.

### stateless와 stateful

HTTP 프로토콜은 상태를 저장하지 않는다. 게임이나 채팅 같은 프로그램의 경우에는 한번 연결이 되며 Request를 하는 클라이언트가 누구인지 알고 연결이 되어 있으나 HTTP는 연결이 되어 있지 않는다. 이를 stateless라고 부른다. 반대의 경우를 stateful라고 한다.

### HTTP Cookie와 HTTP Session

위에서 말했듯이 HTTP는 stateless 형태이다. 하지만 상호작용 하는 과정에서 서버는 클라이언트가 누구인지 알아야 할 필요가 있다. 이렇게 클라이언트의 정보를 서버의 어딘가에 저장하는것을 Session 이라고 부르고 Session의 구분값을 Cookie를 통해서 확인하는 과정을 거치게 된다. Cookie는 항상 Request시마다 함께 보내게 된다.

### HTTP 메시지 구조

*   #### HTTP 요청(Request)와 응답(Response)

    위에서 클라이언트와 서버간에는 서로 HTTP 메세지를 주고받는다고 했다. 이 주고받는 메세지에는 특정한 포맷이 존재하며 해당 포맷에 맞춰 브라우저가 해석을 하게 된다. \
    \- Start line\
    \- Header Set (여러개)\
    \- 빈 줄\
    \- Body\
    이렇게 4가지의 형태가 존재하며 multipart/form-data 의 경우에는 body 값을 여러개를 가질 수가 있다.
*   #### HTTP 요청 메서드(HTTP request methods)

    \- GET -> READ\
    \- HEAD -> GET without body\
    \- POST -> Create\
    \- PUT -> Update\
    \- PATCH -> Update\
    \- DELETE -> Delete\
    \- OPTIONS -> 지원 확인\
    가 존재하며 GET은 멱등성을 지키는 방면에 POST는 멱등성을 지켜주지 않는다. PUT과 PATCH의 차이는 PUT은 Overwrite 개념으로 전체를 덮어 씌우는 거고 PATCH는 일부만 업데이트를 하는 것이다.
*   #### HTTP 응답 상태 코드(HTTP response status code)

    표준으로 정해진 상태 코드 그룹이 있다. 즉 100번대, 200번대, 300번대, 400번대, 500번대 이렇게 정해져 있는데 브라우저가 표준으로 정해진 응답 코드에 맞춰서 동작을 하게 된다.\
    \- 100번대 -> 정보 (쓰는 일 드뭄)\
    \- 200번대 -> 200 OK, 201 Created, 204 No Content\
    \- 300번대 -> 리다이렉션 (304는 cache 관련으로 자주 보임)\
    \- 400번대 -> 클라이언트 쪽 문제\
    \- 500번대 -> 서버 쪽 문제
