<!--
<details>
  <summary><b></b></summary>

  ---

  <details>
    <summary></summary>
  </details>
</details> 
-->

## 서블릿

<details>
  <summary><b>서블릿(Servlet)에 대해 설명하세요.</b></summary>
  
  - 클라이언트의 요청을 처리하고, 그 결과를 반환하는 Servlet 클래스의 구현 규칙을 지킨 자바 웹 프로그래밍 기술입니다.
    - 클라이언트의 요청에 대해 동적으로 작동하는 웹 어플리케이션 컴포넌트입니다.
    - 요청/응답을 일일히 처리하지 않고 서블릿을 통해 웹 요청과 응답의 흐름을 간단한 메서드 호출만으로 다룰 수 있게 합니다.
    - MVC 패턴에서 Controller로 이용됩니다.
  
  ---
  
  <details>
    <summary>서블릿 생명주기에 대해 설명해주세요.</summary>

    - init():
      - 클라이언트의 요청이 들어오면 컨테이너는 해당 서블릿이 메모리에 올라와있는지 확인하고, 없을 경우 init() 메서드를 통해 메모리에 적재합니다.
      - 처음 한 번만 실행되고 서블릿의 모든 쓰레드에서 공통적으로 사용해야 한다면 오버라이딩해서 구현하면 됩니다.
    - service():
      - 클라이언트의 요청이 들어왔을 때, service() 메서드를 통해 요청에 대한 응답이 doGet()과 doPost()로 나뉘며 
        HttpServletRequest와 HttpServletResponse 객체가 제공됩니다.
      - 실질적으로 요청에 대한 처리를 수행하는 곳입니다.
    - destroy():
      - 컨테이너가 서블릿에 종료 요청을 하면 발생되는 메서드로, 서블릿의 처리가 모두 끝났을 때 발생합니다.
  </details>
  <details>
    <summary>서블릿의 경우 멀티 쓰레드 환경에서 어떻게 동작하는지 알려주세요.</summary>

    - 우선 서블릿은 WAS가 실행되면 싱글톤으로 1개만 생성됩니다.
    - 싱글톤으로 생성된 특정 서블릿에 대한 요청이 한 번에 10개가 발생했다고 가정한다면,
      요청 하나당 쓰레드 하나가 쓰레드 풀에서 할당되고 10개의 요청은 모두 쓰레드를 할당받아 특정 서블릿의 service()를 요청합니다.
    - 결국 동시에 여러 클라이언트의 요청을 처리할 수 있기 때문에, 서블릿에서 전역 변수를 사용하거나, 상태를 변경하는 등의
      작업을 여러 쓰레드에서 동시에 처리하면, 데이터 불일치나 에기치 않은 결과를 초래할 수 있습니다.
    - 따라서, 가급적이면 인스턴스 변수를 사용하지 않고 쓰레드마다 지역변수를 이용하거나, synchronized 키워드를 이용해
      특정 코드 블록이 한 번에 하나의 쓰레드만 실행할 수 있도록 제한해야 합니다.
  </details>  
  <details>
    <summary>서블릿 컨테이너(Servlet Container)란?</summary>
  
    - 서블릿을 관리해주는 컨테이너로 클라이언트의 요청을 받고 응답할 수 있게, 웹 서버와 소켓으로 통신하는 역할을 합니다.
    - 즉, Tomcat처럼 서블릿을 지원하는 WAS입니다.
  </details>
  <details>
    <summary>서블릿 컨테이너의 역할에 대해 설명해주세요.</summary>

    1. 웹서버와 통신지원을 합니다.
      - 서블릿과 웹서버가 손쉽게 통신할 수 있게 합니다.
      - 보통 소켓을 만들고 listen, accept를 해야하는데, 서블릿 컨테이너는 이런 기능을 API로 제공하여 복잡한 과정이 생략됩니다.
    2. 서블릿 생명주기를 관리합니다.
      - 서블릿의 탄생부터 죽음을 관리합니다.
      - 서블릿 클래스를 로딩하여 인스턴스화하고 초기화 메서드를 호출하고 요청이 들어오면 적절한 서블릿 메서드를 호출합니다.
    3. 멀티 쓰레드를 지원 및 관리합니다. 
      - 서블릿 컨테이너는 요청이 들어올 때마다 새로운 자바 쓰레드를 생성합니다.
      - 이를 통해 여러 사용자의 요청을 동시에 처리할 수 있습니다.
  </details>

  ---
  
</details> 

