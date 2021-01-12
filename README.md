# JPA
## JPA에서 가장 중요한 2가지
- 객체와 관계형 데이터 베이스 매핑하기
- 영속성 컨텍스트

## 영속성 컨텍스트
- 엔티티를 영구 저장하는 환경
- 논리적인 개념
- em.persist(entity) <- 실제 DB에 저장하는게 아니라 영속성 컨텍스트에 저장하는 것임.
실제 DB에 날아가는건  commit 할 때임

## 플러시
- 영속성 컨텍스트의 변경내용을 데이터베이스에 반영
- "쓰기지연" Sql 저장소의 쿼리를 데이터 베이스에 전송

## 준영속
- 영속성 컨텍스트에서 분리한 상태   
- ex> em.detach(member)
- em.detach(entity)  : 특정 엔티티만 준영속 상태로 전환
- em.clear() : 영속성 컨텍스트를 완전히 초기화
- em.close() : 영속성 컨텍스트를 종료

## 데이터베이스 스키마 자동 생성
- 애플리케이션 실행 시점에 테이블을 생성 (운영에서 사용X, 개발에서만 써야함)

## 필드와 컬럼 매핑
- @Column : 컬럼 매핑
- @Temporal : 날짜 타입 매핑
- @Enumerated : enum 타입 매핑
- @Lob : BLOB, CLOB 매핑
- @Transient : 특정 필드를 컬럼에 매핑하지 않음(매핑 무시)

## 기본키 매핑
- 직접 할당 : @Id만 사용
- 자동 생성 : @GeneratedValue

순수 JPA를 쓸때에는 orderDate -> orderDate로 SQL로 그대로 가는데

스프링 부트를 쓰게 되면 orderDate -> order_date 로 변경되게끔 하는게 기본으로 된다.