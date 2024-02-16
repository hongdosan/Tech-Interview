<!--
<details>
  <summary><h3></h3></summary>

  ---

  <details>
    <summary></summary>
  </details>
</details> 
-->

## JPA 기본 - JDBC, SQL Mapper, ORM, Hibernate

<details>
  <summary><h3>JDBC(Java Database Connectivity)란 무엇인가요?</h3></summary>

  - 자바와 데이터베이스를 연결하기 위한 Java 표준 인터페이스입니다.
  - MySQL, PostgreSQL, SQL Server 등 다양한 DB 미들웨어의 드라이버를 제공합니다.
  - Java 표준이기 때문에, JVM 위에서 운영되는 모든 애플리케이션에서 사용 가능합니다.

  ---

  <details>
    <summary>JDBC을 사용하기 위해 해야하는 동작을 말해주세요.</summary>

    1. 가장 먼저 사용할 DB Driver를 선택합니다.
    2. 드라이버를 선택 후 커넥션 객체를 통해 데이터베이스와 연결합니다.
    3. SQL 쿼리를 실행하기 위해 Statement 객체를 생성합니다.
    4. 쿼리 실행 후 ResultSet 객체를 통해 받습니다.
    5. 마지막으로 커넥션 종료 시에는 메모리 누수 방지를 위해 리소스를 명시적으로 해제해야 합니다.
       예를 들어, Statement, Connection, ResultSet을 close() 메서드로 닫아야 합니다.
  </details>

  <details>
    <summary>JDBC의 단점에 대해 설명해주세요.</summary>

    단점
      - 리소스를 명시적으로 해제해야 합니다. 예를 들어, 커넥션 종료 시, 
        Statement, Connection, ResultSet 모두 close() 메서드로 종료해야 메모리 누수가 발생하지 않습니다.
      - 간단한 SQL 실행에도 중복된 코드가 반복적으로 사용됩니다.
      - DB에 따라 일관성없는 정보를 가진 채 Checked Exception으로 처리됩니다.
      
      - CheckedException
        - RuntimeException을 상속받지 않는 클래스 (ex: IOException, SQLExceptin, InterrupedException)
        - 컴파일 시점에 컴파일러를 확인하는 예외이기 때문에, 반드시 에외 처리를 해야 한다.
      - UncheckedException
        - RuntimeException을 상속하는 클래스 (ex: NPE)
        - 런타임 시점에 확인이 가능한 예외이기 때문에, 예외 처리를 강제하지 않는다.
  </details>
  <details>
    <summary>Spring JDBC에 대해 설명해주세요.</summary>

    - Spring JDBC는 스프링 프레임워크에서 제공하는 JDBC 기반의 데이터 액세스 기술입니다. 
    - Spring JDBC는 JDBC를 보다 쉽고 효율적으로 사용할 수 있도록 추상화된 기능을 제공하는데, 
      이를 통해 개발자는 반복적이고 번거로운 JDBC 작업을 간소화하고 생산성을 향상시킬 수 있다.
  </details>
  <details>
    <summary>Spring JDBC 장단점을 설명하세요.</summary>

    장점
      1) Spring JDBC는 자동으로 데이터베이스 연결, SQL 쿼리, ResultSet을 관리하고 닫아주기 때문에 
         코드를 간소화하고 메모리 누수를 방지합니다.
      2) Spring JDBC는 CheckException을 모두 UncheckedException으로 변환해 예외 처리 코드를 단순화해줍니다.
      3) Spring JDBC는 JdbcTemplate 등과 같은 다양한 템플릿과 헬퍼 클래스를 제공해 반복적인 코드를 줄이고
         데이터베이스 작업도 효율적으로 만들어줍니다. (헬퍼 클래스 : 도움을 주는 클래스)
    단점
      1) 단, 동적 SQL 쿼리를 처리하기 어렵습니다.
      2) 또한 IF 문이나, Switch Case로 인해 코드가 길어지고 지저분해질 수 있습니다.
  </details>
  <details>
    <summary>JdbcTemplate 기능에 대해 설명하세요.</summary>

    1) SQL 실행
      - 간단한 방식으로 SQL 문을 실행할 수 있습니다. 
      - 예를 들어, execute() 메서드를 사용하여 INSERT, UPDATE, DELETE 등의 작업을 실행할 수 있습니다.
      - 예를 들어, query() 메서드를 사용하여 SELECT 문을 실행하고 결과를 반환할 수 있습니다.
    2) PreparedStatement 자동 처리
      - PreparedStatement를 사용하여 SQL 문을 실행합니다.
      - 또한 JdbcTemplate이 자동으로 PreparedStatement를 생성하고 파라미터 값을 설정하기 때문에, SQL 인젝션 공격을 방지할 수 있습니다.
    3) ResultSet 매핑
      - ResultSet을 자동으로 자바 객체로 매핑해줍니다.
      - RowMapper 인터페이스를 구현하여 ResultSet의 각 행을 객체로 변환할 수 있습니다.
    4) 트랜잭션 관리
      - 트랜잭션 경계 설정, 롤백, 커밋 등의 작업을 편리하게 처리할 수 있습니다.
      - @Transactional 어노테이션을 사용하여 메서드 레벨에서 트랜잭션을 선언할 수도 있습니다.
    5) 예외 처리 및 자원 관리
      - JDBC 작업에서 발생하는 예외를 일관되게 처리하고, 연결 및 리소스 관리를 자동으로 처리합니다.
      - 즉, 예외 발생 시, 일관된 예외 계층 구조를 사용하여 예외를 처리할 수 있고, 자원의 올바른 해제를 보장합니다.
  </details>
  <details>
    <summary>Connection Pool에 대해 설명해주세요. (답변 미작성)</summary>
  </details>
  <details>
      <summary>HikariCP에 대해 설명해주세요. (답변 미작성)</summary>
  </details>
