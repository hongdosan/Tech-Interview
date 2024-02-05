<!--
<details>
  <summary><h3></h3></summary>

  ---

  <details>
    <summary><b></b></summary>
  </details>
</details> 
-->

<details>
  <summary><h3>1. 서블릿(Servlet)이란?</h3></summary>

  서블릿은 서버 측에서 실행되어 클라이언트의 요청을 처리하고 그 결과를 반환하는 Java 클래스입니다. 웹 서버(WS) 내에서 동작하며, 동적인 웹 페이지나 웹 애플리케이션을 생성하는데 사용됩니다. 

  ---
  
  <details>
    <summary><b>서블릿 컨테이너란?</b></summary>
    서블릿 컨테이너는 서블릿의 생명주기를 관리하는 컴포넌트입니다. 서블릿의 생성, 초기화, 호출, 소멸 등의 과정을 관리하며, 요청과 응답 객체를 생성하여 서블릿에 전달합니다.
  </details>  
  <details>
    <summary><b>서블릿 동작과정에 대해 설명해주세요.</b></summary>
    1. 사용자가 URL을 통해 요청을 보내면, 웹 서버는 이 요청을 서블릿 컨테이너에 전달합니다. 
    2. 서블릿 컨테이너는 요청을 처리할 서블릿을 찾아 실행합니다.
    3. 서블릿은 요청을 처리한 후 응답을 생성합니다.
    4. 서블릿 컨테이너는 이 응답을 웹 서버에 전달하고, 웹 서버는 이를 사용자에게 반환합니다.
  </details>  
  <details>
    <summary><b>DispatcherServlet 의 역할에 대해 설명해 주세요.</b></summary>
     DispatcherServlet은 스프링 MVC의 핵심 컴포넌트로, 모든 클라이언트 요청을 최초로 받아들이는 프론트 컨트롤러 역할을 합니다. 요청에 따라 적절한 컨트롤러로 분배하고, 처리 결과를 사용자에게 반환하는 역할을 수행합니다.
  </details>
  <details>
    <summary><b>여러 요청이 들어온다고 가정할 때, DispatcherServlet은 한번에 여러 요청을 모두 받을 수 있나요?</b></summary>
    DispatcherServlet은 멀티스레드 환경에서 동작하므로 한 번에 여러 요청을 받아 처리할 수 있습니다. 각 요청은 별도의 스레드에서 처리되며, 이를 통해 동시에 여러 사용자의 요청을 처리할 수 있습니다.
  </details>  
  <details>
    <summary><b>수많은 @Controller 를 DispatcherServlet은 어떻게 구분 할까요?</b></summary>
    DispatcherServlet은 요청 URL을 분석하여 해당 요청을 처리할 @Controller를 결정합니다. 이는 스프링의 HandlerMapping이 수행하며, URL, HTTP 메서드, 요청 파라미터 등을 기반으로 적절한 컨트롤러를 찾습니다.
  </details>  
</details>

<details>
  <summary><h3>2. Tomcat이 정확히 어떤 역할을 하는 도구인가요?</h3></summary>

  ---
  
  <details>
    <summary>혹시 Netty에 대해 들어보셨나요? 왜 이런 것을 사용할까요?</summary>
  </details>
</details>

<details>
  <summary><h3>3. 필터란?</h3></summary>

  ---

  <details>
    <summary>필터는 어떤 상황에 사용해야 할까요?</summary>
  </details>
  <details>
    <summary>Spring에서 Interceptor와 Servlet Filter와 AOP 공통점, 차이점에 대해 설명해 주세요.</summary>
  </details>  
  <details>
    <summary>필터와 인터셉터 차이만 보면, 인터셉터만 쓰는게 나아보이는데, 아닌가요?</summary>
  </details>  
</details>

<details>
  <summary><h3>4. AOP에 대해 설명해 주세요.</h3></summary>

  ---

  <details>
    <summary>@Aspect는 어떻게 동작하나요?</summary>
  </details>  
</details>

<details>
  <summary><h3>5. 스프링이란?</h3></summary>

  ---

  <details>
    <summary>스프링과 스프링 부트는 차이점이 뭔가요?</summary>
  </details>
</details>  

<details>
  <summary><h3>6. MVC패턴이란?</h3></summary>

  ---

  <details>
    <summary>MVC1이랑 MVC2 패턴 차이에 대해 설명해주세요.</summary>
  </details>
  <details>
    <summary>스프링 MVC 구조 흐름에 대해 과정대로 설명해보세요.</summary>
  </details>
</details> 

<details>
  <summary><h3>7. IoC와 DI에 대해 설명해 주세요.</h3></summary>

  ---
  
  - 후보 없이 특정 기능을 하는 클래스가 딱 1개이면, 구체 클래스를 그냥 사용해도 되지 않을까요? 근데, 왜 Spring에선 Bean을 사용 할까요?
  - Spring의 Bean 생성 주기에 대해 설명해 주세요.
  - 프로토타입 빈은 무엇인가요?
</details>

<details>
  <summary><h3>8. JPA와 같은 ORM을 사용하는 이유가 무엇인가요?</h3></summary>

  ---
  
  - 영속성은 어떤 기능을 하나요? 이게 진짜 성능 향상에 큰 도움이 되나요?
  - N + 1 문제에 대해 설명해 주세요.
</details>

<details>
  <summary><h3>9. @Transactional 은 어떤 기능을 하나요?</h3></summary>

  ---
  
  - @Transactional(readonly=true) 는 어떤 기능인가요? 이게 도움이 되나요?
  - 그런데, 읽기에 트랜잭션을 걸 필요가 있나요? @Transactional을 안 붙이면 되는거 아닐까요?
</details>
