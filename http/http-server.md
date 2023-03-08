---
description: 03-HTTP Server
---

# HTTP Server

### Java ServerSocket

HTTP Client 와 다르게 Server 는 Listen을 하고고 있다가 들어오는 Request에 응답을 해주기 때문에 ServerSocket을 사용한다. Socket을 상속한 게 아니라 완전히 구별된다.

### Blocking vs Non-Blocking

`Socket socket = listener.accept();` 해당 부분에서 멈춰 있게 되는데 이렇게 기다리는 걸 Blocking 이라고 한다. Non-Blocking 은 작업이 중단되지 않으며 완료가 될때까지 기다리지 않고 다른 작업을 수행할 수 있다.
