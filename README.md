# oracle
oracle 이모저모


## 맥 오라클 도커 연결
- sudo lsof -i:[포트번호] #49160 49161 확인후 kill
- docker run -d -p 49160:22 -p 49161:1521 deepdiver/docker-oracle-xe-11g // 도커연결
- 로컬에 db 공유를 하면 도커 재실행시 데이터 증발 사라진다 -> -v <localpath>:/var/lib/oracle 옵션을 추가해준다 -->> 도커 옵션따라 input 값다름
    
- ALTER USER <스키마이름> quota unlimited on <db연결 이름 ex) SYSTEM>;
- ALTER USER ds quota unlimited on SYSTEM;


## dbeaver에서 csv to oracle
- 먼저 csv 파일을 업로드진행
- 테이블자체를 oracle로 덤프 -> 에러확률 낮음


## oracle 스키마 db 용량 업데이트
SELECT TABLESPACE_NAME, BYTES/1024/1024 AS MB, FILE_NAME    
FROM DBA_DATA_FILES  -> SYSTEM 경로확인
    
ALTER DATABASE DATAFILE 'PATH' RESIZE <limit size설정>    
- 4000m

## dbeaver 관련
- ctl + shift + e -> auto trace
- shift + 방향키 -> 탭이동
- option + x -> 쿼리실행
- ctl + ] -> sql 실행
    
    
## 저장을 위해 docker 실행 -> containers/apps 에서 실행 -> 데이터작업후 -> docker commit {image name}