<details>
  <summary><b>Tomcat이란 무엇인가요?</b></summary>

   - 웹 서버(WS)와 웹 컨테이너(=서블릿 컨테이너)의 결합인 웹 애플리케이션 서버(WAS)입니다.
     - 보통 Apache Tomcat이라 하는데, Tomcat에서 편의를 위해 Apache 기능을 포함해 Tomcat이라 부릅니다.
     - Apache : 정적인 데이터를 처리하는 웹 서버
     - Tomcat : 동적인 데이터를 처리하는 웹 애플리케이션 서버
     - WS : 정적 콘텐츠를 제공하는 서버입니다. (HTML, CSS, 이미지 등)
     - WAS : 동적인 데이터를 처리하는 서버입니다. (DB 연결 및 데이터 조작 등의 처리를 담당)

  ---

  <details>
    <summary>내장 톰캣과 외장 톰캣이 어떤 식으로 활용되는 지, 차이점에 대해서 아는대로 설명해주세요.</summary>

    주로 톰캣은 스프링 프레임워크를 사용할 때 이용합니다.
    예를 들어, 기본 스프링을 이용할 땐 외장 톰캣을 이용하고 스프링부트를 사용할 때는 내장 톰캣을 이용합니다.
    즉, 프레임워크 밖에서 동작하면, 외장 톰캣, 프레임워크 안에서 동작하면 내장 톰캣을 이용한다고 보면 됩니다.
    내장 톰캣은 웹 어플리케이션을 빌드하고 실행하는 것만으로 웹 애플리케이션을 실행할 수 있습니다. 즉, Jar 파일 형태로 손쉽게 배포가 가능합니다.
    반면 외장 톰캣은 톰캣을 직접 설치하여 스프링과 통신할 수 있도록 복잡한 설정을 해야 합니다.

    1. 내장 톰캣
      - Springboot 안에는 Tomcat이 내장
      - 애플리케이션을 빌드하고 실행하는 것만으로 웹 애플리케이션을 서비스할 수 있다.
    2. 외장 톰캣
      - Spring을 사용하는 경우 Tomcat을 설치하여 스프링과 통신할 수 있도록 설정해야 한다.
      - 복잡한 대신 Virtual Host라는 기능을 사용할 수 있다.
        - 도메인 호스트에 따라 다른 Root Context를 적용해 하나의 웹 어플리케이션에서도 마치 여러 애플리케이션을 사용하는 것처럼 주소 설정 가능
        - 내장 톰캣도 가능하긴 하지만 매우 복잡하기 때문에, 웹 서버를 별도로 두고 하나의 웹 애플리케이션은 하나의 내장 WAS를 갖는 것이 더 효율적
  </details>
  <details>
    <summary>Tomcat 동작과정에 대해 설명해주세요.</summary>
    
    1. 클라이언트가 요청을 하면 웹 서버에서 톰캣과 같은 WAS에 위임합니다.
    2. 서블릿 컨테이너가 HttpServletRequest, HttpServletResponse(빈객체) 객체를 생성합니다.
    3. web.xml을 기반으로 해당 URL이 어떤 서블릿에 대한 요청인지 찾습니다.
    4. 해당 서블릿이 최초 요청이면 init()를 통해 메모리에 로드하고 아니라면 기존 서블릿 인스턴스를 가져옵니다.
    5. 가져온 서블릿에서 service()를 호출 후 doGet() 또는 doPost()를 호출합니다.
    6. doGet() 혹은 doPost()가 동적 페이지를 생성해 HttpServletResponse 객체에 응답을 보냅니다.
    7. 응답이 끝나면 HttpServletRequest와 HttpServletResponse 객체를 소멸시킵니다.
  </details>
  <details>
    <summary>Spring 환경에서 tomcat 에 request 가 들어왔을 때 RequestMapping 에 도달하기까지 과정을 설명해주세요.</summary>

    1) 톰캣이 HttpServletRequest와 HttpServletResponse 객체를 생성합니다.
    2) 스프링이 DispatcherServlet에 이 두 객체를 전달합니다. 
    3) DispatcherServlet은 HandlerMapping에게 이 요청을 처리할 Handler(컨트롤러)를 물어봅니다. 
    4) HandlerMapping은 요청의 URI, HTTP 메서드 등을 기준으로 Handler를 찾아 DispatcherServlet에 반환합니다.
    5) DispatcherServlet은 반환받은 Handler(@RequestMapping이 붙은 컨트롤러의 메서드)를 실행합니다.
  </details>
  
  ---
  
</details>

<details>
  <summary><b>필터(Filter)란?</b></summary>

  - 서블릿으로 전달되는 클라이언트의 요청 혹은 서블릿에서 클라이언트로 전달되는 응답을 중간에 가로채 필터링을 위한 객체와 메서드를 정의해둔 인터페이스입니다.

  ---

  <details>
    <summary>Filter 메서드에 대해 설명해주세요.</summary>

    - init(FilterConfig): 
      - 필터 인스턴스 초기화를 위해 호출하는 메서드
      - 필터가 생성되고 난 후 한 번만 호출됩니다. 
    - doFilter(ServletRequest, ServletResponse, FilterChain):
      - 실제 필터의 로직을 수행하는 메서드입니다.
      - 클라이언트의 요청이 있을 때마다 호출됩니다.
      - 작업이 끝나면 FilterChain의 doFilter 메서드를 호출하여 다음 필터나 서블릿에게 요청과 응답을 전달합니다.
    - destroy():
      - 필터 인스턴스를 종료시키기 전에 호출하는 메서드입니다.
      - 이 메서드에서는 필터의 리소스를 해제하거나 종료에 필요한 작업을 수행합니다.
    
    이처럼 필터는 요청과 응답을 가공하거나 특정 작업을 수행하는 데 사용되며, 
    init, doFilter, destroy 세 가지 메서드를 통해 필터의 생명 주기를 관리합니다.    
  </details>
  <details>
    <summary>필터에서 사용되는 요청과 서블릿에서 사용되는 요청의 차이를 설명하세요.</summary>

    - 필터는 ServletRequest 사용되고 서블릿은 HttpServletRequest가 사용됩니다.
    - 서블릿의 HttpServletRequest는 필터의 ServletRequest의 기능을 상속받아
      추가적으로 Http 프로토콜 관련 기능들을 추가적으로 제공하는 인터페이스입니다.
  </details>
  <details>
    <summary>필터를 사용해본 경험이 있나요? 있다면 필터에서 예외 처리를 해봤나요? 없다면 어떻게 할 것 같은가요?</summary>

    이 답변은 개인적으로 준비하는 것이 좋을 것 같습니다.
  </details>
  
  ---
  
</details>

## 스프링 기본

<details>
  <summary><b>Spring과 SpringBoot 차이에 대해 설명하세요.</b></summary>

  - Spring Boot는 WAS 서버를 내장하고 있어, Jar 파일로 배포가 용이합니다. <br/>
    또한 의존성을 관리해주기 때문에 손쉽게 사용이 가능합니다.
    예를 들어, Spring MVC, Spring Data JPA, Spring Security 등을 자동으로 설정해 개발자가 별도로 설정 파일을 작성하지 않아도 됩니다.
  - 반면 Spring은 굉장히 많은 설정을 해줘야 합니다. <br/>
    예를 들어, 웹 서버로 만들 때는 외부의 WAS 서버를 이용해 처리해야 합니다. <br/>

  ---

  <details>
    <summary>본인이 생각할 때 스프링과 스프링부트는 각각 언제 사용할 것 같나요?</summary>

    우선 스프링은 많은 설정을 개발자가 직접해야 해서 복잡하지만, 오히려 섬세한 설정을 할 수 있기 때문에,
    스프링 프레임워크에 대한 이해가 깊다면, 세밀한 설정이 필요할 때 사용할 것 같습니다.
    반대로 스프링부트는 개발 시간을 최소화해야하는 경우 사용할 것 같습니다.
  </details>
  
  ---
  
</details>

