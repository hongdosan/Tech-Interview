<!--
<details>
  <summary><b></b></summary>

  ---

  <details>
    <summary></summary>
  </details>
</details> 
-->

## 객체지향
<details>
  <summary><b>객체지향 4가지 특징에 대해 설명하세요.</b></summary>

  - 객체지향 4가지 특성 중 적용한 특성이 있나요?
  - 오버로딩과 오버라이딩 차이점에 대해 설명하세요.
  - 클래스, 객체, 인스턴스 차이에 대해 설명하세요.
  - 접근 제어자에 대해 설명하세요.
  - 추상 클래스와 인터페이스 차이점에 대해 설명하세요.
  - 본인은 어떤 기준으로 추상 클래스와 인터페이스를 사용하는지 알려주세요.
</details>
<details>
  <summary><b>SOLID 5원칙에 대해 설명하세요.</b></summary>

  - SOLID 원칙에서 가장 중요하다고 생각하는 원칙이 있나요?
  - DIP를 적용해본 경험이 있나요?
</details>
<details>
  <summary><b>객체지향, 절차지향, 함수형 프로그래밍 차이점에 대해 설명하세요.</b></summary>

  - 자바의 함수형 프로그래밍 예시를 설명하세요.
  - 일급 객체에 대해 설명하세요.
</details>

## Java Version

<details>
  <summary><b>Java 8에 대해 설명해주세요.</b></summary>

</details>
<details>
  <summary><b>Java 11에 대해 설명해주세요.</b></summary>

</details>

<details>
  <summary><b>Java 17에 대해 설명해주세요.</b></summary>

</details>

<details>
  <summary><b>Java 21에 대해 설명해주세요.</b></summary>

  - Virtual Thread에 대해 설명해주세요.
</details>

## Java 기초

<details>
  <summary><b>Primitive Type과 Reference Type의 차이점에 대해 설명하세요.</b></summary>

  - Wrapper Class에 대해 설명하세요.
  - Call By Reference와 Call By Value에 대해 설명하세요.
