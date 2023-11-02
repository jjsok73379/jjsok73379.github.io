---
layout: default
title: mysql monitor
parent: 클라이언트
grand_parent: 데이터베이스와 MYSQL
nav_order: 1
---

# mysql monitor  
- mysql서버의 번들로 제공하는 기본 프로그램  
- 명령어 기반  

# 사용법  
mysql -u아이디 -p비밀번호  
mysql -h호스트주소 -p포트번호 -u아이디 -p비밀번호  

# 데이터베이스 생성  
```
CREATE DATABASE music CHARACTER SET utf8 COLLATE utf8_general_ci;
```  

# 생성된 데이터베이스 보기  
````
show databases;
````  

# 데이터베이스 선택  
```
use music;
```  

# 테이블 생성  
````
CREATE TABLE `favorite_music` (
  `title` varchar(255) NOT NULL,
  `musician` varchar(20) NOT NULL,
  `duration` varchar(20) NOT NULL,
  `album` varchar(30) NOT NULL
) ENGINE=innodb;
````  

# 테이블에 데이터 추가  
```
insert into favorite_music (`title`,`musician`, `duration`, `album`) values('Chasing Pavements', '아델', '3:30', 19);
```  

# 입력된 데이터 조회  
````
select * from favorite_music;
````  

# 종료
```  
exit;
```