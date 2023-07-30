# spring DB접근 기술

## H2데어터 베이스 설치 방법
### 1. [h2데이터 베이스 설치](https://www.h2database.com)에 접속하여 설치 후 압축  풀기
### 2. h2 bat를 실행한다
### 3. jdbc:h2:~/test로 접속한다
### 4. cmd에 dir를 입력 한뒤 ~/test.mv.db파일이 생기는지 확인한다
### 5. 이후부터는 충돌이 발생 할 수 있으니까 jdbc:h2:tcp://localhost/~/test로 접속한다
* 혹시 웹 브라우저가 실행이 안된다면 :8082앞에 숫자들을 localhost로 변경해주면 된다