</details> 

<details>
  <summary><h3>SQL Mapper에 대해 설명해주세요.</h3></summary>

  - 객체와 SQL의 필드를 매핑해 데이터를 객체화하는 기술입니다.
  - 이는 객체와 테이블 간 관계를 매핑하는 것이 아니라, SQL문을 직접 작성하여 쿼리 수행 결과를 어떤 객체에 매핑하는 것을 말합니다.
  - 예를 들어, JDBCTemplate 혹은 MyBatis를 의미합니다.

  ---

  <details>
    <summary>MyBatis에 대해 설명하세요.</summary>

    - MyBatis는 자바 언어를 위한 데이터 매퍼 프레임워크입니다.
    - Spring JDBC는 코드에 직접 쿼리를 작성하지만 MyBatis는 XML 파일에서 SQL 쿼리를 관리하고
      SQL 결과와 객체 인스턴스의 매핑을 수행합니다.
  </details>
  <details>
    <summary>MyBatis 장/단점을 설명하세요.</summary>

    장점
      - 개발자가 SQL을 직접 작성하기 때문에, 세밀한 SQL 쿼리 최적화가 가능합니다.
      - 개발자가 복잡한 쿼리와 고급 데이터베이스 기능을 사용할 수 있습니다.
    단점
      - SQL을 개발자가 직접 작성하기 때문에, 지루하고 반복적인 코드를 작성해야합니다.
      - SQL 중심적인 개발을 하기 때문에, 객체와 관계형 테이블 구조간 패러다임 불일치 문제가 발생합니다.
      - DBMS에 종속적입니다.
  </details>
  <details>
    <summary>패러다임 불일치 문제는 무엇이 있나요?</summary>

    - 객체에는 상속 개념이 있지만 테이블에는 상속 개념이 존재하지 않습니다.
    - 객체는 연관 관계를 참조로 표현하고 테이블은 외래키로 표현합니다.
    - 객체는 그래프 탐색이 가능해야 하지만 테이블은 불가능합니다.
    - 객체는 동등성/동일성으로 비교하지만 테이블은 Row의 ID 값을 기준으로 조회합니다.
      - 동일성(Identity) : 두 객체가 완전히 같은 경우. 즉, 두 객체의 메모리 주소값이 같습니다.
      - 동등성(Equality) : 두 객체가 같은 정보를 갖고 있는 경우. 즉, 주소값이 달라도 값만 같으면 동등하다 표현합니다.
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
    <summary>현업에서는 JPA를 많이 사용하긴 하지만 아직까지 JDBCTemplate 혹은 Mybatis를 사용하는 곳이 많습니다. 그 이유가 무엇일까요?</summary>

    SQL Mapper는 개발자가 SQL을 직접 작성하기 때문에, 지루하고 반복적인 코드를 작성하긴 하지만,
    SQL 지식만 충분하다면, 세밀한 SQL 쿼리 최적화가 가능합니다. 
    또한 복잡한 쿼리를 짤 수 있고 고급 데이터베이스 기능을 사용할 수 있습니다.
    추가적으로 Entity 기준으로 동작하는 JPA보다 조회된 데이터를 바로 DTO로 변환해 응답하기가 편리하기 때문이라 생각합니다.
  </details>
