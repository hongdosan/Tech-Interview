<!--
<details>
  <summary><h3></h3></summary>

  ---

  <details>
    <summary></summary>
  </details>
</details> 
-->

<details>
  <summary><h3>1. 서블릿(Servlet)이란?</h3></summary>

  서블릿은 서버 측에서 실행되어 클라이언트의 요청을 처리하고 그 결과를 반환하는 Java 클래스입니다. 웹 서버(WS) 내에서 동작하며, 동적인 웹 페이지나 웹 애플리케이션을 생성하는데 사용됩니다. 

  ---
  
  <details>
    <summary>서블릿 컨테이너란?</summary>
    
    서블릿 컨테이너는 서블릿의 생명주기를 관리하는 컴포넌트입니다. 서블릿의 생성, 초기화, 호출, 소멸 등의 과정을 관리하며, 요청과 응답 객체를 생성하여 서블릿에 전달합니다.
  </details>  
  <details>
    <summary>서블릿 동작과정에 대해 설명해주세요.</summary>
    
    1. 사용자가 URL을 통해 요청을 보내면, 웹 서버는 이 요청을 서블릿 컨테이너에 전달합니다. 
    2. 서블릿 컨테이너는 요청을 처리할 서블릿을 찾아 실행합니다.
    3. 서블릿은 요청을 처리한 후 응답을 생성합니다.
    4. 서블릿 컨테이너는 이 응답을 웹 서버에 전달하고, 웹 서버는 이를 사용자에게 반환합니다.
  </details>  
  <details>
    <summary>서블릿의 경우 멀티 쓰레드 환경에서 어떻게 동작하는지 알려주세요.</summary>
  </details>
</details>

<details>
  <summary><h3>2. DispatcherServlet 이란?</h3></summary>
    
   DispatcherServlet은 스프링 MVC의 핵심 컴포넌트로, 모든 클라이언트 요청을 최초로 받아들이는 프론트 컨트롤러 역할을 합니다. 
   요청에 따라 적절한 컨트롤러로 분배하고, 처리 결과를 사용자에게 반환하는 역할을 수행합니다.

  ---

  <details>
    <summary>Dispatcher Servlet의 동작 과정에 대해서 간단하게 설명해주세요.</summary>
  </details>
  <details>
    <summary>여러 요청이 들어온다고 가정할 때, DispatcherServlet은 한번에 여러 요청을 모두 받을 수 있나요?</summary>
    
    DispatcherServlet은 멀티스레드 환경에서 동작하므로 한 번에 여러 요청을 받아 처리할 수 있습니다. 
    각 요청은 별도의 스레드에서 처리되며, 이를 통해 동시에 여러 사용자의 요청을 처리할 수 있습니다.
  </details>  
  <details>
    <summary>수많은 @Controller 를 DispatcherServlet은 어떻게 구분 할까요?</summary>
    
    DispatcherServlet은 요청 URL을 분석하여 해당 요청을 처리할 @Controller를 결정합니다. 
    이는 스프링의 HandlerMapping이 수행하며, URL, HTTP 메서드, 요청 파라미터 등을 기반으로 적절한 컨트롤러를 찾습니다.
  </details>  
</details>

<details>
  <summary><h3>3. Tomcat이 정확히 어떤 역할을 하는 도구인가요?</h3></summary>

   Tomcat은 자바 서블릿 컨테이너와 웹 서버의 기능을 제공하는 오픈소스 소프트웨어입니다. 웹 서버로서의 역할로는 정적인 페이지를 사용자에게 제공하고, 서블릿 컨테이너로서의 역할로는 JSP(Java Server Pages)와 서블릿의 실행 환경을 제공합니다. 즉, 클라이언트의 요청을 받아 해당하는 동적 컨텐츠를 생성하고 응답을 반환하는 역할을 합니다.

  ---

  <details>
    <summary>내장 톰캣과 외장 톰캣은 어떤식으로 구성되어 활용되나요?</summary>
  </details>
  <details>
    <summary>내장 톰캣과 외장 톰캣의 차이점에 대해서 아는대로 설명해주세요.</summary>
  </details>
  <details>
    <summary>혹시 Netty에 대해 들어보셨나요? 무엇인가요?</summary>
    
    Netty는 자바 네트워크 프로그래밍 라이브러리로, 비동기 이벤트 주도 네트워크 애플리케이션을 쉽게 개발할 수 있게 설계되었습니다.
    Netty를 사용하면 TCP/UDP 소켓 서버와 클라이언트, HTTP/HTTPS 서버와 클라이언트 등을 쉽게 구현할 수 있습니다. 
    또한, 네트워크 프로그래밍에서 발생할 수 있는 다양한 이슈들(예: 접속 수락, 메시지 읽기/쓰기, 에러 처리 등)을 효율적으로 처리할 수 있습니다.
  </details>
  <details>
    <summary>왜 Netty란 것을 사용할까요?</summary>

    1. 효율적인 리소스 관리: Netty는 비동기 이벤트 주도 모델을 사용하여 리소스를 효율적으로 관리하여 높은 동시 접속 처리 성능을 제공합니다.
    2. 쉬운 프로그래밍 모델: 복잡한 네트워크 프로그래밍을 보다 쉽게 구현할 수 있도록 도와줍니다.
    3. 높은 확장성: 다양한 프로토콜을 지원하며, 사용자가 직접 프로토콜을 구현할 수 있도록 지원합니다.
  </details>
