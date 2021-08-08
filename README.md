# oracle
oracle 이모저모


## 맥 오라클 도커 연결
- sudo lsof -i:[포트번호] #49610 49611 확인후 kill
- docker run -d -p 49160:22 -p 49161:1521 deepdiver/docker-oracle-xe-11g // 도커연결
- ALTER USER <스키마이름> quota unlimited on <db연결 이름 ex) SYSTEM>;