</details>
<details>
  <summary><b>Java의 Exception에 대해 설명해 주세요.</b></summary>

  ![image](https://github.com/HyuckJuneHong/Tech-Interview/assets/31675711/56efe881-6e81-4275-8d1b-d55b7c674c34)
  > [그림 출처](https://velog.io/@agugu95/java-exception-and-error)

  ---

  <details>
    <summary>프로그래밍의 오류 종류는 무엇이 있을까요?</summary>

    - 컴파일 에러
      - 컴파일 시 발생하는 에러입니다.
      - 컴파일 단계에서 오류 발견 시, 컴파일러가 에러 메시지를 출력해주는 에러를 말합니다.
    - 런타임 에러
      - 실행 시 발생하는 에러입니다.
      - 컴파일 문제가 없더라도, 프로그램 실행 중에 에러가 발생해 잘못된 결과를 얻거나, 
        외부적인 요인으로 프로그램이 비정상 종료되는 에러를 말합니다.
    - 논리적 에러
      - 실행은 되지만, 의도와 다르게 동작하는 에러입니다.
      - 일종의 버그라고 할 수 있습니다.
      - 실행 및 작동에 아무 문제가 없지만, 결과가 예상과 다른 에러입니다.
  </details>
  <details>
    <summary>Error와 Exception의 차이점에 대해 설명해주세요.</summary>

    자바에서의 오류는 프로그램 실행 중 어떤 원인에 의해 오작동 혹은 비정상 종료되는 경우를 프로그램 오류라고 합니다.
    자바에서 이 오류가 Error(에러)와 Exception(예외)로 나뉘는데, 메모리 부족같은 복구할 수 없는 오류를 에러라고 하고
    NPE와 같이, 예측해서 상황에 맞게 처리할 수 있는 오류를 예외라고 합니다.
    
    - 에러(Error)
      - 시스템이 종료되어야할 수준과 같이 수습할 수 없는 심각한 문제입니다.
      - 이는 개발자가 미리 예측하여 방지할 수 없습니다.
      - Ex) StackOverflowError : 호출의 깊이가 깊어지거나, 재귀가 지속되어 stack overflow 발생 시, 던지는 에러입니다.
      - Ex) OutOfMemoryError : JVM이 할당한 메모리 부족으로 더 이상 객체를 할당할 수 없을 때 던지는 에러입니다.
                               이는, GC에 의해 추가적인 메모리가 확보되지 못하는 상황이기도 합니다.
    - 예외(Exception)
      - 이는 개발자가 미리 예측해서 상황에 맞는 예외처리를 할 수 있습니다.
      - 예외는 오류와 다르게 개발자가 임의로 예외를 던질 수 있습니다.
      - 예외는 RuntimeException과 Exception으로 나뉩니다.
      - Ex) NullPointerException : 객체가 필요한 경우에 null을 사용하려고 시도한 경우 던지는 예외입니다.
      - Ex) IllegalArgumentException : 메서드가 허가되지 않거나 부적절한 Argument를 받았을 때, 던지는 예외입니다.
    
    - 공통점
      - 오류나 예외 모두 Object 클래스를 상속 받는 Throwable 클래스를 상속 받습니다.
      - Throwable 객체는 오류나 예외에 대한 메시지를 담고, 예외가 연결될 때 해당 예외의 정보를 기록합니다.
        이를 위해, Throwable 클래스에는 getMessage()와 printStackTrace() 함수가 구현되어 있습니다.
  </details>
  <details>
    <summary>CheckedException, UncheckedException 의 차이에 대해 설명해 주세요.</summary>

    - CheckedException (컴파일 에외 클래스들)
      - 예외 처리하지 않을 시, 컴파일되지 않기 때문에, 예외 처리가 필수입니다.
      - JVM 외부와 통신(네트워크, 파일 시스템 등) 시, 주로 사용됩니다.
      - RuntimeException을 상속받지 않는 모든 예외를 말합니다.
      - Ex) IOExceptiom, SQLException 등
    - UncheckedException (런타임 예외 클래스들)
      - 예외 처리하지 않아도, 컴파일이 가능합니다.
      - RuntimeException을 상속받는 모든 예외입니다.
      - Ex) NPE, IndexOutOfBoundException 등
  </details>
  <details>
    <summary>예외 처리(Exception Handling)를 하는 방법에 대해 설명해 주세요.</summary>

    - `try-catch`문으로 감싸서 복구 및 전환하거나, Throws로 던져서 회피하여 처리할 수 있습니다.
  </details>
  <details>
    <summary>예외처리가 성능에 큰 영향을 미치나요? 만약 그렇다면, 어떻게 하면 부하를 줄일 수 있을까요?</summary>
  </details>
  <details>
    <summary>try-with-resource에 대해 설명하세요.</summary>

    try-with-resource는 try 블록이 끝날 때, 자동으로 자원을 해제해주는 기능입니다.

    - 보통 DB, Network, File 등과 같은 자원을 사용 후 자원을 해제해야 하는데, 실수 및 에러로 인해, 자원이 해제되지 않을 수 있습니다.
    - 이 `try-with-resource`문을 이용하면, try 블록이 끝나자마자 자동으로 할당된 자원을 해제해 줍니다.
    - 단, `try-with-resource`을 사용하려면, AutoCloseable 인터페이스를 구현하고 있어야 합니다.

    - 특징
      - 자원 반납에 의해 코드가 복잡해지던 문제를 해결
      - 실수 및 에러로 인해 자원을 반납하지 못하던 문제 해결
      - 에러 스택 트레이스가 누락되던 문제 해결
      - Java 7에 도입
  </details>
  <details>
    <summary>AutoCloseable, Closeable 차이점에 대해 설명하세요.</summary>

    이 둘은 거의 똑같은데, Closeable은 IOException으로 범위가 더 좁습니다. 
    하지만 Closeable이 AutoCLoseable보다 더 오래된 인터페이스입니다.
    때문에, Closeable 인터페이스 부모 인터페이스인 AutoCloseable을 추가함으로써, 
    하위 호환성을 달성함과 동시에 변경 작업에 대한 수고를 덜었습니다.
    만약, Closeable을 부모로 만들었다면, 기존에 이를 사용하던 클래스들을 모두 AutoCloseable로 수정해야 합니다.

    - Closeable
      - backward compatiblity를 유지하기 위해 남아 있습니다.
      - JDK 5에 도입되었습니다.
      - `void close() throws IOException`
      - AutoCloseable의 자식 인터페이스입니다.      
    - AutoCloseable
      - try-with-resources statement를 위해 도입 되었습니다.
      - JDK 7에 도입되었습니다.
      - `void close() throws Exception`
      - Closeable의 부모 인터페이스입니다.
  </details>

  ---