</details>

<details>
  <summary><h3>4. 필터(Filter)란?</h3></summary>

  필터는 클라이언트의 요청을 서블릿이나 JSP로 보내기 전에 특정 작업을 처리하거나, 서블릿이나 JSP의 응답을 클라이언트로 보내기 전에 특정 작업을 처리하는데 사용됩니다. 예를 들어 인코딩, 로깅, 압축, 암호화 등의 작업을 필터를 통해 처리할 수 있습니다. 

  ---

  <details>
    <summary>필터는 어떤 상황에 사용해야 할까요?</summary>

    필터는 주로 다음과 같은 상황에서 사용됩니다 :
    - 요청/응답 데이터의 변환 또는 가공: 예를 들어, 인코딩 변경, XSS 공격 방어 등 
    - 공통적인 요청 처리: 예를 들어, 사용자 인증, 세션 체크 등 
    - 로깅 및 감사 추적: 예를 들어, 요청 경로, 처리 시간, IP 주소 등의 정보를 로그로 남기는 경우 
  </details>
  <details>
    <summary>Spring에서 Interceptor와 Servlet Filter와 AOP 공통점, 차이점에 대해 설명해 주세요.</summary>

    공통점:
      - 모두 요청을 가로채어 특정 로직을 수행하는 역할을 합니다. 
    차이점: 
      - Servlet Filter: 서블릿 명세의 일부로서, 서블릿 실행 전후에 요청과 응답을 변환하는 역할을 담당합니다. 
      - Interceptor: 스프링 프레임워크에서 제공하는 기능으로서, DispatcherServlet이 컨트롤러를 호출하기 전후로 특정 작업을 수행할 수 있습니다. 
      - AOP(Aspect Oriented Programming): 관점 지향 프로그래밍으로, 횡단 관심사(cross-cutting concerns)를 분리하여 모듈화하는 프로그래밍 패러다임입니다.
  </details>  
  <details>
    <summary>Spring에서 Interceptor와 Servlet Filter 차이점에 대해 설명해 주세요.</summary>

    1. 작동 시점 
      - 필터: 스프링의 디스패처 서블릿이 작동하기 전에 요청을 가로챕니다. 
             따라서 필터는 스프링의 컨텍스트 외부에서 작동하며, 스프링과 관련이 없는 웹 리소스에 대해서도 작동합니다. 
      - 인터셉터: 스프링의 디스패처 서블릿이 컨트롤러를 호출하기 전과 후에 요청을 가로챕니다. 
                따라서 인터셉터는 스프링의 컨텍스트 내부에서 작동하며, 스프링 MVC의 컨트롤러에 대해서만 작동합니다. 
    2. 접근 가능한 객체
      - 필터: HttpServletRequest와 HttpServletResponse 객체에만 접근할 수 있습니다. 
      - 인터셉터: HttpServletRequest와 HttpServletResponse 뿐만 아니라, 컨트롤러와 뷰에 대한 추가적인 정보를 담고 있는 Handler 객체에 접근할 수 있습니다. 
                이를 통해 특정 컨트롤러에 대한 요청인지를 판단하거나, 컨트롤러의 실행 여부를 결정하는 등의 로직을 구현할 수 있습니다. 
    3. 사용 목적
      - 필터: 인코딩, CORS 설정, 로깅 등의 공통적인 웹 처리를 위해 사용됩니다. 
      - 인터셉터: 인증, 권한 체크, 세션 체크 등의 스프링 MVC와 관련된 처리를 위해 사용됩니다.
      
    - 결론: 요구 사항에 따라 필터와 인터셉터를 적절히 사용하면 됩니다. 
           필터는 보다 일반적인 웹 처리를 위한 것이며, 인터셉터는 스프링 MVC의 특정 컨트롤러에 대한 요청을 처리하는 데 더 적합합니다.
  </details>  
  <details>
    <summary>필터와 인터셉터 차이만 보면, 인터셉터만 쓰는게 나아보이는데, 아닌가요?</summary>

    아니라고 생각합니다. 필터와 인터셉터는 각각의 용도에 따라 선택적으로 사용됩니다. 
    필터는 서블릿 수준에서 작동하므로 스프링 컨텍스트를 벗어난 모든 요청에 대해 적용할 수 있습니다. 
    반면에 인터셉터는 스프링의 디스패처 서블릿이 컨트롤러를 호출하기 전후에 작동하기 때문에 스프링 MVC의 컨트롤러에만 적용할 수 있습니다.
    따라서 요구 사항에 따라 적절한 것을 선택하여 사용하면 됩니다.
  </details>
  <details>
    <summary>필터에서 사용되는 Request와 서블릿에서 사용되는 Request가 어떤 점이 다른지? 2개의 Request에 대한 차이를 설명해주세요.</summary>
  </details>
  <details>
    <summary>필터를 사용해본 경험이 있으면 말씀해주시고, 필터에서 예외 처리를 해본 경험이 있는지 있다면 어떻게 할 수 있는지 말씀해주세요.</summary>
  </details>
