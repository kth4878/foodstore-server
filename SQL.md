
```
CREATE TABLE `main_board` (
`branch` varchar(20) NOT NULL COMMENT '구분',
`name` varchar(100) DEFAULT NULL COMMENT '이름',
`use_yn` varchar(1) DEFAULT NULL COMMENT '사용 유무',
`created_name` varchar(100) DEFAULT NULL COMMENT '등록자 이름',
`created_date` datetime DEFAULT NULL COMMENT '등록 날짜',
`updated_name` varchar(100) DEFAULT NULL COMMENT '수정자 이름',
`updated_date` datetime DEFAULT NULL COMMENT '수정 날짜',
`reg_date` date DEFAULT NULL COMMENT '등록 년-월-일',
PRIMARY KEY (`branch`),
KEY `main_board_reg_date_IDX` (`reg_date`) USING BTREE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4



CREATE TABLE `main_board_log` (
  `branch` varchar(20) NOT NULL COMMENT '구분',
  `name` varchar(100) DEFAULT NULL COMMENT '이름',
  `use_yn` varchar(1) DEFAULT NULL COMMENT '사용 유무',
  `created_name` varchar(100) DEFAULT NULL COMMENT '등록자 이름',
  `created_date` datetime DEFAULT NULL COMMENT '등록 날짜',
  `updated_name` varchar(100) DEFAULT NULL COMMENT '수정자 이름',
  `updated_date` datetime DEFAULT NULL COMMENT '수정 날짜',
  `dml_type` varchar(50) NOT NULL COMMENT '등록, 수정, 삭제 구분',
  `created_log_date` datetime NOT NULL COMMENT '로그 생성 날짜',
  `reg_date` date DEFAULT NULL COMMENT '등록 년-월-일',
  PRIMARY KEY (`branch`),
  KEY `main_board_log_reg_date_IDX` (`reg_date`) USING BTREE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4



CREATE TABLE `member` (
  `email` varchar(100) NOT NULL COMMENT '이메일',
  `name` varchar(50) NOT NULL COMMENT '이름',
  `nickname` varchar(30) DEFAULT NULL COMMENT '닉네임',
  `role` varchar(10) DEFAULT NULL COMMENT '권한',
  `use_yn` varchar(1) DEFAULT 'Y' COMMENT '사용 유무',
  `created_date` datetime DEFAULT NULL COMMENT '등록 날짜',
  `updated_date` datetime DEFAULT NULL COMMENT '수정 날짜',
  PRIMARY KEY (`email`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4



CREATE TABLE `member_log` (
  `email` varchar(100) NOT NULL COMMENT '이메일',
  `first_login_date` datetime DEFAULT NULL COMMENT '첫 로그인 날짜',
  `last_login_date` datetime DEFAULT NULL COMMENT '마지막 로그일 날짜',
  PRIMARY KEY (`email`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4



CREATE TABLE `restaurant` (
  `name` varchar(100) NOT NULL COMMENT '음식점 이름',
  `address` varchar(255) NOT NULL COMMENT '주소',
  `owner_name` varchar(50) DEFAULT NULL COMMENT '대표자 이름',
  `business_type` varchar(255) DEFAULT NULL COMMENT '업종',
  `main_food` varchar(100) DEFAULT NULL COMMENT '메인 음식',
  `closed_yn` varchar(1) DEFAULT 'N' COMMENT '폐업 유무',
  `created_name` varchar(100) DEFAULT NULL COMMENT '등록자 이름',
  `cerated_date` datetime DEFAULT NULL COMMENT '등록 날짜',
  `updated_name` varchar(100) DEFAULT NULL COMMENT '수정자 이름',
  `updated_date` datetime DEFAULT NULL COMMENT '수정 날짜',
  PRIMARY KEY (`name`,`address`),
  KEY `restaurant_main_food_IDX` (`main_food`) USING BTREE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4



CREATE TABLE `restaurant_file` (
  `name` varchar(100) NOT NULL COMMENT '음식점 이름',
  `address` varchar(255) NOT NULL COMMENT '주소',
  `file_name` longtext DEFAULT NULL COMMENT '파일명',
  `file_path` longtext DEFAULT NULL COMMENT '파일 경로',
  `real_file_name` varchar(255) DEFAULT NULL COMMENT '실제 파일명',
  `created_name` varchar(100) DEFAULT NULL COMMENT '등록자 이름',
  `created_date` datetime DEFAULT NULL COMMENT '등록 날짜',
  PRIMARY KEY (`name`,`address`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4



CREATE TABLE `sub_board` (
  `id` bigint(20) NOT NULL COMMENT '글번호',
  `branch` varchar(20) NOT NULL COMMENT '상위 게시판 구분',
  `name` varchar(100) DEFAULT NULL COMMENT '이름',
  `notice_yn` varchar(1) DEFAULT 'N' COMMENT '공지사항 구분',
  `subject` varchar(100) DEFAULT NULL COMMENT '제목',
  `content` longtext DEFAULT NULL COMMENT '내용',
  `hits` bigint(20) DEFAULT 0 COMMENT '조회수',
  `recommend` bigint(20) DEFAULT 0 COMMENT '추천수',
  `created_name` varchar(100) DEFAULT NULL COMMENT '등록자 이름',
  `created_date` datetime DEFAULT NULL COMMENT '등록 날짜',
  `updated_name` varchar(100) DEFAULT NULL COMMENT '수정자 이름',
  `updated_date` datetime DEFAULT NULL COMMENT '수정 날짜',
  `reg_date` date DEFAULT NULL COMMENT '등록 년-월-일',
  PRIMARY KEY (`id`,`branch`),
  KEY `sub_board_reg_date_IDX` (`reg_date`) USING BTREE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4



CREATE TABLE `sub_board_log` (
  `id` bigint(20) NOT NULL COMMENT '글번호',
  `branch` varchar(20) NOT NULL COMMENT '상위 게시판 구분',
  `name` varchar(100) DEFAULT NULL COMMENT '이름',
  `notice_yn` varchar(1) DEFAULT 'N' COMMENT '공지사항 구분',
  `subject` varchar(100) DEFAULT NULL COMMENT '제목',
  `content` longtext DEFAULT NULL COMMENT '내용',
  `hits` bigint(20) DEFAULT 0 COMMENT '조회수',
  `recommend` bigint(20) DEFAULT 0 COMMENT '추천수',
  `created_name` varchar(100) DEFAULT NULL COMMENT '등록자 이름',
  `created_date` datetime DEFAULT NULL COMMENT '등록 날짜',
  `updated_name` varchar(100) DEFAULT NULL COMMENT '수정자 이름',
  `updated_date` datetime DEFAULT NULL COMMENT '수정 날짜',
  `dml_type` varchar(50) NOT NULL COMMENT '등록, 수정, 삭제 구분',
  `created_log_date` datetime NOT NULL COMMENT '로그 생성 날짜',
  `reg_date` date DEFAULT NULL COMMENT '등록 년-월-일',
  PRIMARY KEY (`id`,`branch`),
  KEY `sub_board_log_reg_date_IDX` (`reg_date`) USING BTREE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4
```
