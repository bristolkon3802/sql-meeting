# SQL
 - SQLite

***

## SQLite
- 다운로드 : https://www.sqlite.org/index.html
- Function 참조 : https://www.sqlite.org/lang_corefunc.html

1. 설치
  > PowerShell 관리자권한, choco 사용(BeekeeperStudio - db 실행도구)
  ```
  choco install sqlite
  sqlite3
  ```
2. 데이터베이스 생성
  ```
  E:file_name> New-Item hello_sql.db
  ```
3. 사용 방법
   - 테이블 생성
     ```
     -- name, type, constraint, NULL, 기본값 입력, 조건값
      CREATE TABLE movies (
        title TEXT UNIQUE NOT NULL, -- 유일한 값만 입력 
        released INTEGER NOT NULL CHECK (released > 0), -- 양수만 입력
        overview TEXT NOT NULL CHECK (LENGTH(overview) < 100), -- 100자 이하 확인
        rating REAL NOT NULL CHECK (rating BETWEEN 0 AND 10), -- 0~10 사이값
        director TEXT,
        for_kids INTEGER NOT NULL DEFAULT 0 CHECK (for_kids BETWEEN 0 AND 10) -- 0 or 1
        --poster BLOB -- byte를 저장할 수 있음(이미지 저장, 바이너리 데이터면 상관없음)
      ) STRICT;
     ```
   - 테이블 삭제
     ```
     DROP TABLE movies;
     ```
   - 데이터 입력
     ```
     INSERT INTO movies 
  	  (title, rating, released, overview, for_kids)
     VALUES
	    ('The Godfather', 7, 1,  'Rings and hobbits', 1);
     ```

4. 명령어 모음
   ```
   주석 : --, /**/
   ```
