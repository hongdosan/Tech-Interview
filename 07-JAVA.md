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

  - 공유되는 변수나 메서드를 정의할 때 사용되는 키워드입니다. <br/>
    즉, 정적(=클래스) 멤버인 정적 필드나 정적 메서드를 정의할 때 사용됩니다.
  - static은 런타임 시, 클래스 로더에 의해서 Method Area 혹은 Heap 영역에 <br/>
    클래스 메타 데이터 및 정적 변수로 적재됩니다.
  - 대부분의 static은 런타임에 적재되고 프로그램 종료까지 GC 대상이 아니지만, <br/>
    Java 8 이후부터 Static 객체는 Heap 영역에 저장되고 주소값은 metaspace에서 <br/>
    관리되기 때문에, 참조를 잃은 Static 객체는 GC 대상이 될 수 있습니다.
  - Static 객체는 Java 8이전에 Permanent 영역, 이후에는 Heap 영역에서 관리됩니다.

  ---

  <details>
    <summary>인스턴스 변수, static 변수와 static 메서드를 비교해 주세요.</summary>

    - 인스턴스 변수(non-static 변수)
      - 클래스 내에 선언된 변수를 말합니다.
      - 객체 생성 시마다 매번 새로운 변수가 생성됩니다.
      - 클래스 변수와 달리 공유되지 않습니다.
    - static 변수
      - 특정 클래스에서 공용으로 함께 사용할 수 있는 변수를 만들고자 하는 경우 사용됩니다.
      - 힙 영역이 아닌, 메서드 영역에 저장되며, 클래스 당 단 하나만 생성됩니다.
      - 접근의 경우 클래스, 인스턴스 둘 다 가능하지만, 클래스 접근을 권장합니다.
    - static 메서드
      - 인스턴스 변수가 별도로 필요하지 않고, 단순히 기능만 제공할 때 사용됩니다.
      - static 메서드 내에서는 static method와 static 변수만 사용 가능합니다.
  </details>
  <details>
    <summary>static 사용을 왜 지양해야 할까요?</summary>

    - `메모리가 낭비`됩니다.
      - 대부분의 static은 프로그램 실행 시점에 메모리에 할당하며, 프로그램 종료 시점까지 메모리에서 해제되지 않기 때문입니다.
    - `별도의 동기화 전략을 수립`해야 합니다.
      - static은 전역에서 접근이 가능하기 때문입니다.
      - 전역에서 접근 가능하므로, 가변보다는 불변으로 선언하는 것이 좋습니다.
      - 만약, 동시성을 제어해 Thread-safe하게 구현한다면 성능이 떨어지게 됩니다.
    - `런타임 다형성이 불가능`합니다.
      - static으로만 이뤄진 메서드를 사용하는 객체는 메모리를 할당해서 사용하지 않고 해당 메서드에 바로 접근하여 호출하기 때문입니다.
    - `객체 상태를 이용할 수 없습니다.`
      - 대부분 static은 프로그램 실행 시점에 메모리에 올라가므로, 정적 메서드 안에서 초기화되지 않은 필드를 사용하면, 문제가 생길 수 있습니다. 
        즉, 정적 메서드 안에선 정적 변수만 사용할 수 있습니다.
      - 반대로, 정적 메서드가 아닌 일반 메서드들은 객체 내의 상태를 통해 메서드를 구현해줄 수 있으므로 상태에 따라 다양한 구현이 가능합니다.
        즉, 객체 내에 정적 메서드가 많을 수록 외부 값에 의존하는 수동적인 객체가 됩니다.
    - `테스트하기가 어렵습니다.`
      - 정적 변수는 전역으로 관리되기 때문에, 프로그램 전체에서 이 필드에 접근하고 수정할 수 있습니다.
        즉, 해당 필드를 추론하기 어려워 테스트하기가 까다롭습니다.
  </details>
  <details>
    <summary>그렇다면, static은 어떤 시점에 사용해야 하고, 사용 시, 어떤 이점을 얻을 수 있나요?</summary>

    - 자주 사용되는 상수를 정의할 때 사용할 수 있습니다.
      - `private static final` 키워드를 이용해 불변 변수인 상수를 정의하여 메모리를 아낄 수 있습니다.
    - 유틸리티 클래스를 정의할 때 사용할 수 있습니다.
      - 인스턴스 메서드와 인스턴스 변수를 제공하지 않고, 데이터 처리만을 위한 정적 메서드인 유틸리티 클래스를 정의하여 유용하게 사용할 수 있습니다.
      - 즉, 객체 상태가 필요 없고 여러 객체에서 데이터를 처리하는 공통 로직이 필요할 때 사용할 수 있습니다.
      - 예를 들어, Java의 Math Class는 상수 외에 인스턴스 변수가 하나도 없고 오로지 계산을 위한 정적 메서드만 제공합니다.
  </details>
  <details>
    <summary>static이 저장되는 위치는 어디인가요?</summary>

    static으로 선언된 변수는 Class Variables 영역에 저장됩니다.
    만약, final이 함께 사용된다면, Constant Pool에 값이 복사되어 값 조회 시, 바로 조회하기 때문에, 성능을 높여줍니다.

    - Java 8 이전
      - 8 이전의 Heap을 보면 Permanent 영역이 존재하고 이 안에 클래스 메타 데이터, 정적 변수 등이 저장됩니다.
      - 이때, Permanent 영역은 Method Area에 해당하므로 Java 8 이전의 static 변수는 메소드 영역에 저장되는 것이 맞습니다.
    - Java 8 이후
      - 8 이후 힙은 Permanent 영역이 사라지고 해당 영역에서 관리하던 클래스 메타 데이터는 Heap 외부의 Metaspace라는
        네이티브 메모리에 관리되도록 바뀌었고, String Pool과 클래스 정적 변수는 Heap 영역에서 관리되도록 바뀌었습니다.
      - 즉, Java 8 이후부터 static은 Heap 영역에서 관리됩니다. (참고: string pool은 Java 7부터)

    - Permanent 영역
      - 클래스 내부의 메타 데이터를 저장하는 영역
      - Heap 영역에 속하며, Class, Method Meta Data, Static Object, Variable, Constant Pool 등을 관리
      - Java 8 이전에는 Method Area로 사용.
      - Java 8 이후 이 영역은 사라지고 Metaspace 영역으로 대체
    - Metaspace 영역
      - Java 8부터 생긴 영역으로 Permanent 영역이 관리하던 정보를 저장.
      - Permanent 영역과는 다르게 Native Memory 영역으로서 JVM이 아닌 OS에서 관리
      - Method Area이 이 영역에 속한다.

    - Class Metadata
      - Method Area에 저장되는 정보 단위
      - Class Metadata가 저장되는 Method Area(Metaspace)는 Heap 영역에서 관리되기 때문에, 
        static 변수를 참조하지 않는 상황이 오면 GC 대상이 될 수 있습니다.
      - 즉, Class Metadata가 GC 대상이 되면, 자동적으로 static 변수들도 GC 대상이 됩니다.
    - Method Area에 저장되는 정보
      - Type 정보 : name, sub class name, modifier 등
      - Field 정보 : type, modifier 등
      - Method 정보 : Construtor를 포함한 모든 메소드 메타 데이터
      - Runtime Constant Pool : Type, Field, Method의 모든 레퍼런스 정보
                                JVM은 이 영역을 통해, 실제 메모리 상 주소를 찾아 참조합니다.
      - Class Variable : static 키워드로 선언된 변수를 저장합니다. 
                         클래스 변수를 관리하는 곳이기 때문에, 모든 인스턴스에 공유되며 인스턴스 없이 접근이 가능합니다.
                         final static 변수는 상수로 치환되어 Method Area의 Constant Pool에 값을 복사합니다.
                         클래스를 사용하기 이전에 이 변수들은 미리 메모리를 할당 받습니다.
  </details>
  <details>
    <summary>static 키워드 동작 흐름을 설명해주세요.</summary>

    [정리]
      1-1. static만 선언된 경우 Class Variables 영역에 값을 참조합니다.
      1-2. static만 선언된 경우 동시성 이슈가 발생할 수 있습니다.
      1-3. thread-safe하게 한다면 성능 이슈가 발생합니다.
  
      2-1. static과 final로 선언된 경우, Constant pool 영역에 값을 참조합니다.
      2-2. thread-safe하고 성능 이슈도 발생하지 않게 됩니다.

      3-1. Constant Pool에 복사된 값이 수정이 일어나면 Class Metadata를 갱신해야하기 때문에, 가변 변수는 따로 관리합니다.
      3-2. lazy-loading으로 static 변수 초기화 시점을 조절해 메모리를 효율적으로 사용할 수 있습니다.

    [static 키워드만 사용된 변수 호출 동작 흐름]
      - 메모리 할당 및 초기화 단계
        1. 클래스로더에 의해 메모리를 할당받고 static initializer에 의해 값을 초기화합니다.
        2. 메모리 영역의 Class Variable 영역에 변수값이 저장됩니다.
        3. 클래스의 Constant Pool에 Class Variable의 참조 값이 저장됩니다.
      - 호출 단계
        1. Constant Pool의 메모리 공간의 시작 지점을 조회합니다.
        2. Constant Pool에 저장된 참조 값을 읽습니다.
        3. Class Variables에서 실제 값을 읽습니다.
    [static과 final 키워드가 사용된 변수 호출 동작]
      - 메모리 할당 및 초기화 단계
        1. 선언된 변수는 메모리를 할당받고 static initializer에 의해 값을 초기화합니다.
        2. 메모리 영역의 Class Variable 영역에 실제 값이 저장됩니다.
        3. 클래스의 Constant Pool에 Class Variable의 실제 값이 복사됩니다.
      - 호출 단계
        1. Constant Pool의 메모리 공간의 시작 지점을 조회합니다.
        2. Constant Pool에 저장된 실제 값을 읽습니다.
    [왜, 차이가 발생할까?]
      - Constant Pool에 복사된 값을 수정하는 연산이 진행되면, Class Metadata를 갱신해야 하고,
        데이터 정합성을 위해 생기는 락에 의해 성능이 떨어질 수 있기 때문입니다.
      - 즉, 변경 가능성이 있는 변수를 따로 관리한다고 볼 수 있습니다.
    [static 변수가 바로 초기화되지 않는 상황]
      - static 변수들이 초기화되는 시점은 항상 클래스의 인스턴스가 생성되는 시점이라고 볼 수 없습니다.
        즉, static 변수를 Lazy Loading해 효율적으로 메모리를 사용할 수 있습니다.
      - 예를 들어, static 메서드는 호출 시점에 초기화되는 방식을 이용해 static variables가 선언된 inner class 인스턴스 생성을 제어하면,
        static 변수의 초기화 시점을 원하는 순간으로 조절할 수 있습니다.
  </details>
  <details>
    <summary>Java 8이후로 Heap의 Permanent(PermGen) 영역이 Native Memory 영역의 Metaspace로 대체된 이유는? </summary>
    
    - 결론부터 말씀드리면, OOM(OutOfMemory) 에러의 발생 가능성을 줄이기 위해서입니다.
    - PermGen은 고정 메모리 사이즈를 가지고 있기 때문에, MAX 값이 반드시 설정해야 해서 메모리 관리의 불편함이 있었습니다.
      만약, MAX 값을 설정하지 않으면 Default 값이 설정됩니다.
    - 어쨌든, 이 MAX 값을 넘어서는 순간, OOM이 발생하는데, 이 문제점을 해결하기 위해 Metaspace로 대체된 것입니다.
    - Metaspace의 메모리 MAX 값은 기본값이 64 bit Integer의 최댓값이기 때문에, 특별한 경우가 아닌 이상 신경쓰지 않아도 됩니다.
  </details>
  <details>
    <summary>컴파일 과정에서 static 이 어떻게 처리되는지 설명해주세요.</summary>

    - static 키워드가 붙은 멤버는 클래스 로딩 시점(런타임 시점)에 메모리에 할당됩니다.
    - 이는 컴파일 과정에서 이뤄지는 것이 아닌 JVM이 클래스를 로딩하고 초기화하는 과정에서 이뤄집니다.
    - static 키워드가 붙은 멤버는 클래스 레벨에서 관리되기 때문에, 해당 클래스의 모든 인스턴스에서 동일한 멤버에 접근할 수 있습니다.
  </details>
  
  ---
