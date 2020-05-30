# 1.기본적인 내용

 - 분산 처리 종류
	 - 미들웨어 : Apache Hadoop
	 - 클라우드 서비스 : Amazon Redshift, Google BigQuery

- 용도
	- 개별적인 사용자의 행동 파악
	- 사용자의 흥미와 기호를 기반으로 하는 추천
	- 광고 타깃팅
	- 예측 모델링
	- 기계 학습

- 저장된 데이터에 접근하려면 빅데이터를 관리하는 미들웨어 부속 도구를 사용할 줄 알아야 함.
- Hadoop은 Hue, Amazon Redshift라면 Aginity 등
- 이 도구들을 이용하여 다양한 조건과 형식에 맞게 데이터 추출

---

# 2.시스템 종류
## 1) PostgreSQL
- PostgreSQL은 오픈소스 RDB(Relational Database)
- MySQL 등 다른 오픈소스 RDB에 비해 표준 SQL을 잘 준수
- 비교적 가볍게 동작하기 때문에 소규모의 데이터 분석, SQL 학습 목적으로 적합

## 2) Apache Hive
- Apache Hive (이하 Hive)는 HDFS(Hadoop File System)이라고 부르는 분산 파일 시스템 위의 데이터를 SQL스러운 인터페이스로 간단하게 처리해 주는 시스템
- 분산 파일 시스템은 거대한 데이터를 작게 분할해서 여러 개의 디스크에 분산해서 저장하고 각 디스크에서 동시에 데이터를 읽어 들여 고속으로 대량의 데이터를 처리하게 해줌
- 분산 파일 시스템 위의 데이터의 순서를 맞추느 방법으로 MapReduce라는 알고리즘이 있음
- HDFS와 MapReduce 아키텍처를 구현한 시스템이 초기의 Apache Hadoop
- Hive는 이 Hadoop 생태계의 일부분으로 HiveQL이라 부르는 SQL스러운 쿼리 언어로 작성한 쿼리를 자동적으로 변환해 간단하게 병렬 분산 처리를 해줌

## 3) Amazon Redshift
- Amazon Redshift는 AWS에서 제공하는 분산 병렬 RDB
- 레코드를 업데이터하거나 제거할 수 있고 트랜잭션 등도 지원
- 일반적이 RDB에서 다룰 수 없는 대량의 데이터와 상호 작용하는 쿼리를 실행하고 싶을 때 효과적
- 사용시간에 따라 비용이 발생함
- 성능 튜닝이나 비용을 줄이기 등 관리를 하려면 굉장히 전문적인 지식이 필요함

## 4) Google BigQuery
- Google BigQuery는 빅데이터 분석을 위해 구글이 제공하는 클라우드 서비스
- Redshift와 다르게 직접 노드 인스턴스를 관리할 필요가 없음
- 사용 시간이 아니라 읽어 들인 데이터의 양으로 비용이 발생
- 레거시 SQL과 표준 SQL 두 종류가 있음

## 5) SparkSQL
- SparkSQL은 MapReduce를 사용한 분산 처리 프레임워크인 Apache Spark의 기능 중에서 SQL 인터페이스와 관련된 기능을 나타내는 용어
- 무료임
- 오픈소스 제품 중 빠른 속도로 개발이 이루어질 수 있음
- 기계 학습, 그래프 처리, 실시간 스트리밍 등의 다양한 처리를 쉽게 분산 처리 할 수 있는 기능 등도 제공
- Spark는 인터페이스로 SQL, Python, R, Scala, Java 등 프로그래밍 언어를 지원하고 데이터 익스포트와 임포트 기능도 굉장히 다양하게 가지기 때문에 Spark 내부에서 데이터 추출 부터 전처리, 정제 등 한 번에 구현이 가능함

