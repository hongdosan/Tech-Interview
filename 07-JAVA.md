## Java

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
  <summary><h3>1. JVM이 정확히 무엇이고, 어떤 기능을 하는지 설명해 주세요.</h3></summary>
<ul>
<li> 그럼, 자바 말고 다른 언어는 JVM 위에 올릴 수 없나요?</li>
<li> 반대로 JVM 계열 언어를 일반적으로 컴파일해서 사용할 순 없나요?</li>
<li> VM을 사용함으로써 얻을 수 있는 장점과 단점에 대해 설명해 주세요.</li>
<li> JVM과 내부에서 실행되고 있는 프로그램은 부모 프로세스 - 자식 프로세스 관계를 갖고 있다고 봐도 무방한가요?</li>
</ul>
</details>

<details>
  <summary><h3>2. final 키워드를 사용하면, 어떤 이점이 있나요?</h3></summary>
<ul>
<li> 그렇다면 컴파일 과정에서, final 키워드는 다르게 취급되나요?</li>
</ul>
</details>

<details>
  <summary><h3>3. 인터페이스와 추상 클래스의 차이에 대해 설명해 주세요.</h3></summary>
<ul>
<li> 왜 클래스는 단일 상속만 가능한데, 인터페이스는 2개 이상 구현이 가능할까요?</li>
</ul>
</details>

<details>
  <summary><h3>4. 리플렉션에 대해 설명해 주세요.</h3></summary>
<ul>
<li> 의미만 들어보면 리플렉션은 보안적인 문제가 있을 가능성이 있어보이는데, 실제로 그렇게 생각하시나요? 만약 그렇다면, 어떻게 방지할 수 있을까요?</li>
<li> 리플렉션을 언제 활용할 수 있을까요?</li>
</ul>
</details>

<details>
  <summary><h3>5. static class와 static method를 비교해 주세요.</h3></summary>
<ul>
<li> static 을 사용하면 어떤 이점을 얻을 수 있나요? 어떤 제약이 걸릴까요?</li>
<li> 컴파일 과정에서 static 이 어떻게 처리되는지 설명해 주세요.</li>
</ul>
</details>

<details>
  <summary><h3>6. Java의 Exception에 대해 설명해 주세요.</h3></summary>
<ul>
<li> 예외처리를 하는 세 방법에 대해 설명해 주세요.</li>
<li> CheckedException, UncheckedException 의 차이에 대해 설명해 주세요.</li>
<li> 예외처리가 성능에 큰 영향을 미치나요? 만약 그렇다면, 어떻게 하면 부하를 줄일 수 있을까요?</li>
</ul>
</details>

<details>
  <summary><h3>7. Synchronized 키워드에 대해 설명해 주세요.</h3></summary>
<ul>
<li> Synchronized 키워드가 어디에 붙는지에 따라 의미가 약간씩 변화하는데, 각각 어떤 의미를 갖게 되는지 설명해 주세요.</li>
<li> 효율적인 코드 작성 측면에서, Synchronized는 좋은 키워드일까요?</li>
<li> Synchronized 를 대체할 수 있는 자바의 다른 동기화 기법에 대해 설명해 주세요.</li>
<li> Thread Local에 대해 설명해 주세요.</li>
</ul>
</details>

<details>
  <summary><h3>8. Java Stream에 대해 설명해 주세요.</h3></summary>
<ul>
<li> Stream과 for ~ loop의 성능 차이를 비교해 주세요,</li>
<li> Stream은 병렬처리 할 수 있나요?</li>
<li> Stream에서 사용할 수 있는 함수형 인터페이스에 대해 설명해 주세요.</li>
<li> 가끔 외부 변수를 사용할 때, final 키워드를 붙여서 사용하는데 왜 그럴까요? 꼭 그래야 할까요?</li>
</ul>
</details>

<details>
  <summary><h3>9. Java의 GC에 대해 설명해 주세요.</h3></summary>
<ul>
<li> finalize() 를 수동으로 호출하는 것은 왜 문제가 될 수 있을까요?</li>
<li> 어떤 변수의 값이 null이 되었다면, 이 값은 GC가 될 가능성이 있을까요?</li>
</ul>
</details>

<details>
  <summary><h3>10. equals()와 hashcode()에 대해 설명해 주세요.</h3></summary>
<ul>
<li> 본인이 hashcode() 를 정의해야 한다면, 어떤 점을 염두에 두고 구현할 것 같으세요?</li>
<li> 그렇다면 equals() 를 재정의 해야 할 때, 어떤 점을 염두에 두어야 하는지 설명해 주세요.</li>
</ul>
</details>

<details>
  <summary><h3>17. Java 에서 Annotation 은 어떤 기능을 하나요?</h3></summary>

  - 어노테이션은 자바 소스 코드에 메타데이터를 제공하는 방법입니다. 
  - 이는 코드의 의미를 설명하거나, 컴파일 시점이나 실행 시점에 특정 기능을 수행하도록 정보를 제공합니다. 
  - 예를 들어, @Override 어노테이션은 메서드가 상위 클래스의 메서드를 오버라이드한다는 것을 컴파일러에게 알려줍니다.
  - 예를 들어, @Autowired 어노테이션은 스프링 프레임워크에게 의존성 주입을 요청합니다.

  ---

  - 별 기능이 없는 것 같은데, 어떻게 Spring 에서는 Annotation 이 그렇게 많은 기능을 하는 걸까요?</li>
  - Lombok의 @Data를 잘 사용하지 않는 이유는 무엇일까요?
</details>
