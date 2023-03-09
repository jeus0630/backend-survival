---
description: 05-Spring Web Mvc
---

# Spring Web MVC

### Spring

스프링 프레임워크는 모듈로 나뉜다. 애플리케이션을 만들때 필요한 모듈을 선택할 수 있으며 중심에는 종속성 주입 메커님즘을 포함한 코어 컨테이너의 모듈이 있다.&#x20;

### Spring Boot

스프링 부트는 스프링을 어플리케이션 프로덕션 레벨로 바로 실행할 수 있게 복잡한 환경설정들이 설정되어진 채 제공된다.

### Spring initializer

스프링 홈페이지의 이니셜라이저를 사용하면 바로 실행 가능한 코드와 프레임워크를 제공해 준다.

### Model-View-Controller(MVC) 아키텍처 패턴

디자인패턴과 아키텍처 패턴은 다른것이며 MVC는 아키텍처 패턴이다.\
View -> 표현\
Controller -> 입력\
Model -> 그외의 모든 것\
장고나 레일즈에서는 모델을 DB와 긴밀하게 연결해서 사용하는데 사실상 모델은 View와 컨트롤러를 제외한 모든 것 을 말한다.

### 관심사의 분리(Seperation of Concern)

각 관심사의 맞는 클래스를 생성하고 해당 클래스에서 작업을 하도록 나누는걸 관심사의 분리라고 한다. MVC 패턴은 이 관심사의 분리에 맞게 모델-뷰-컨트롤러로 나눈 것이다.

### Java Annotation

자바의 어노테이션은 소스코드에 추가해서 사용할 수 있는 메타 데이터의 일종이다. 어노테이션을 추가함으로서 자바에게 해당 메소드나 인터페이스등의 역할을 알려 줄 수 있다.

### Spring Annotation

&#x20;스프링에서 사용되는 어노테이션들이 있다. 해당 어노테이션을 통해 스프링에서 각 역할에 맞춰 작동을 하게 된다.

*   #### @RestController

    &#x20;컨트롤러를 RestController로 작업하겠다는 걸 명시하는데 내부적으로는아래의 2가지 어노테이션을 포함하고 있다.

    * #### @Controller
    *   #### @ResponseBody

        이 리스펀스 바디 어노테이션 덕분에 우리는 Template Engine 의 뷰파일이 아닌 문자 그대로를 내려줄 수 있다.
*   #### @RequestMapping

    RequestMapping 은 2가지가 핵심인데, path 와 method 이다.

    *   #### @GetMapping

        GetMapping은 Method가 Get으로 설정되어 있기 때문에 path 만 넣어주면 된다.
* [Spring](https://docs.spring.io/spring-framework/docs/current/reference/html/overview.html#overview)(링크된 문서에서 핵심을 캐치할 것, 괴롭지만 한 번은 해내야 함).

앞서 진행했던 소켓 프로그래밍을 통해 알 수 있듯이 스프링도 내부적으로는 소켓을 연결해서 HTTP Message를 주고 받으며 동작하는 원리로 작동된다.
