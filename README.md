# Tech-Interview

> 답변 정리 완료 및 진행 중인 아닌 Contents는 아직 건들지 않았기 때문에, VSFe 님의 2024.02.01 기준 포스팅과 동일합니다.
 
- 해당 포스팅은 VSFe 님의 [Tech-Interview](https://github.com/VSFe/Tech-Interview) 포스팅을 클론하여 개인적으로 커스텀하고 있는 저장소입니다.
- 계속해서 질문도 추가하며, 질문에 대한 답변도 정리하고 있습니다.

- 답변은 개인적인 공부 지식을 바탕으로 정리했기 때문에, 틀린 부분이 있을 수 있습니다.
- 잘못된 내용은 이슈와 PR로 알려주시면 감사하겠습니다.

- Tech-Interview에 합류하고 싶으신 분은 이슈로 알려주시면 감사하겠습니다.

## Contents

- [Java](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/01-JAVA.md)
- [Spring](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/02-SPRING.md)
- [JPA](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/03-JPA.md)
- [Database](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/04-DATABASE.md)
- [Network](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/05-NETWORK.md)
- [OS](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/06-OS.md)

## 답변 정리 완료

- v1.1.0 완료 : [Java](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/01-JAVA.md)
- v1.0.0 완료 : [Spring](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/02-SPRING.md)
- v1.0.0 완료 : [JPA](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/03-JPA.md)
- v1.0.0 완료 : [Network](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/05-NETWORK.md)
- v1.1.0 완료 : [OS](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/06-OS.md)
  
## 답변 정리 진행 중

- v1.2.0 진행 : [Java](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/01-JAVA.md)
- v1.1.0 진행 : [Network](https://github.com/HyuckJuneHong/Tech-Interview/blob/main/05-NETWORK.md)

# 📌 키워드 정리

> 이 키워드 정리는 황창현님의 [저장소](https://github.com/Hchanghyeon/computer-science-storage)를 참고한 정리입니다.

### 1️⃣ Java
- 객체지향
    - 4가지 특징
    - 5원칙 (SOLID)
    - 객체지향 vs 절차지향 vs 함수형 프로그래밍
- JDK, JRE, JVM
    - 컴파일 과정
    - 컴파일 언어 vs 인터프리터 언어
    - JVM 메모리 구조
    - Garbage Collector 동작과정
        - STW(Stop-The-World)
        - Parallel GC, G1 GC, ZGC
    - Java8의 큰 특징 + Java11과의 차이점
    - Java21
        - Virtual Thread
- Java 기초
    - 접근제어자
    - 클래스, 객체, 인스턴스 차이
    - primitive 타입들의 바이트 수
    - Overloading vs Overriding
    - Primitive type vs Reference type
        - Call by Reference vs Call by Value
        - Wrapper Class
    - interface vs abstract class
    - Checked Exception vs UnChecked Exception
    - static
    - final
    - generic
    - stream, lambda
        - map vs flatmap
    - Reflection & Dynamic Proxy
    - hashcode() & equals()
    - Thread Safe & Syncronized
        - Volatile
        - AtomicInteger
        - ReentrantLock
        - CAS(CompareAndSwap)
    - String
        - String vs StringBuffer vs StringBuilder
        - Immutable Object
        - `String a = ""` vs `String a = new String("")`
    - 직렬화, 역직렬화
    - try-with-resource
- Java 자료구조
    - Collection
    - List
        - Array vs ArrayList
        - ArrayList vs LinkedList
    - Map
        - HashTable vs HashMap vs LinkedHashMap vs TreeMap
        - HashMap vs ConcurrentHashMap
        - Hash Collision
    - Set
        - HashSet vs TreeSet vs SortedSet
    - Stack vs Queue vs Deque
    - Heap, Priority Queue
    - Tree, Binary Tree, Binary Search Tree, AVL Tree, Red Black Tree

### 2️⃣ Spring

- Servlet
    - 개념
    - Tomcat
        - Thread Per Request vs EventLoop
        - 동기 vs 비동기
    - Filter
    - Servlet Container
    - 동작과정
- Spring 기본
    - Spring vs Spring MVC vs Spring Boot
        - MVC1 vs MVC2
    - Dispatcher servlet
    - IoC
    - DI
    - Bean, Component
        - Bean Scope
        - `@Component` `@Service` `@Controller` `@ResponseBody`
        - 생성주기
        - 프로토타입 빈
        - Component와 Configuration의 차이
    - Container
    - VO vs DTO vs DAO
    - Maven, Gradle
- Spring 심화
    - `@Async`,`@EventListener`
    - AutoConfiguration
    - ObjectMapper
    - ControllerAdvice, ExceptionHandler
    - AOP
        - Spring AOP 어노테이션
        - JDK Dynamic Proxy
        - CGLIB
    - Interceptor
        - Filter와 차이점
    - Spring 전체 동작과정

- JPA
    - JDBC, Spring JDBC
    - Sql Mapper(MyBatis), ORM
    - @Transactional
    - JPA, Hibernate
    - 영속성 컨텍스트
    - 즉시/지연 로딩
    - 프록시
    - 고아객체
    - 단뱡향/양방향 매핑
    - N + 1 문제
        - BatchSize, EntityGraph, Fetch Join
- 테스트
    - DDD, TDD
    - Junit4 vs Junit5
    - 단위, 통합, 인수 테스트
    - stub, mock
    - SpringBoot 계층별 테스트 방법
    - 테스트 커버리지 (JACOCO)
- 기타
    - 2.x.x와 3.x.x 버전 차이



### 3️⃣ 데이터베이스(DB)
- 관계형 데이터베이스
    - 데이터베이스와 파일시스템의 차이
    - 관계형 데이터베이스의 개념과 장단점
    - DDL, DML, DCL, TCL
    - Key(Primary, Unique, Foreign)
- MySQL 아키텍처
    - innodb
    - 언두로그
    - 쿼리동작 방식
- Join
- 이상 현상과 정규화, 역정규화
- 트랜잭션
    - 트랜잭션 개념
    - ACID
    - Commit, Rollback
    - 트랜잭션 격리수준
    - LOCK, 교착상태
- 인덱스
    - 인덱스 개념
    - 인덱스 종류
    - Clustered index, Non-Clustered index, Covering index
    - 인덱스 자료구조(B-Tree 인덱스, B+Tree 인덱스)
- 옵티마이저
- 실행계획
- Master/Slave
- Sharding
- CAP 이론
- NoSQL
    - NoSQL의 개념
    - RDB VS NoSQL
    - Redis, Memcached
        - 캐싱 전략
- Elastic Search

### 4️⃣ 운영체제
- 운영체제 소개
    - 운영체제 필요성
    - 운영체제 정의
    - 운영체제 역할
- 운영체제 구조
    - 커널
    - 시스템 호출
- 프로세스
    - 프로세스 개념
    - 프로세스 상태
    - 프로세스 제어 블록
    - 프로세스 문맥 교환(컨텍스트 스위칭)
- 스레드
    - 스레드 개념
    - 멀티스레드의 구조
    - 멀티스레드의 장단점
    - 멀티 프로세스 VS 멀티 스레드
- CPU 스케줄링
    - 장기 스케줄링
    - 중기 스케줄링
    - 단기 스케줄링
- 스케줄링 알고리즘
    - FCFS
    - SJF
    - Round Robin
    - SRT
    - Priority scheduling
    - Multilevel Queue
    - Multilevel Feedback Queue
- 인터럽트
    - 인터럽트 개념
    - 동기적 인터럽트, 비동기적 인터럽트
    - 인터럽트 처리 과정
    - 인터럽트와 이중 모드
- 프로세스 동기화
    - 공유자원, 경쟁상태, 임계구역
    - 피터슨 알고리즘
    - 뮤텍스
    - 세마포어
    - 모니터
- 교착 상태(Deadlock)
    - 교착 상태 정의
    - 교착 상태 조건
    - 교착 상태 해결 방법
    - 식사하는 철학자 문제
- 메모리 관리
    - 메모리 관리 필요성
    - 고정 분할 방식
    - 가변 분할 방식
    - OOM
- 가상 메모리 개요
    - 가상 메모리 정의
    - 가상 메모리 필요성
    - 페이징 기법
    - 세그먼테이션 기법
- 가상 메모리 관리
    - 요구 페이징
    - 페이지 교체 알고리즘
        - FIFO
        - OPT
        - LRU

### 5️⃣ 네트워크 (Network)
- 네트워크 레이어
    - OSI 7계층
    - TCP/IP 4계층
    - IP
        - IPv4 vs IPv6
        - subnet
        - CIDR
- 통신
    - naver.com을 입력했을 때 일어나는 일
    - TCP
        - 흐름제어, 혼잡제어, 오류제어
        - 3-way-handshake, 4-way-handshake
    - UDP
    - HTTP
        - HTTP status code
        - HTTP method
        - HTTP 1.1, 2.0, 3.0
    - HTTPS, SSL/TSL, SSL Handshake
    - DNS
    - 기타 : socket, STOMP, SMTP (프로젝트에서 사용한 경우)
- Web
    - Web Server vs WAS
    - Web Server
        - apache vs nginx (동작원리)
        - SSL offloading
        - reverse proxy
        - load balancing
            - L7 vs L4
            - 알고리즘
    - Web cache
    - URI, URN, URL
    - Rest API
- 보안
    - CORS
    - XSS
    - SQL Injection
- 인증
    - cookie
    - session
    - JWT

### 6️⃣ 디자인 패턴
- 싱글톤 패턴
- 전략 패턴
- 빌더 패턴
- 팩토리 메서드 패턴
- 퍼사드 패턴
- 옵저버 패턴