</details>
<details>
  <summary><b>final에 대해 설명해주세요.</b></summary>

  - 자바에서 불변성을 확보할 수 있도록 제공하는 키워드입니다.
    - final Variables, Arguments : 불변값이 되도록 합니다.
    - final Class : 상속받지 못하도록 합니다.
    - final Method : 오버라이딩이 되지 못하도록 합니다.
    
  ---
  
  <details>
    <summary>final 키워드를 사용하면, 어떤 이점이 있나요?</summary>

    - 최초 할당 후 해당 값을 변경할 수 없어 안정성을 높이고, 버그를 방지할 수 있습니다.
  </details>
  <details>
    <summary>Effective Final 키워드에 대해 아시나요?</summary>

    - 변수에 final 키워드를 사용하지 않아도 초기화 후 변경되지 않는 변수라면, 컴파일러가 final 변수로 인식하는 것을 말합니다.
    - 이는 Lambda가 final을 명시하지 않은 지역 변수를 사용할 수 있도록 하기 위해 Java 8이후로 도입된 기능입니다.
  </details>
  <details>
    <summary>그렇다면 컴파일 과정에서, final 키워드는 다르게 취급되나요?</summary>

    - final 키워드가 붙은 변수는 컴파일러에 의해 한 번만 초기화될 수 있음을 표시하는 것입니다.
      즉, 이는 불변성을 보장하는 키워드입니다. 
    - 예를 들어, 해당 키워드 사용 시, 해당 변수가 한 번 초기화 된 후 다시 값을 변경하는 코드가 있는 지 검사 후,
      있다면 컴파일 에러가 발생합니다.
  </details>

  ---