</details>

<details>
  <summary><h3>5. AOP에 대해 설명해 주세요.</h3></summary>

  ---

  <details>
    <summary>@Aspect는 어떻게 동작하나요?</summary>
  </details>  
</details>

<details>
  <summary><h3>6. 스프링(Spring)이란?</h3></summary>

  스프링은 자바 플랫폼을 위한 오픈 소스 애플리케이션 프레임워크입니다. 
  엔터프라이즈 수준의 애플리케이션을 구축하는 데 필요한 모든 기능을 종합적으로 제공하며, 특히 엔터프라이즈 애플리케이션 개발의 복잡함을 줄이고 개발자가 비즈니스 로직에 집중할 수 있도록 지원합니다.
  스프링의 핵심 기능 중 하나는 제어 역전(Inversion of Control, IoC)입니다. IoC는 객체의 생성과 생명주기 관리를 개발자가 아닌 프레임워크가 담당하며, 이를 통해 개발자는 비즈니스 로직 구현에만 집중할 수 있습니다.

  ---

  <details>
    <summary>스프링과 스프링 부트(Spring Boot)는 차이점이 뭔가요?</summary>

    스프링 부트는 스프링 프레임워크를 기반으로 하되, 스프링보다 애플리케이션을 더 쉽게 설정하고 실행할 수 있게하여 비즈니스 로직에 더 집중할 수 있도록 도와주는 도구입니다.
    
    스프링 부트의 주요 특징은 다음과 같습니다:
      - 자동 설정(Auto Configuration): 스프링 부트는 애플리케이션에 필요한 라이브러리와 설정을 자동으로 제공합니다.
      - 내장 서버 지원: Tomcat, Jetty 등의 웹 서버를 내장하고 있어 별도의 서버 설치 없이 웹 애플리케이션을 실행할 수 있습니다.
      - 독립적인 실행 가능: JAR 파일 하나로 애플리케이션을 실행할 수 있습니다.

    따라서, 스프링 부트는 스프링 프레임워크의 기능을 그대로 활용하면서, 복잡한 설정 없이도 빠르게 애플리케이션을 구축하고 실행할 수 있는 환경을 제공합니다.
  </details>
  <details>
    <summary>본인이 생각할 때 스프링과 스프링부트는 각각 어느때 사용할 것 같은지 설명해주세요.</summary>
  </details>
</details>  

<details>
  <summary><h3>7. MVC패턴이란?</h3></summary>

  ---

  <details>
    <summary>MVC1이랑 MVC2 패턴 차이에 대해 설명해주세요.</summary>
  </details>
  <details>
    <summary>스프링 MVC 구조 흐름에 대해 과정대로 설명해보세요.</summary>
  </details>
</details> 

<details>
  <summary><h3>8. IoC와 DI에 대해 설명해 주세요.</h3></summary>

  ---
  
  - 후보 없이 특정 기능을 하는 클래스가 딱 1개이면, 구체 클래스를 그냥 사용해도 되지 않을까요? 근데, 왜 Spring에선 Bean을 사용 할까요?
  - Spring의 Bean 생성 주기에 대해 설명해 주세요.
  - 프로토타입 빈은 무엇인가요?
</details>

<details>
  <summary><h3>9. JPA와 같은 ORM을 사용하는 이유가 무엇인가요?</h3></summary>

  ---
  
  - 영속성은 어떤 기능을 하나요? 이게 진짜 성능 향상에 큰 도움이 되나요?
  - N + 1 문제에 대해 설명해 주세요.
</details>

<details>
  <summary><h3>10. @Transactional 은 어떤 기능을 하나요?</h3></summary>

  ---
  
  - @Transactional(readonly=true) 는 어떤 기능인가요? 이게 도움이 되나요?
  - 그런데, 읽기에 트랜잭션을 걸 필요가 있나요? @Transactional을 안 붙이면 되는거 아닐까요?
</details>