</details>
<details>
  <summary><b>static에 대해 설명해주세요.</b></summary>
  
  - static class와 static method를 비교해 주세요.
  - static 을 사용하면 어떤 이점을 얻을 수 있나요?
  - static 을 사용하면 어떤 제약이 걸릴까요?
  - 컴파일 과정에서 static 이 어떻게 처리되는지 설명해 주세요.
</details>
<details>
  <summary><b>final에 대해 설명해주세요.</b></summary>

  - final 키워드를 사용하면, 어떤 이점이 있나요?
  - 그렇다면 컴파일 과정에서, final 키워드는 다르게 취급되나요?
</details>
<details>
  <summary><b>generic에 대해 설명해주세요.</b></summary>

</details>
<details>
  <summary><b>Java Stream에 대해 설명해 주세요.</b></summary>

  - Stream과 for ~ loop의 성능 차이를 비교해 주세요.
  - Stream은 병렬처리 할 수 있나요?
  - Stream에서 사용할 수 있는 함수형 인터페이스에 대해 설명해 주세요.
  - 가끔 외부 변수를 사용할 때, final 키워드를 붙여서 사용하는데 왜 그럴까요? 꼭 그래야 할까요?
</details>
<details>
  <summary><b>Java Lambda에 대해 설명해 주세요.</b></summary>

</details>
<details>
  <summary><b>Reflection에 대해 설명해 주세요.</b></summary>
  
  - 의미만 들어보면 리플렉션은 보안적인 문제가 있을 가능성이 있어보이는데, 어떻게 방지할 수 있을까요?
  - 리플렉션을 언제 활용할 수 있을까요?
  - Dynamic Proxy에 대해 설명해 주세요.
</details>

## Java Collection

<details>
  <summary><b>equals()와 hashcode()에 대해 설명해 주세요.</b></summary>

  - hashcode() 를 정의해야 한다면, 어떤 점을 염두에 두고 구현할 것 같으세요?
  - equals() 를 재정의해야 할 때, 어떤 점을 염두에 두어야 하는지 설명해 주세요.
</details>
<details>
  <summary><b>Synchronized 키워드에 대해 설명해 주세요.</b></summary>

  - Synchronized 키워드가 어디에 붙는지에 따라 의미가 약간씩 변화하는데, 각각 어떤 의미를 갖게 되는지 설명해 주세요.
  - 효율적인 코드 작성 측면에서, Synchronized는 좋은 키워드일까요?
  - Synchronized 를 대체할 수 있는 자바의 다른 동기화 기법에 대해 설명해 주세요.
  - Thread Local에 대해 설명해 주세요.
  - Volatile에 대해 설명해주세요.
  - AtomicInteger에 대해 설명해주세요.