<details>
  <summary><b>Spring MVC(Model-View-Controller) 란?</b></summary>

  - Spring MVC는 Dispatcher Servlet, ModelAndVidew, View Resolver와 같은 간단한 개념으로 <br/>
    웹 애플리케이션을 개발할 수 있도록 돕는 프레임워크입니다.
  
  ---

  <details>
    <summary>MVC 패턴이란?</summary>

    MVC 패턴은 애플리케이션을 세 가지 역할로 구분한 개발 방법론입니다. 
      - Model: 애플리케이션의 정보, 데이터를 나타내며, 비즈니스 로직을 처리합니다.
      - View: 사용자에게 보여지는 화면입니다. Model이 처리한 데이터를 사용자에게 보여주는 역할을 합니다.
      - Controller: 사용자의 입력을 받아 Model에 작업을 지시하고, 그 결과를 View에 반영하여 사용자에게 전달하는 역할을 합니다.
  </details>
  <details>
    <summary>Spring MVC1, Spring MVC2 패턴 차이에 대해 설명해주세요.</summary>

    - Spring MVC1: 
      - View와 Controller를 JSP가 모두 담당하는 형태를 의미합니다.
      - JSP에 모든 정보가 담겨 있기 때문에, 읽기가 힘들고 유지보수성이 떨어집니다.
    - Spring MVC2: 
      - 요청을 하나의 Controller(Servlet)가 먼저 받아 View와 Model의 중간 역할을 하는 형태입니다.
      - 예를 들어, 스프링에서는 Dispatcher Servlet이 프론트 컨트롤러 역할을 맡아 요청에 맞는 컨트롤러를 찾아 요청을 위임합니다.
      - 때문에 Spring MVC1보다 역할이 명확하게 분리되어, 유지보수성 및 확장성이 용이합니다.
  </details>
  
  ---
  
</details>

<details>
  <summary><b>DispatcherServlet 이란?</b></summary>
    
   - Http 프로토콜로 들어오는 모든 클라이언트 요청을 최초로 받아 적합한 컨트롤러에 위임해주는 프론트 컨트롤러입니다.
     - 프론트 컨트롤러란 서블릿 컨테이너의 제일 앞에서 서버로 들어오는 클라이언트의 모든 요청을 받아 처리해주는 컨트롤러입니다.
     - web.xml에 맵핑되는 컨트롤러를 모두 등록해야 하던 것을, Dispatcher Servlet을 통해 모든 요청을 핸들링하고 공통 작업을 처리해주면서 web.xml의 역할이 축소되었습니다.

  ---

  <details>
    <summary>Dispatcher Servlet의 동작 과정에 대해서 설명해주세요.</summary>

    1. 첫 번째로, 클라이언트 요청이 들어오면 웹 컨텍스트를 지나 스프링 컨텍스트에 있는 Dispatcher Servlet이 가장 먼저 요청을 받습니다.
    2. Dispatcher Servlet은 사용자가 요청한 URL을 기반으로 HandlerMapping을 통해 어떤 컨트롤러로 요청을 위임할 지 찾습니다.
    3. 찾았다면 HandlerExecutionChain으로 감싸서 반환합니다.
      - 컨트롤러로 요청을 넘기기 전 처리해야하는 인터셉터 등을 포함하기 위해 감싸서 반환합니다.
    4. 반환된 값을 기반으로 HandlerAdapter를 통해 컨트롤러로 요청을 위임합니다.
      - HandlerAdapter에서는 컨트롤러로 요청을 위임하기 전/후에 Interceptor와 @RequestParam, @RequestBody 등을 처리하기 위한
        ArgumentResolver들과 직렬화와 같은 기능을 처리하게 됩니다.
    5. 요청을 위임받은 컨트롤러가 비지니스 로직을 수행 후 응답합니다.
      - 웹 페이지를 사용할 경우 View Name을 String으로 반환합니다.
      - 응답 데이터를 JSON으로 반환할 경우 주로 ResponseEntity를 반환하게 됩니다.
      - HandlerAdapter에서 반환된 값을 파악해 해당하는 것에 맞는 Converter를 이용하여 클라이언트로 반환합니다.
  </details>

  <details>
    <summary>여러 요청이 들어온다고 가정할 때, DispatcherServlet은 한번에 여러 요청을 모두 받을 수 있나요?</summary>
    
    - DispatcherServlet은 멀티스레드 환경에서 동작하므로 한 번에 여러 요청을 받아 처리할 수 있습니다.
    - 각 요청은 별도의 스레드에서 처리되며, 이를 통해 동시에 여러 사용자의 요청을 처리할 수 있습니다.
    
  </details>    
  <details>
    <summary>수많은 Controller 를 DispatcherServlet은 어떻게 구분 할까요?</summary>
    
    - DispatcherServlet은 요청 URL을 분석하여 해당 요청을 처리할 Controller를 결정합니다.
    - 스프링에서는 HandlerMapping이 @Controller 어노테이션이 적용된 모든 컨트롤러를 찾아 파싱하여 HashMap<요청 정보, 처리할 대상>으로 관리합니다.
  </details>
  <details>
    <summary>HandlerMapping, HandlerAdapter, HandlerInterceptor, ViewResolver 용어에 대해 설명해주세요.</summary>

    HandlerMapping
      - 요청을 처리할 컨트롤러를 찾아주는 역할을 합니다.
      - 요청 URL, HTTP Method 등을 기준으로 적절한 핸들러를 찾아 DispatcherServlet에게 반환합니다.
    HandlerAdapter
      - 요청을 컨트롤러로 위임하기 위한 어댑터입니다.
      - DispatcherServlet은 이를 이용해 각각의 핸들러 타입에 맞는 방식으로 요청을 처리합니다.
    HandlerInterceptor
      - 핸들러의 처리 전/후에 특정 작업을 수행할 수 있게 해주는 역할을 합니다.
    ViewResolver
      - 뷰를 반환하기 위한 리졸버입니다.
  </details>
  
  ---
  
</details>

