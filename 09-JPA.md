<!--
<details>
  <summary><h3></h3></summary>

  ---

  <details>
    <summary></summary>
  </details>
</details> 
-->

## JDBC, MyBayis(SQL Mapper), JPA(ORM), Hibernate

<details>
  <summary><h3>JDBC(Java Database Connectivity)란 무엇인가요?</h3></summary>

  - 자바에서 데이터베이스에 접속할 수 있도록 하는 자바 API입니다.
  - 이를 통해 자바 프로그램은 SQL을 사용해 데이터베이스와 상호작용할 수 있습니다.
  - JDBC는 각종 SQL 명령을 수행하고, 그 결과를 받아 처리하는 기능을 제공합니다.

  ---

  <details>
    <summary>JDBC의 이점에 대해 설명해주세요.</summary>

    JDBC는 JDBC 표준 인터페이스를 이용해 각 데이터베이스에 맞도록 JDBC 드라이버를 구현하여,
    데이터베이스와 커넥션 연결, SQL 전달 및 결과 응답 기능들을 제공합니다.
    이로 인해, 특정 데이터베이스 언어에 종속되지 않게 해줍니다.    
  </details>
  <details>
    <summary>Connection Pool에 대해 설명해주세요.</summary>
  </details>
    <details>
    <summary>HikariCP에 대해 설명해주세요.</summary>
  </details>
</details> 

<details>
  <summary><h3>ORM(Object Relational Mapping)이란 무엇인가요?</h3></summary>

  - ORM은 객체지향 프로그래밍 언어를 사용해 호환되지 않는 시스템 간에 데이터를 매핑해주는 도구입니다.
  - 즉, 객체와 데이터베이스 테이블 간의 매핑을 도와줍니다.
  - 이를 통해 개발자는 SQL을 직접 다루지 않고도 데이터베이스를 CRUD 작업을 수행할 수 있습니다.

  ---
  
  <details>
    <summary>JPA와 Hibernate란 무엇인가요?</summary>

    JPA는 자바 ORM 기술에 대한 표준 API 명세이기 때문에, JPA를 사용하려면 JPA를 구현한 ORM 프레임워크를 선택해야 합니다.
    자바 진영에 다양한 ORM 프레임워크 중 대표적으로 사용되는 것이 바로 하이버네이트입니다.    
  </details>
  <details>
    <summary>MyBatis에 대해 설명해주세요.</summary>
  
    - MyBatis는 SQL Mapper로 JPA와 달리 데이터베이스와 상호작용을 위해 개발자가 직접 SQL을 작성해서 사용해야 합니다.
    - 따라서, 최적화된 쿼리를 직접 구현할 수 있고 엔티티에 종속받지 않으면서 다양한 테이블을 조합할 수 있습니다.
    - 하지만 직접 쿼리를 작성해야 하고 데이터 매핑을 위해 XML 또는 어노테이션을 사용해야 합니다.
    - 때문에, 지루하고 반복적인 코드를 작성하게 되고 최종적으로 SQL에 종속적이게 됩니다.

    DB와 상호작용 방식
      - MyBatis : 개발자가 직접 SQL 작성하며 데이터 매핑을 위해 XML or 어노테이션 사용
      - JPA : 객체와 관계형 데이터베이스 간의 매핑을 제공하며 JPQL을 사용      
  </details> 
  <details>
    <summary>SQL 중심적인 개발의 문제점에 대해 설명하세요.</summary>

    SQL에 의존적인 개발이 되기 때문에, 비지니스 로직이 SQL에 종속적이게 됩니다.
    즉, SQL에 의존적인 상황에서 개발자들이 엔티티를 신뢰하고 사용할 수 없게 됩니다.
    예를 들어, SQL 변경 시, 자바 코드도 변경해야 하므로 유지보수도 어려워집니다.
    
    최종적으로 패러다임 불일치 문제가 발생합니다. 객체지향 프로그래밍과 관계형 데이터베이스는 서로 다른 패러다임을 가지고 있습니다. 
    이 둘의 차이를 중앙에서 해결해주지 않으면 개발자가 많은 코드를 작성해야 하며, 복잡성이 증가합니다.
  </details>
  <details>
    <summary>JPA ORM을 왜 사용해야 할까요?</summary>

    데이터베이스 설계 중심의 패러다임을 객체 설계 중심으로 역전시킬 수 있기 때문에, 지루하고 반복적인 쿼리 작성을 JPA가 대신 처리해줍니다.
    이처럼 패러다임 불일치 문제가 자연스레 해결되면서 유지보수성이 향상됩니다.
    또한 JPA는 데이터베이스 사이에 추상화된 데이터 접근 계층을 제공해 특정 데이터베이스 언어에 종속되지 않게 됩니다.
    그 외에도 다양한 성능 최적화 기능을 제공하기 때문에, 성능면에서도 이점이 있습니다.
  </details>
  <details>
    <summary>JPQL(Java Persistence Query Language)이란 무엇인가요?</summary>

    JPQL은 SQL과 비슷한 문법을 가지고 있지만, JPQL은 엔티티 객체를 대상으로 쿼리를 수행합니다. 
    또한 JPQL은 SQL을 추상화하여 특정 데이터베이스에 의존되지 않기 때문에, 데이터베이스 방언이 바뀌어도 수정하지 않아도 됩니다.
    이를 통해 SQL과 같은 데이터베이스 테이블이 아닌 자바 객체에 집중할 수 있습니다. 즉, JPQL은 객체지향 쿼리라고 할 수 있습니다.
  </details>