</details>

<details>
  <summary><h3>ORM(Object Relational Mapping)이란 무엇인가요?</h3></summary>

  - 객체와 Database 테이블을 매핑하여 데이터를 객체화하는 기술입니다.
  - 즉, 객체지향 프로그래밍 언어를 사용해 데이터베이스를 관리할 수 있게 합니다.
  - 대표적으로 Hibernate가 있습니다.

  ---
  
  <details>
    <summary>JPA를 Hibernate와 함께 설명해주세요.</summary>

    - JPA는 자바 ORM 기술에 대한 표준 명세를 의미합니다.즉, ORM을 사용하기 위한 인터페이스를 모아둔 것으로 
      자바에서 관계형 데이터베이스를 어떻게 사용해야 하는 지 정의되어 있기만 하고 구현되어 있지 않습니다.
    - 이 JPA를 구현한 것이 바로 Hibernate입니다. 즉, 하이버네이트는 JPA를 구현한 ORM 프레임워크입니다.
      때문에 하이버네이트를 사용하면 SQL를 사용하지 않고 직관적인 메서드를 이용해 데이터를 조작할 수 있습니다.
      단, SQL을 사용하지 않는다고 해서 JDBC를 사용하지 않는 것은 아닙니다.
  </details>
  <details>
    <summary>Spring Data JPA란 무엇인가요?</summary>

    - Spring에서 제공하는 모듈 중 하나로 개발자가 JPA를 더 쉽고 편하게 사용할 수 있도록 도와줍니다.
    - 예를 들어 JPA를 한 단게 추상화시킨 Repository 인터페이스를 제공합니다.
  </details>
  <details>
    <summary>Spring Data JPA 장/단점을 설명하세요.</summary>

    장점
      - SQL을 직접 사용하지 않고 메서드 호출만으로 쿼리가 실행되어 생산성이 높고, 쿼리에 집중하기보다 비지니스 로직에 집중할 수 있습니다. 
        이는 결국 패러다임 불일치 문제도 자연스레 해결되면서 유지보수성도 향상됩니다.
      - 추상화된 데이터 접근 계층을 이용하기 때문에 Database에 종속되지 않습니다.
    단점
      - 효과적으로 사용하기 위해서 학습이 필요합니다.
      - 메서드 호출로 쿼리를 실행한다는 것은 내부 로직이 많다는 것이기 때문에, SQL을 직접 사용하는 것보다 성능이 떨어질 수도 있습니다.
      - 제대로 알고 사용하지 않으면, N + 1 문제와 같이 의도와 다르게 동작할 수 있습니다.
      - 자동화된 쿼리는 때로 최적화가 필요한 곳이나 복잡한 쿼리가 필요한 부분에서 비효율적일 수도 있습니다.
  </details>
</details>

## JPA 심화 - JPQL, 영속성 컨텍스트
<details>
  <summary><h3>@Transactional 어노테이션은 어떤 기능을 하나요? (답변 불충분)</h3></summary>

  - 해당 어노테이션을 메소드나 클래스에 적용하면 해당 메소드 혹은 클래스 내의 작업들이 하나의 트랜잭션으로 묶입니다.
  - 즉, @Transactional 어노테이션이 적용된 메소드에서 오류가 발생하면, 그 동안의 모든 데이터베이스 작업이 롤백되어 데이터의 일관성을 유지할 수 있습니다. 
  - 반대로 오류 없이 모든 작업이 성공적으로 마무리되면, 데이터베이스에 변경 사항이 커밋되어 반영됩니다.

  ---

  <details>
    <summary>@Transactional(readonly=true)는 어떤 기능인가요? (답변 불충분)</summary>

    이는 해당 트랜잭션이 읽기 전용이라는 것을 나타내는 것으로 데이터의 변경이 없는 조회 작업에 사용되며, 성능 최적화를 위해 사용됩니다. 
    일반적으로, 읽기 전용 트랜잭션에서는 더티 체킹 등의 불필요한 연산을 생략하여 처리 성능을 향상시킬 수 있습니다. 
  </details>
  <details>
    <summary>읽기에 트랜잭션을 걸 필요가 있을까요? @Transactional 어노테이션을 안 붙이면 되지 않을까요? (답변 불충분)</summary>

    읽기 작업에 대해 트랜잭션을 걸지 않으면, 데이터의 일관성을 보장할 수 없습니다. 
    동시에 다른 트랜잭션에서 데이터 변경이 일어날 경우, 읽기 작업 중인 트랜잭션에서는 변경 전의 데이터를 읽거나, 변경 중인 데이터를 읽는 등의 문제가 발생할 수 있습니다. 
    따라서 읽기 작업에도 트랜잭션을 걸어 데이터의 일관성을 보장하는 것이 중요합니다.
  </details>  
  <details>
    <summary>JPA Propagation 전파 단계를 설명해주세요. (답변 불충분)</summary>

    JPA Propagation은 트랜잭션 동작 도중 다른 트랜잭션을 호출하는 상황에 선택할 수 있는 옵션입니다.
    이는 @Transactional 어노테이션의 propagation 속성을 통해 설정하여 호출한 쪽의 트랜잭션을 그대로 사용할 수도 있고, 새롭게 트랜잭션을 생성할 수도 있습니다.

    예를 들어, 기본값은 REQUIRED로 부모 트랜잭션 내에서 실행하며 부모 트랜잭션이 없을 경우 새로운 트랜잭션을 생성합니다.
  </details>
  <details>
    <summary>OSIV에 대해 설명해주세요. (답변 미작성)</summary>
  </details> 