<details>
  <summary><b>IoC(Inversion of Control)에 대해 설명해 주세요.</b></summary>

  - IoC는 제어의 역전이라해서, 개발자가 아닌 다른 곳, 프레임워크 같은 곳에 제어권을 맡기는 것을 의미합니다.
  - 예를 들어, 스프링의 경우 빈의 생성과 의존성 주입 등 여러가지 일을 스프링 컨테이너에서 하게 되는데, <br/>
    이것을 개발자가 관리하지 않고 프레임워크에서 한다고 하여 제어의 역전이라고 부릅니다.

  <details>
    <summary>IoC 컨테이너(Spring 컨테이너)란 무엇인가요?</summary>

    - 빈의 생명주기를 관리하고 의존성 주입과 같은 DI 역할을 도와주는 컨테이너입니다. 
    - 즉, Bean 객체를 담는 공간이라 볼 수 있는 곳으로 Bean 객체의 생명주기를 관리하고 생성된 객체에게 추가적인 기능을 제공합니다.
    - 스프링에서는 BeanFactory, ApplicationContext, DI Container라고도 불립니다.
  </details>
  <details>
    <summary>IoC 컨테이너 동작과정에 대해 설명해주세요.</summary>

    - XML 혹은 어노테이션 등의 Bean 설정을 읽어 Bean을 생성하고 Bean 간의 의존성을 주입합니다.
  </details>

  <details>
    <summary>BeanFactory과 ApplicationContext 차이에 대해 설명해주세요.</summary>

    BeanFactory와 ApplicationContext는 스프링에서 제공하는 IoC Container입니다.
    이들은 빈의 생명주기를 관리하고 의존성 주입과 같은 DI 역할을 도와주는 컨테이너입니다.

    그 중 BeanFactory는 컨테이너의 최상위 인터페이스로 스프링 빈을 관리하고 조회하는 역할을 합니다. 
    그리고 ApplicationContext는 BeanFactory를 상속받은 인터페이스로 
    빈 팩토리의 기능을 모두 수행하며 메시지 국제화, 이벤트 발행, 환경 변수와 같은 추가적인 기능을 수행합니다.
  
    - BeanFactory
      - Spring 컨테이너의 최상위 인터페이스로 getBean() 메서드를 제공합니다.
      - 이는 Spring Bean을 관리하고 조회하는 역할을 담당합니다.
    - ApplicationContext
      - BeanFactory의 자식 컨테이너로 BeanFactory보다 더 많은 기능을 수행합니다.
      - 예를 들어, 국제화 기능, 이벤트 발행, 환경 변수와 같은 추가적인 기능을 수행합니다.
  </details>
  
  ---
  
</details>

<details>
  <summary><b>DI(Dependency Injection)에 대해 설명해 주세요.</b></summary>
  
  - 의존 관계를 외부에서 결정하는 것을 의존 관계 주입이라 합니다.
    - 예를 들어, 자바에서 클래스 내 new 키워드로 직접 생성하는 것이 아닌, 외부에서 클래스를 생성할 때 생성자 매개변수로 넣어주는 것을 의미합니다.
  
  ---

  <details>
    <summary>주입 방식에 대해 설명해주세요.</summary>

    1. 필드 주입
      - 장점
        - 사용하기 편리 합니다.
      - 단점
        - 의존성이 외부에서 보이지 않아 의존 관계를 한 눈에 파악하기 힘듭니다.
        - 필드에 직접 주입되기 때문에, 테스트 시 어려움이 있습니다.
    2. 세터 주입 (수정자 주입)
      - 장점
        - 선택적인 의존성을 가질 수 있습니다. 즉, 중간에 수정이 가능합니다.
      - 단점
        - 주입받지 않은 구현체를 사용할 가능성이 있어 NPE 문제가 발생할 수 있습니다.
    3. 생성자 주입 (권장)
      - 장점
        - 의존 관계를 모두 주입해야만 객체 생성이 가능하기 때문에, NPE 문제가 방지됩니다.
        - 객체 생성 시, 모든 의존성이 주입되므로 객체의 불변성을 보장합니다.
        - 순환 참조를 컴파일 단계에서 찾아낼 수 있습니다.
  </details>
  <details>
    <summary>생성자 주입 방식을 사용하는 이유가 있나요?</summary>

    - 생성자 주입 방식을 사용하면, 객체가 생성될 때 모든 의존성이 주입되므로 객체의 불변성을 보장할 수 있습니다. 
    - 또한, 컴파일 단계에서 순환 참조를 방지할 수 있으며, 테스트에도 유리합니다. 이런 이유로 Spring에서는 생성자 주입 방식을 권장하고 있습니다.
  </details>  
  <details>
    <summary>DI를 진행할 때, @Autowired를 사용하는데, 어떤 식으로 의존 관계를 주입하는지 설명하세요.</summary>

    1. 스프링 서버가 실행되면 ApplicationContext가 @Bean 혹은 그 외 어노테이션을 이용해 등록된 스프링 빈을 생성합니다.
    2. 스프링 빈 생성 후, AutowiredAnnotationBeanPostProcessor 클래스의 processInjection() 메서드에서 @Autowired 어노테이션이 붙은 빈을 찾습니다.
    3. 찾은 빈을 객체에 주입할 때 reflection을 이용해 의존성을 주입합니다.
      - reflection : 구체적인 클래스 타입을 몰라도, 해당 클래스의 메서드, 타입, 변수들에 접근할 수 있도록 해주는 자바 API
  </details>
  
  ---
  
</details>

<details>
  <summary><b>@Bean과 @Component 어노테이션 차이에 대해 설명해주세요.</b></summary>

  - @Bean: 
    - 개발자가 컨트롤이 불가능한 외부 라이브러리들을 Bean으로 등록하고 싶을 때, 메서드에 해당 어노테이션을 붙여 사용할 수 있습니다. 단, 클래스에 @Configuration을 붙어야 합니다.
    - 예를 들어, ObjectMapper 클래스는 JSON 처리를 담당하는 외부 라이브러리 클래스이기 때문에, @Component 어노테이션을 붙여 개발자가 직접 수정할 수 없습니다.
    - 하지만, @Bean 어노테이션을 이용해 메서드에서 new 키워드로 ObjectMapper를 생성하고 커스텀하여 반환하면 빈으로 등록할 수 있습니다.
  - @Component: 
    - @Bean과 반대로 직접 컨트롤이 가능한 Bean들을 Spring에서 관리하기 위해 사용하는 어노테이션입니다.
  
  ---

  <details>
    <summary>@Repository, @Service, @Rest/Controller, @Rest/ControllerAdvice 어노테이션 등에 대해 설명하세요.</summary>

    - @Repository
      - 데이터베이스에 접근하는 로직에 사용되는 어노테이션입니다.
      - Hibernate와 같은 영속성 프레임워크를 사용할 경우, 선언된 클래스에서 발생하는 영속성 예외를 스프링의 예외로 자동 전환합니다.
    - @Service
      - 비즈니스 로직이나 Repository를 호출하는 클래스를 컴포넌트로 등록할 때 사용됩니다.
    - @Controller
      - 일반적으로 웹 페이지 요청을 처리하는 클래스를 컴포넌트로 등록할 때 사용됩니다.
      - 보통 메서드가 View 이름을 반환하고 View 이름과 실제 뷰를 연결하는 작업이 필요합니다.
      - @Controller로 작성된 컨트롤러에서 JSON을 반환하려면 메서드에 @ResponseBody를 추가하면 됩니다.
    - @RestController
      - RESTFul 웹 서비스 요청을 처리하는 클래스를 컴포넌트로 등록할 때 사용됩니다.
      - @Controller와 다르게 메서드가 데이터를 반환하고 이 데이터는 HTTP 응답 본문에 직접 쓰여집니다.
      - @RestController는 사실상 @Controller와 @ResponseBody가 결합된 형태입니다.
    - @ControllerAdvice
      - ?
    - @RestControllerAdvice
      - ?
  </details>
  <details>
    <summary>@Component 을 메서드 레벨에 선언할 수 있을까요? 혹은 @Bean 을 클래스 레벨에 선언할 수 있을까요?</summary>

    - 결론부터 말씀드리자면, 둘 경우 모두 선언할 수 없습니다. 
    - @Bean과 @Component 어노테이션은 각각 선언할 수 있는 타입이 정해져 있기 때문에, 해당 용도 외에 사용할 시 컴파일 에러가 발생합니다.
    - 예를 들어 @Bean 같은 경우에는 @Target이 METHOD로 지정되어 있지만, TYPE은 없고,
    - @Component 는 @Target이 TYPE로 지정되어 Class위에서만 선언될수 있음을 알 수 있습니다.
  </details>
  
  ---
  