</details>

## 영속성 컨텍스트

<details>
  <summary><h3>영속성 컨텍스트란 무엇인가요?</h3></summary>

  ---

  <details>
    <summary>영속성은 어떤 기능을 하나요?</summary>
  </details>
  <details>
    <summary>영속성은 정말 성능 향상에 큰 도움이 되나요?</summary>
  </details>  
  <details>
    <summary>영속성 컨텍스트의 이점 5가지를 설명해주세요.</summary>
  </details>
  <details>
    <summary>엔티티 생명주기를 설명해주세요.</summary>
  </details>
  <details>
    <summary>플러시란 무엇인가요?</summary>
  </details>  
  <details>
    <summary>준영속 상태에 대해 설명해주세요.</summary>
  </details>
</details>


<details>
  <summary><h3>프록시 객체에 대해 설명해주세요.</h3></summary>

  ---

  <details>
    <summary>즉시 로딩과 지연 로딩에 대해 설명해주세요.</summary>
  </details>
  <details>
    <summary>영속성 전이에 대해 설명해주세요.</summary>
  </details>
  <details>
    <summary>고아 객체에 대해 설명해주세요.</summary>
  </details>
  <details>
    <summary>N + 1 문제 무엇인지 원인과 해결방안을 함께 설명해주세요.</summary>
  </details>   
</details>

<details>
  <summary><h3>@Transactional 어노테이션은 어떤 기능을 하나요?</h3></summary>

  ---

  <details>
    <summary>@Transactional(readonly=true)는 어떤 기능인가요?</summary>
  </details>
  <details>
    <summary>읽기에 트랜잭션을 걸 필요가 있을까요? @Transactional 어노테이션을 안 붙이면 되지 않을까요?</summary>
  </details>  
  <details>
    <summary>JPA Propagation 전파 단계를 설명해주세요.</summary>
  </details>
  <details>
    <summary>OSIV에 대해 설명해주세요.</summary>
  </details> 
</details>

## Reference

- [https://www.inflearn.com/course/ORM-JPA-Basic](https://www.inflearn.com/course/ORM-JPA-Basic)
- [https://hongguri.tistory.com/](https://hongguri.tistory.com)
- [https://code-lab1.tistory.com/](https://code-lab1.tistory.com/)