</details>

<details>
  <summary><h3>JPQL(Java Persistence Query Language)이란 무엇인가요?</h3></summary>

  - JPQL은 SQL과 비슷한 문법을 가지고 있지만, JPQL은 엔티티 객체를 대상으로 쿼리를 수행합니다. 
  - 또한 JPQL은 SQL을 추상화하여 특정 데이터베이스에 의존되지 않기 때문에, 데이터베이스 방언이 바뀌어도 수정하지 않아도 됩니다.
  - 이를 통해 SQL과 같은 데이터베이스 테이블이 아닌 자바 객체에 집중할 수 있습니다. 즉, JPQL은 객체지향 쿼리라고 할 수 있습니다.

  ---

  <details>
    <summary>JPQL 사용 시, 기존 영속성 컨텍스트의 데이터는 갱신될까요></summary>
  </details>
</details>

<details>
  <summary><h3>영속성 컨텍스트란 무엇인가요?</h3></summary>

  - 영속성 컨텍스트는 엔티티를 영구 저장하는 환경입니다.
    - 영속성 컨텍스트는 엔티티매니저를 통해 접근할 수 있습니다.
    - 예를 들어, EntityManager.persist() 메서드를 통해 영속성 컨텍스트에 엔티티를 저장할 수 있습니다.

  ---

  <details>
    <summary>영속성은 어떤 기능을 하나요? (답변 미작성)</summary>
  </details>
  <details>
    <summary>영속성은 정말 성능 향상에 큰 도움이 되나요? (답변 미작성)</summary>
  </details>  
  <details>
    <summary>영속성 컨텍스트의 이점 5가지를 설명해주세요.</summary>

    영속성 컨텍스트를 쓰는 이유는 1차 캐시, 동일성 보장, 쓰기 지연, 변경 감지, 지연로딩이 있습니다.

    - 1차 캐시: 
      - 엔티티 조회 시, 1차 캐시에 있다면 1차 캐시에서 조회하고 없다면 Database에서 조회 후 1차 캐시에 올립니다.
      - 1차 캐시가 REPEATABLE READ 격리 수준을 데이터베이스가 아닌 애플리케이션 차원에서 제공합니다.
    - 동일성(Identity, ==) 보장: 
      - 동일한 트랜잭션 내에서 동일성 비교가 가능합니다.
      - 영속성 컨텍스트는 특정 엔티티를 여러번 조회해도, 1차 캐시에 있는 동일한 엔티티를 반환하기 때문에 동일성이 보장됩니다.
    - 쓰기 지연:
      - 트랜잭션을 지원하는 쓰기 지연이 가능합니다.
      - 즉, SQL을 바로 보내지 않고 쓰기 지연 SQL 저장소에서 관리됩니다.
      - 쓰기 지연 SQL 저장소는 Flush 발생 시, 날라갑니다.
    - 변경 감지(Dirty checking): 
      - 플러시가 일어날 때, 1차 캐시에 들어있는 엔티티와 스냅샵을 비교해서 값이 다르면 쓰기 지연 저장소에 업데이트 쿼리를 저장합니다. 
        마지막으로 쓰기 지연 저장소 SQL을 데이터베이스에 전송하고 커밋이 완료됩니다.
      - 단, 변경 감지는 영속 상태의 엔티티에만 적용됩니다.
      - 스냅샷 : 값을 읽어온 최초 시점
    - 지연 로딩(Lazy Loading)
      - 엔티티가 실제 사용될 때까지 데이터베이스 조회를 지연한다.
      - 지연 로딩을 위해 실제 엔티티 대신 프록시 객체를 제공한다.
  </details>
  <details>
    <summary>엔티티 생명주기를 설명해주세요.</summary>

    - 비영속(new/transient)
      - 영속성 컨텍스트와 전혀 관계가 없는 상태
      - 즉, 순수한 객체 상태를 말한다.
    - 영속(managed)
      - 영속성 컨텍스트에 저장된 상태
      - 즉, 영속성 컨텍스트가 관리하는 엔티티를 말한다.
      - `EntityManager.persist(..);`, `EntityManager.find(..);`
    - 준영속(detached)
      - 영속성 컨텍스트에 저장됐다가 분리된 상태
      - `EntityManager.detach(..);`, `EntityManager.clear(..);`, `EntityManager.close(..);`
    - 삭제(removed)
      - 삭제된 상태.
      - 즉, 엔티티를 영속성 컨텍스트와 데이터베이스에서 삭제된 것을 말한다.
      - EntityManager.remove(..);
  </details>
  <details>
    <summary>플러시란 무엇인지 설명하고 플러시 발생 시, 일어나는 일을 설명하세요.</summary>

    플러시는 영속성 컨텍스트의 내용을 데이터베이스에 반영하는 것을 말합니다. 이때 영속성 컨텍스트를 비우지는 않습니다.
    즉, 영속성 컨텍스트의 내용을 데이터베이스와 동기화하는 것입니다.

    때문에, 플러시가 발생한다면 가장 먼저, 변경 감지가 일어납니다.
    그리고 변경된 것이 있다면, 데이터베이스에도 반영하기 위해 쓰기 지연 SQL 저장소에 해당 변경 쿼리를 추가합니다.
    마지막으로 쓰기 지연 저장소의 쿼리를 데이터베이스에 전송합니다.

    - 플러시 방법
      - EntityManager.flush() : 직접 호출
      - 트랜잭션 커밋 : 자동 호출
      - JPQL 쿼리 실행 : 자동 호출
  </details> 