</details>

<details>
  <summary><b>싱글턴 빈과 프로토타입 빈의 차이에 대해 설명해 주세요.</b></summary>
  
  - 싱글턴 스코프의 스프링 빈은 스프링 컨테이너와 생명주기를 같지만, 프로토타입 스코프의 스프링 빈은 생명주기를 달리합니다.
  - 예를 들어, 싱글톤 스코프의 스프링 빈은 매번 Spring 컨테이너에서 동일한 인스턴스 참조 주소 값을 반환하고 스프링 컨테이너 종료 시, 소멸 메서드도 자동으로 실행됩니다.
  - 하지만 프로토타입 스코프의 스프링 빈은 Spring 컨테이너에 요청할 때마다 새로운 스프링 빈이 생성되고 의존 관계까지 주입 및 초기화 진행 후 반환합니다.
  - 따라서 프로토타입 빈은 싱글턴 빈과는 다르게 소멸 메서드가 호출되지 않아 클라이언트가 프로토타입 빈을 직접 관리해야 합니다.

  <br/>
  
  - singleton: 기본 Scope로, Spring 컨테이너 내에 하나의 Bean 인스턴스만 생성합니다. 
  - prototype: 요청할 때마다 새로운 Bean 인스턴스를 생성합니다. 

  ---
  
  <details>
    <summary>Bean Scope 에 대해서 아시나요?</summary>
  
    Bean Scope는 Spring Bean이 존재할 수 있는 범위를 뜻합니다. 
    기본적으로 Spring 컨테이너에서 스프링 Bean 이 싱글톤 스코프로 생성되기 때문에, Spring 컨테이너와 생명주기가 같아 신경쓸 필요가 없습니다.
    하지만, Bean Scope를 어떻게 설정하느냐에 따라 Spring Bean의 생성과 소멸을 클라이언트에서 관리해야하는 경우도 생길 수 있습니다.
  </details> 
  <details>
    <summary>싱글턴 스코프와 프로토타입 스코프 외의 웹 스코프 종류를 말해보세요.</summary>

    웹 스코프는 웹 환경에서만 동작하는 스코프로 스프링이 웹 스코프의 종료시점까지 관리하며, 종료 메서드도 호출됩니다.

    웹 스코프 종류로는 다음과 같습니다.
    - request: HTTP 요청이 들어오고 나갈 때까지 유지되는 스코프로 각각의 요청마다 별도의 빈 인스턴스가 생성 및 관리됩니다.
    - session: HTTP Session과 동일한 생명주기를 가집니다.
    - application: ServletContext와 동일한 생명주기를 가지는 스코프입니다.
    - websocket: 웹소켓과 동일한 생명주기를 가지는 스코프입니다.
  </details>
  <details>
    <summary>스프링의 디폴트 스코프가 어떤 스코프인지 이유와 함께 설명하세요.</summary>

    - Spring의 기본 Bean Scope는 Singleton Scope입니다. 
    - 이는 Spring이 객체의 생명 주기를 관리하고, 객체 간의 의존성을 관리하는 DI 컨테이너의 특성상, 
    - 대부분의 경우에 하나의 Bean 인스턴스만을 생성하여 재사용하는 것이 효율적이기 때문입니다.
  </details>
  <details>
    <summary>프로토타입 스코프는 언제 사용할까요?</summary>

    - Prototype Scope는 요청할 때마다 새로운 Bean 인스턴스를 생성하므로, 여러 인스턴스를 검색해야 하는 경우 사용할 것 같습니다.
    - 예를 들어, 여러 인스턴스 중 특정 인스턴스를 지연하거나 선택적으로 찾아야 하는 경우가 있을 것 같습니다.
  </details>
  <details>
    <summary>Spring의 Bean 생명 주기(Life Cycle)에 대해 설명해 주세요.</summary>
  
    Spring Bean은 스프링 컨테이너에 의해 관리 받습니다.
    흐름은 다음과 같습니다.
    
    1. 생성 : 스프링 컨테이너가 Bean 정의를 읽고 Bean 인스턴스를 생성합니다.
    2. 의존 : 생성된 Bean 인스턴스는 생성자 주입 등의 방식으로 의존 설정이 일어납니다.
    3. 초기화 : Bean이 InitalizingBean 인터페이스를 구현했거나, @PostConstruct 어노테이션이 붙은 메서드가 있다면 초기화가 수행됩니다.
      - Bean 객체가 InitialzingBean 인터페이스 구현 시, afterPropertiesSet() 메서드가 호출
    4. 사용 : 이제 애플리케이션은 해당 Bean을 사용해 비즈니스 로직을 수행합니다.
    5. 소멸 : 추가적으로 Bean이 DisposableBean 인터페이스를 구현했거나, @PreDestory 어노테이션이 붙은 메서드가 있으면 Bean이 소멸된다.
      - Bean 객체가 DisposableBean 인터페이스 구현 시, destory() 메서드가 호출된다.
        
    이런 식으로 Spring 컨테이너는 Bean의 생명 주기를 관리한다.
  </details>
  <details>
    <summary>Spring에서 후보 없이 특정 기능을 하는 클래스가 단 1개일 때에도, 왜 구체 클래스를 사용하지 않고 Spring Bean을 사용 할까요?</summary>

     - Spring에서는 Bean을 사용하여 객체의 생명 주기를 관리합니다. 
     - Bean을 사용하면 개발자는 객체 생성, 소멸 등의 생명 주기 관리와 같은 부수적인 작업을 하지 않아도 되며, 객체의 의존성을 자동으로 관리해줍니다. 
     - 또한, Bean을 사용하면 하나의 객체를 여러 컴포넌트에서 공유하여 사용할 수 있어 메모리 사용량을 줄일 수 있습니다.
  </details>
  
  ---
  