</details>
<details>
  <summary><b>String에 대해 설명해 주세요.</b></summary>

  - String, StringBuffer, StringBuilder 차이점을 설명해주세요.
  - Immutable Object에 대해 설명해주세요.
  - `String a = ""`과 `String a = new String("")`의 차이점을 설명해주세요.
</details>

## JVM & Garbage Collector

<details>
  <summary><b>JVM이 정확히 무엇이고, 어떤 기능을 하는지 설명해 주세요.</b></summary>

  - JDK, JRE, JVM 차이점을 설명해주세요.
  - 자바 말고 다른 언어는 JVM 위에 올릴 수 없나요?
  - JVM 계열 언어를 일반적으로 컴파일해서 사용할 순 없나요?
  - VM을 사용함으로써 얻을 수 있는 장점과 단점에 대해 설명해 주세요.
  - JVM과 내부에서 실행되고 있는 프로그램은 부모 프로세스, 자식 프로세스 관계를 갖고 있다고 봐도 무방한가요?
  - JVM의 성능을 모니터링하고 분석해본 경험이 있나요? 있다면 설명해주세요.
</details>
<details>
  <summary><b>JVM 메모리 구조를 설명해주세요.</b></summary>

  - Stack과 Heap 메모리 차이점을 설명하세요.
  - Heap에 메모리를 할당하는 과정에 대해 설명하세요.
  - TLAB Thread-Local Allocation Buffer가 무엇인지 아시나요?
</details>
<details>
  <summary><b>자바는 컴파일 언어인가요? 인터프리터 언어인가요?</b></summary>
  
  - 컴파일 언어와 인터프리터 언어의 차이점은?
  - 자바 컴파일 과정을 설명해주세요.
</details>
<details>
  <summary><b>Java의 GC에 대해 설명해 주세요.</b></summary>

  - GC는 왜 필요할까요?
  - finalize() 를 수동으로 호출하는 것은 왜 문제가 될 수 있을까요?
  - 어떤 변수의 값이 null이 되었다면, 이 값은 GC가 될 가능성이 있을까요?
  - GC의 대상을 어떻게 판별할까요?
  - GC 동작과정을 설명해주세요.
</details>
<details>
  <summary><b>STW (Stop-The-World)에 대해 설명하세요.</b></summary>

</details>
<details>
  <summary><b>`Parallel GC`, `G1 GC`, `ZGC`를 설명해주세요.</b></summary>

</details>

## Reference

- [https://mangkyu.tistory.com/](https://mangkyu.tistory.com/)
- [https://inpa.tistory.com/](https://inpa.tistory.com/)
- [https://gyoogle.dev/blog/computer-language/Java/Error%20&%20Exception.html](https://gyoogle.dev/blog/computer-language/Java/Error%20&%20Exception.html)

<!-- 


<details>
  <summary><b>인터페이스와 추상 클래스의 차이에 대해 설명해 주세요.</b></summary>

- 왜 클래스는 단일 상속만 가능한데, 인터페이스는 2개 이상 구현이 가능할까요?

</details>



<details>
  <summary><b>Java 에서 Annotation 은 어떤 기능을 하나요?</b></summary>

  - 어노테이션은 자바 소스 코드에 메타데이터를 제공하는 방법입니다. 
  - 이는 코드의 의미를 설명하거나, 컴파일 시점이나 실행 시점에 특정 기능을 수행하도록 정보를 제공합니다. 
  - 예를 들어, @Override 어노테이션은 메서드가 상위 클래스의 메서드를 오버라이드한다는 것을 컴파일러에게 알려줍니다.
  - 예를 들어, @Autowired 어노테이션은 스프링 프레임워크에게 의존성 주입을 요청합니다.

  ---

  - 별 기능이 없는 것 같은데, 어떻게 Spring 에서는 Annotation 이 그렇게 많은 기능을 하는 걸까요?
  - Lombok의 @Data를 잘 사용하지 않는 이유는 무엇일까요?
</details>
-->
