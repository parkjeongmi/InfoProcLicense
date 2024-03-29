# Transaction

* 데이터베이스의 상태를 변환시키는 하나의 논리적 기능을 수행하기 위한 작업의 단위, 일련의 연산을 의미



## 1. 트랜잭션의 특성

* 원자성 (Atomicity)

  트랜잭션의 연산은 데이터베이스에 모두 반영되도록 완료(commit) 되거나 모두 반영되지 않도록 복구(Rollback) 되어야 함

* 일관성(Consistency)

  트랜잭션이 실행을 성공적으로 완료하면 언제나 일관성있는 데이터베이스 상태로 전환되어야 함

* 지속성(Durability)

  트랜잭션이 실행되면, 해당 시스템에 장애가 생겨도 그 결과는 일관되게 지속되어야 함

* 독립성(Isolation)

  둘 이상의 트랜잭션이 동시에 병행 실행되면, 한 트랜잭션 실행 중 다른 트랜잭션의 연산이 끼어들 수 없음

## 2. 병행제어

다중 프로그램의 이점을 활용해 동시에 여러 개의 트랜잭션을 병행 수행할 때 실행되는 트랜잭션들이 데이터베이스의 일관성을 파괴하지 않도록 트랜잭션 간의 상호 작용을 제어하는 기술

* 로킹 기법

  주요 데이터의 액세스를 상호 배타적으로 하는 것

  트랜잭션들이 어떤 로킹 단위를 액세스하기 전에 락을 요청해 락이 허락되어야만 그 로킹 단위를 액세스 할 수 있도록 하는 기법

* 2 Phase Loocking 기법

* 낙관적 검증기법

* Timestamp Ordering 기법

  직렬성 순서를 결정하기 위해 트랜잭션 간의 처리 순서를 미리 선택하는 기법 중 가장 보편적임

  트랜잭션과 트랜잭션이 읽거나 갱신한 데이터에 대해 트랜잭션이 실행을 시작하기 전에 시간표를 부여하여 부여된 시간에 따라 트랜잭션 작업을 수행하는 기법

* 다중버전동시성제어기법(MVCC)