</details>

<details>
  <summary><b>DTO, VO, DAO, ENTITY의 각 정의를 말해주세요.</summary>

  - DAO
    - Database에 접근하는 역할을 가진 객체입니다.
    - 데이터의 CRUD 작업을 시행하는 클래스입니다. 즉, 데이터에 대한 CRUD 기능을 전담하는 객체입니다.
  - DTO
    - 데이터를 전달하기 위한 객체입니다.
    - 로직을 가지지 않는 순수한 데이터 객체입니다.
    - 계층 간 데이터를 주고 받을 때 사용합니다.
  - VO
    - 값 자체를 표현하는 객체이비다.
    - VO는 Getter 메서드만 존재하고 Setter 메서드는 존재하지 않습니다. 단, 비즈니스 로직을 포함할 수 있습니다.
    - VO는 두 객체의 모든 필드 값들이 동일하다면, 두 객체는 같다라는 것이 핵심 정의입니다.
    - 완전히 값 자체 표현 용도로만 사용된다면, equals(), hashCode() 메서드를 오버라이딩 해야할 수도 있습니다.
  - Entity
    - Database Table과 매핑되는 클래스입니다.
  
  ---
  
  <details>
    <summary>DAO와 Repository 차이를 아시나요?</summary>

    - 이 둘은 거의 같다고 생각합니다. 좀 더 깊이있게 차이를 설명하자면, 
    - Repotiroy는 Entity 객체를 보관하고 관리하는 저장소라 생각합니다.
    - DAO는 데이터에 접근하도록 Databasae에 접근 관련 로직을 모아둔 객체라 생각합니다.
    - 즉, Repository는 객체 중심이고 DAO는 데이터 저장소인 Database 테이블 중심이라 생각합니다.
    - 하지만 둘다 개념의 차이일뿐 실제로 개발할 때는 비슷하게 사용되는 것 같습니다.
  </details>
  
  ---
  
</details>

## 스프링 심화

<!--

  <details>
    <summary>스프링 프레임워크에서 Bean을 등록할 때는 Proxy로 생성되나요? </summary>

    - Spring Framework에서는 Spring Context로 관리되는 Bean들이 필요한 경우 Proxy로 만들어지고 나머지는 일반적인 Bean으로 생성됩니다.
    -  예를 들어, AOP와 같이 Proxy가 필요한 어노테이션을 사용하는 경우 Proxy 객체로 생성됩니다.
  </details>
  <details>
    <summary>스프링의 전체 동작 과정에 대해 설명해주세요.</summary>

    1. 클라이언트의 요청: 
      - 사용자가 웹 브라우저를 통해 특정 URL에 요청을 보냅니다.
    2. DispatcherServlet: 
      - 스프링 MVC에서 가장 먼저 요청을 받는 것은 디스패처 서블릿입니다. 
      - 이는 프론트 컨트롤러 패턴을 구현한 것으로, 모든 클라이언트의 요청을 한 곳에서 받아 적절한 컨트롤러에게 요청을 위임합니다.
    3. HandlerMapping: 
      - 디스패처 서블릿은 HandlerMapping에게 어떤 컨트롤러(핸들러)에게 요청을 위임할지 물어봅니다. 
      - HandlerMapping은 요청 URL을 분석하여 해당 URL을 처리할 수 있는 가장 적합한 컨트롤러를 찾아 반환합니다.
    4. 컨트롤러 실행: 
      - 디스패처 서블릿은 HandlerMapping이 반환한 컨트롤러를 실행시킵니다. 
      - 컨트롤러는 비즈니스 로직을 처리하고, 그 결과를 저장하는 모델 객체와 결과를 보여줄 뷰 이름을 반환합니다.
    5. ViewResolver: 
      - 디스패처 서블릿은 컨트롤러가 반환한 뷰 이름을 ViewResolver에게 전달합니다. 
      - ViewResolver는 이 뷰 이름을 기반으로 실제로 결과를 보여줄 뷰 객체를 찾아 반환합니다.
    6. 뷰 처리: 
      - 디스패처 서블릿은 ViewResolver가 반환한 뷰 객체에 모델 데이터를 전달하여 처리를 요청합니다. 
      - 뷰 객체는 모델 데이터를 사용하여 결과 페이지를 생성합니다.
    7. 클라이언트에게 응답 반환: 
      - 디스패처 서블릿은 생성된 결과 페이지를 클라이언트에게 반환합니다. 
      - 이로써 클라이언트의 요청 처리가 완료됩니다.

    이처럼 스프링 프레임워크는 클라이언트의 요청을 받아 처리하고 결과를 반환하는 전체 과정을 통합적으로 관리합니다. 
    이를 통해 개발자는 비즈니스 로직에 집중할 수 있으며, 애플리케이션의 유지보수와 확장성도 향상시킬 수 있습니다.
  </details>
  <details>
    <summary>스프링부트에서 에러가 발생했을 때 동작과정에 대해 설명해주세요.</summary>

    - 스프링부트는 예외 발생 시, 기본적으로 예외 요청을 다시 전달하도록 WAS 설정이 되어 있습니다. 
    - 즉, 별도 설정이 없을 때, 예외 발생 시, BasicErrorController가 동작합니다.
    - 이 BasicErrorController의 예외 경로는 기본적으로 `/error`입니다.
  </details>
  <details>
    <summary>springBootApplication run 이 일어나면 동작하는 과정에 대해 설명해주세요 (답변 미작성)</summary>
  </details>
  