</details>

<details>
  <summary><h3>지연로딩을 위한 프록시 객체 특징에 대해 설명해주세요. (답변 미작성)</h3></summary>

  ---

  <details>
    <summary>즉시 로딩과 지연 로딩에 대해 설명해주세요.(답변 불충분)</summary>

    - 즉시 로딩(EAGER LOADING)
      - 엔티티를 조회할 때 연관된 엔티티도 함께 조회합니다.
      - @ManyToOne(fetch = FetchType.EAGER)
      - 엔티티를 조회할 때 연관된 엔티티도 같이 조회하므로 쿼리를 2번 이상 실행할 것 같지만, 대부분 JPA는 즉시 로딩을 최적화하기 위해 가능하면 조인 쿼리를 사용합니다.
        때문에, 조인 쿼리를 사용하여 즉시 로딩할 때 null을 허용하면 외부 조인, null을 허용하지 않으면 내부 조인으로 됩니다.
    - 지연로딩(LAZY LOADING)
      - 연관된 엔티티를 실제 사용할 때 조회한다.
      - @ManyToOne(fetch = FetchType.LAZY)
      - 엔티티를 조회할 때 연관된 엔티티가 영속성 컨텍스트에 없다면, 프록시 객체로 조회하고 이 프록시 객체를 실제 사용할 때까지 데이터 로딩을 미룹니다.
  </details>
  <details>
    <summary>영속성 전이에 대해 설명해주세요. (답변 미작성)</summary>
  </details>
  <details>
    <summary>고아 객체에 대해 설명해주세요. (답변 미작성)</summary>
  </details>
  <details>
    <summary>N + 1 문제 무엇인지 원인과 해결방안을 함께 설명해주세요. (답변 미작성)</summary>
  </details>   
</details>

## Reference

- [https://www.inflearn.com/course/ORM-JPA-Basic](https://www.inflearn.com/course/ORM-JPA-Basic)
- [https://hongguri.tistory.com/](https://hongguri.tistory.com)
- [https://code-lab1.tistory.com/](https://code-lab1.tistory.com/)
