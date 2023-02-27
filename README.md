# ksqldb
ksqldb demo

# 아키텍처
![ksqldb-architecture-and-components](https://user-images.githubusercontent.com/5574171/221448147-2d41acf0-4fe3-422a-86d6-0de46119adc8.png)

# 스트림과 테이블
![kafka-streams-and-tables](https://user-images.githubusercontent.com/5574171/221450284-403bdff2-3dc8-4ace-a2bd-128b3342ec43.gif)

  * 스트림
    * immutable
    * insert 만 가능
    * history 성 데이터
  * 테이블
    * mutable
    * insert, update, delete 가능
    * state 성 데이터

# 스트림 생성
  CREATE STREAM LINE_1K_STREAM (
    TABLE_NM VARCHAR,
    OP_TYPE VARCHAR,
    OP_TS VARCHAR,
    CURRENT_TS VARCHAR,
    AFTER STRUCT<
      "TRAN_DT" VARCHAR,
      "CUS_NO" VARCHAR,
      "TRX_CD" VARCHAR
    >
  )
  WITH (
    KAFKA_TOPIC = 'line-1',
    VALUE_FORMAT = 'JSON'
  );
  