<details>
  <summary><b>9. AOP(Aspect Oriented Programming)에 대해 설명해 주세요.</b></summary>

  - AOP, 즉 관점 지향 프로그래밍은 횡단 관심사를 분리하여 모듈화하는 프로그래밍 패러다임입니다. 
  - 로깅, 트랜잭션 관리, 보안 등 여러 곳에서 공통으로 사용되는 코드를 분리하여 중복을 제거하고, 코드의 가독성을 높이는 데 도움을 줍니다.

  ---

  <details>
    <summary>AOP 동작원리에 대해 설명해보세요.</summary>

    - AOP는 프록시 패턴을 기반으로 동작합니다. 
    - 스프링 AOP에서는 특정 빈에 대한 프록시 객체를 생성한 후, 이 프록시 객체를 통해 원래의 빈을 대신하여 동작하게 합니다. 
    - 이 프록시 객체에서는 원래의 빈의 메서드 실행 전후에 추가적인 로직(Advice)를 실행하여, 횡단 관심사를 처리합니다. 
  </details>
  <details>
    <summary>AOP 용어들을 설명해보세요. (Advice, Joinpoint, Pointcut, Weaving, Aspect, Target, Proxy, Introduction)</summary>

    - Advice: 
      - 횡단 관심사의 코드를 가리키며, 언제 실행할 지를 정의합니다. 
      - 예를 들어, 메서드 호출 전후에 실행하는 등의 설정이 가능합니다. 
    - Joinpoint: 
      - Advice가 적용될 수 있는 위치를 말합니다. 
      - 스프링 AOP에서는 메서드 호출이 Joinpoint에 해당합니다. 
    - Pointcut: 
      - 어떤 Joinpoint에 Advice를 적용할 지를 정의하는 것입니다. 
      - 표현식을 통해 특정 메서드를 선택하는 등의 설정이 가능합니다. 
    - Weaving: 
      - Advice를 Joinpoint에 적용하는 과정을 말합니다. 
      - 컴파일, 로드, 런타임 등 다양한 시점에서 수행될 수 있습니다. 
    - Aspect: 
      - 횡단 관심사를 모듈화한 것을 말합니다. 
      - Advice와 Pointcut을 포함합니다.
    - Target: 
      - Advice가 적용되는 대상 객체를 말합니다. 
      - 스프링 AOP에서는 빈 객체가 Target에 해당합니다.
    - Proxy: 
      - Target에 Advice를 적용하여 생성한 객체를 말합니다. 
      - 스프링 AOP에서는 런타임에 프록시 객체를 생성하여 AOP를 구현합니다.
    - Introduction: 
      - 기존 클래스에 새로운 메서드나 필드를 추가하는 것을 말합니다. 
      - 스프링 AOP에서는 @DeclareParents 어노테이션을 이용하여 Introduction을 구현할 수 있습니다. 
      - 이를 통해 특정 클래스가 특정 인터페이스를 구현하도록 할 수 있습니다.
  </details>
  <details>
    <summary>@Aspect는 어떻게 동작하나요?</summary>

    - @Aspect 어노테이션은 클래스 레벨에서 적용되며, 해당 클래스를 Aspect로 정의합니다. 
    - 이 클래스 내부에서 Pointcut과 Advice를 정의하며, 이를 통해 어떤 Joinpoint에 어떤 Advice를 적용할 지를 설정합니다.
  </details>
  <details>
    <summary>AspectJ 란 무엇인가요?</summary>

    - AspectJ는 AOP를 구현하기 위한 자바 프레임워크입니다. 
    - 스프링 AOP는 실행 시점에 동적으로 프록시 객체를 생성하여 AOP를 구현하는 반면, AspectJ는 컴파일 시점에 바이트 코드를 조작하여 AOP를 구현합니다. 
  </details>
  <details>
    <summary>AOP와 필터, 인터셉터의 차이점에 대해 자세하게 설명해보세요.</summary>

    1. 작동 시점 
      - 필터: 
        - 스프링의 디스패처 서블릿이 작동하기 전과 후로 동작합니다.
        - 즉, 서블릿 컨테이너 단에서 동작하며, HTTP 요청이 웹 애플리케이션에 들어오고 나가는 시점에 동작합니다. 
        - 따라서 필터는 스프링의 컨텍스트 외부에서 작동하며, 스프링과 관련이 없는 웹 리소스에 대해서도 작동합니다. 
      - 인터셉터: 
        - 스프링의 디스패처 서블릿이 컨트롤러를 호출하기 전과 후에 요청을 가로챕니다. 
        - 따라서 인터셉터는 스프링의 컨텍스트 내부에서 작동하며, 스프링 MVC의 컨트롤러에 대해서만 작동합니다. 
      - AOP
        - 특정 Joinpoint에서 동작하며, 이는 메서드 호출 전/후, 메서드 실행 중 예외 발생 시 등 다양한 시점에 해당될 수 있습니다.
        - 즉, 특정 메서드 호출 전/후에 실행됩니다.
    2. 접근 가능한 객체
      - 필터: 
        - HttpServletRequest와 HttpServletResponse 객체에만 접근할 수 있습니다. 
        - 스프링의 컨텍스트에 접근하는 것은 불가능합니다.
      - 인터셉터: 
        - HttpServletRequest와 HttpServletResponse 뿐만 아니라,  HandlerMapping이 선택한 Controller(핸들러)에 대한 정보에도 접근이 가능합니다. 
        - 또한, 스프링의 컨텍스트에 접근하는 것도 가능합니다.
        - 이를 통해 특정 컨트롤러에 대한 요청인지를 판단하거나, 컨트롤러의 실행 여부를 결정하는 등의 로직을 구현할 수 있습니다. 
      - AOP
        - 클래스, 메서드, 필드 등 다양한 객체에 접근이 가능합니다. 
        - 스프링의 컨텍스트에도 접근이 가능합니다. 
    3. 사용 목적
      - 필터: 
        - 인코딩, CORS 설정, 로깅 등의 공통적인 웹 처리를 위해 사용됩니다. 
        - 즉, 공통적으로 설정해야 하는 HTTP 헤더 처리 등 HTTP 요청과 응답에 대한 전/후처리를 합니다.
      - 인터셉터: 
        - 인증, 권한 체크, 세션 체크 등의 스프링 MVC와 관련된 처리를 위해 사용됩니다.
        - 즉, Controller의 실행 전/후로 공통 처리가 필요한 경우에 사용됩니다.
      - AOP
        - 로깅, 트랜잭션 관리, 보안 등 전체 애플리케이션에 걸쳐 공통적으로 적용되어야 하는 횡단 관심사를 처리하는 데 사용됩니다.

    정리하자면, Filter와 Interceptor는 주로 웹 관련 처리에 초점을 맞추는 반면, 
    AOP는 애플리케이션 전체에 걸친 공통 로직을 처리하는 데 주로 사용됩니다. 
    또한, Filter와 Interceptor는 주로 HTTP 요청의 전/후 처리를, AOP는 특정 로직의 전/후 처리를 담당합니다.
  </details>
  <details>
    <summary>AOP 를 실제로 사용해 본 경험이 있나요?</summary>
    로깅을 위해.. 어쩌구.. 저쩌구..
  </details>
  <details>
    <summary>AOP 를 동작시키기 위해 어떤 조건 혹은 어떤 코드를 구성을 해야 AOP 가 정상적으로 동작하는지 아시나요?</summary>

    - Aspect 클래스에 @Aspect 어노테이션을 붙여야 합니다. 
      - Aspect 클래스를 스프링 컨테이너에 빈으로 등록해야 합니다. 
      - 이는 @Component 어노테이션을 이용하거나, XML 설정 등을 통해 가능합니다. 
    - Advice 메서드에 @Before, @After, @Around 등의 어노테이션을 붙여 언제 실행될 지를 설정해야 합니다. 
    - Pointcut 표현식을 통해 어떤 Joinpoint에 Advice를 적용할 지를 설정해야 합니다.
  </details>
  <details>
    <summary>AOP 적용할 수 있는 포인트가 메서드라고 했을 때 메서드의 시작과 끝에 AOP 를 걸 수가 있습니다. 이때, 메서드를 호출하는 과정에서 메서드가 다른 외부에서의 호출이거나 동일한 클래스 내부에서의 호출이 될 수도 있습니다. 이런 경우에 모두 AOP가 동작하나요? 근거와 함께 설명해주세요.</summary>

    - 스프링 AOP는 프록시 기반의 AOP를 사용하므로, 메서드를 호출하는 주체에 따라 AOP가 적용되지 않을 수 있습니다. 
    - 예를 들어, 동일한 클래스 내부에서의 메서드 호출은 프록시를 거치지 않으므로 AOP가 적용되지 않습니다. 
    - 반면, 외부에서의 호출은 프록시를 거치므로 AOP가 적용됩니다. 
    - 이러한 이유로, AOP를 적용하려는 메서드는 외부에서 호출 가능하도록 public으로 선언되어야 합니다.
  </details>
