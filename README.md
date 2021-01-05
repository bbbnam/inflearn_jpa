##JPA에서 가장 중요한 2가지
- 객체와 관계형 데이터 베이스 매핑하기
- 영속성 컨텍스트

##영속성 컨텍스트
- 엔티티를 영구 저장하는 환경
- 논리적인 개념
- em.persist(entity) <- 실제 DB에 저장하는게 아니라 영속성 컨텍스트에 저장하는 것임.
실제 DB에 날아가는건  commit 할 때임

##준영속
- 영속성 컨텍스트에서 분리한 상태   
- ex> em.detach(member)