</details>
<details>
  <summary><b>generic에 대해 설명해주세요.</b></summary>

  - 타입을 클래스 내부에서 지정하는 것이 아닌 외부에서 사용자에 의해 지정하는 기능입니다.
  - 예를 들어, 변수 선언 시 타입을 지정해주듯, 재네릭은 객체에 타입을 지정해주는 것입니다.
  - 이 기능은 JDK 1.5에 추가된 Spec입니다.
  
  <details>
    <summary>제네릭 사용 이유 및 이점믈 설명해주세요.</summary>

    - 컴파일 단계에 타입 검사를 통한 예외 방지
      - JDK 1.5 이전에는 여러 타입을 다루기 위해 인수나 반환값으로 Object 타입을 사용했었습니다.
        하지만, 이 방식은 Object 타입 객체를 다시 원하는 타입으로 일일히 타입 변환을 해야하고 
        런타임 에러가 발생할 가능성도 존재했습니다.
      - 제네릭은 컴파일 시점에서 클래스나 메서드를 정의할 때, 타입 파라미터로 객체의 서브 타입을 지정해줌으로써,
        잘못된 타입이 사용될 수 있는 문제를 컴파일 단계에서 찾을 수 있습니다.
    - 불필요한 캐스팅을 없애 성능 향상
    
  </details>
  <details>
    <summary>제네릭 타입 파라미터에 대한 기능들을 모두 설명해주세요.</summary>

    - 재네릭 타입 매개변수
      - `<>` 다이아몬드 연산자를 통해 식별자 기호를 지정함으로써 파라미터화할 수 있습니다.
      - 메서드가 매개변수를 받아 사용하는 것과 비슷하여 제네릭의 타입 매개변수/타입 변수라고 부릅니다.
      - 할당 가능한 타입은 Reference 타입만 가능합니다.
    - 제네릭 타입 전파
      - `<T>` 부분에서 타입을 받아와 내부에서 T 타입으로 지정한 멤버들에게 전파해 타입이 구체적으로 설정됩니다.
      - 이를 전문 용어로 구체화(Specialization)이라고 합니다.
    - 타입 파라미터 생략
      - JDK 1.7 버전 이후부터 new 생성자 부분의 제네릭 타입을 생략할 수 있게 되었다.
      - Ex) `A<String> gener = new A<생략>();`
    - 다형성 원리 적용
      - 타입 파라미터로 클래스 타입이 오기 때문에, 클래스끼리 상속을 통해 다형성 원리가 그대로 적용됩니다.
      - 즉, 업캐스팅을 통해 자식 객체도 할당이 가능합니다.
      - Ex)
        ```java
            A<Fruit> list = new ArrayList<>();
            list.add(fruit);  // O
            list.add(apple);  // O
            list.add(banana);  // O
        ```
    - 복수, 중첩 타입 파라미터 가능
      - 복수 타입 파라미터 : FruitBox<T, U>
      - 중첩 타입 파라미터 : List<ArrayList<String>>
    - 타입 파라미터 기호 네이밍
      - 명명하고 싶은대로 아무 단어나 넣어도 되지만, 통상적인 네이밍으로 다음과 같이 정해져있다.
      - `<T>` : Type
      - `<E>` : Element - Ex) List
      - `<K>` : Key - Ex) Map<K, V>
      - `<V>` : Variable - 반환 값 또는 매핑된 값
      - `<N>` : Number
      - `<S, U, V>` : 2, 3, 4번째에 선언된 타입
  </details>
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
  - Permanent, Metaspace 영역 차이에 대해 설명해주세요.
  - Java 8 이후 Permanent 영역이 왜 사라졌을까요?
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
- [https://gyoogle.dev/blog/](https://gyoogle.dev/blog/)
- [https://steady-coding.tistory.com/](https://steady-coding.tistory.com/)
- [변수는 어디에 저장되는가?](https://velog.io/@this-is-spear/%EA%B7%B8%EB%9E%98%EC%84%9C-static-%EB%B3%80%EC%88%98%EB%8A%94-%EC%96%B4%EB%94%94%EC%97%90-%EC%A0%80%EC%9E%A5%EB%90%98%EB%8A%94%EA%B0%80)
- [https://incheol-jung.gitbook.io/docs/q-and-a/java/static](https://incheol-jung.gitbook.io/docs/q-and-a/java/static)
- [자바 8부터 static이 Heap 영역에 저장된다.](https://jgrammer.tistory.com/entry/JAVA-Java8%EB%B6%80%ED%84%B0%EB%8A%94-static%EC%9D%B4-heap%EC%98%81%EC%97%AD%EC%97%90-%EC%A0%80%EC%9E%A5%EB%90%9C%EB%8B%A4)

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