</details>

<details>
  <summary><b>10. 프록시가 무엇인지 아시나요?</b></summary>

  - 프록시는 '대리인'이라는 의미를 가지며, 다른 객체를 대신하여 그 객체의 기능을 사용하거나 제어하는 역할을 합니다. 
  - 컴퓨터 과학에서는 프록시를 통해 인터페이스를 제공하고, 이를 통해 실제 객체의 기능을 사용하거나 추가적인 기능을 제공합니다

  ---

  <details>
    <summary>프록시 패턴이란 무엇인가요?</summary>

    - 프록시 패턴은 디자인 패턴 중 하나로, 어떤 객체에 대한 접근을 제어하거나 추가적인 작업을 수행하기 위해 그 객체의 대리 객체를 제공하는 패턴입니다. 
    - 프록시 객체는 원래 객체와 같은 인터페이스를 가지므로, 클라이언트는 원래 객체인지 프록시 객체인지 구별 없이 사용할 수 있습니다.
  </details>
  <details>
    <summary>프록시 객체란 무엇인가요?</summary>

    - 프록시 객체는 원래 객체를 대신하여 그 객체의 기능을 사용하거나 제어하는 객체를 말합니다. 
    - 프록시 객체는 원래 객체와 같은 인터페이스를 가지므로, 클라이언트는 원래 객체인지 프록시 객체인지 구별 없이 사용할 수 있습니다.
  </details>
  <details>
    <summary>동적 프록시(JDK Dynamic Proxy)에 대해 설명해주세요.</summary>

    - 이 방식은 자바에서 제공하는 동적 프록시 기능으로, 인터페이스를 구현하는 프록시 객체를 런타임에 동적으로 생성합니다. 
    - 이는 런타임에 특정 인터페이스를 구현하는 클래스 또는 인스턴스를 만드는 기술로 Reflection API의 프록시 클래스를 이용하여 구현할 수 있습니다.
    - 이를 통해 원래 객체의 기능을 사용하면서 추가적인 기능을 제공할 수 있습니다.
    
    단, 이 방식은 인터페이스가 있어야만 가능한 방법이고 Reflection을 사용하기 때문에 컴파일러 최적화를 전혀 받지 못해 성능상 좋지 않습니다. 
    그리고 사실 여러 부가기능을 적용해야할 때, 계속해서 무거워집니다.
  </details>
  <details>
    <summary>CGLIB(Code Generation Library)에 대해 설명해주세요.</summary>
    
    - CGLIB는 바이트 코드 조작 라이브러리로, 클래스 파일을 동적으로 생성하여 프록시 객체를 만드는 데 사용됩니다. 
    - 이를 통해 인터페이스가 없는 클래스에 대해서도 프록시 객체를 생성할 수 있습니다. 
    - 즉, 동적 프록시와는 다르게 클래스 기반으로 동작을 하고 특정 라이브러리를 사용하여 프록시를 만듭니다.
    - 이 기능은 스프링 AOP에서 사용되며, JDK Dynamic Proxy로 처리할 수 없는 경우에 CGLIB를 사용하여 프록시 객체를 생성합니다.

    결론적으로 CGLIB은 동적 프록시와는 다르게 외부 의존성을 사용하기 때문에, 의존성을 추가해야 합니다. 
    하지만 CGLIB은 메소드가 처음 호출 됐을 때, 동적으로 타겟 클래스의 바이트 코드를 조작하고 이후 호출 시에는 조작된 바이트 코드를 재사용합니다. 
    즉, 성능면에서 Reflection을 사용하는 동적 프록시보다 좋을 수밖에 없습니다.
  </details>
  <details>
    <summary>Dynamic Proxy와 CGLIB에 대해 IoC 컨테이너와 연관지어 설명해주세요 (답변 미작성)</summary>
  </details>
  <details>
    <summary>프록시가 스프링 싱글톤 빈에서 동시성 처리에 용이한 이유를 아시나요? (답변 미작성)</summary>
  </details>
</details>  

-->
  
## Reference

- [https://inpa.tistory.com/](https://inpa.tistory.com/)
- [https://mangkyu.tistory.com/](https://mangkyu.tistory.com/)
- [https://steady-coding.tistory.com/](https://steady-coding.tistory.com/)
- [https://catsbi.oopy.io/](https://catsbi.oopy.io/)
- [https://sas-study.tistory.com/](https://sas-study.tistory.com/)
