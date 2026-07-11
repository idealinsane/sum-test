# sum-test

C++ 1부터 10까지 합을 출력하는 프로그램 및 Git 형상 관리 실습 과제입니다.

---

# 과제 요구사항

1. 1부터 10까지 합을 출력하는 프로그램을 작성하여라.
2. 실행 파일 이름은 sum-test로 한다.
3. sum-test 프로젝트를 git 사이트에 올린다.
4. 2번 이상 commit하도록 하여 git에서 변경 이력을 확인할 수 있도록 한다.
5. git에는 소스 코드(h, c, cpp)만 올리지 말고 프로젝트 파일(Makefile)도 같이 올릴 것.
6. 메일에는 코드 파일을 첨부하지 말고 git 주소만 알려줄 것.

---

# 과제 수행 보고서

- 수행자: 김민수 (취약점)
- GitHub 저장소 주소: https://github.com/idealinsane/sum-test

## 1. 개요 및 동작 원리
본 프로그램은 1부터 10까지의 정수 누적 합을 구하고 결과를 화면에 출력하는 C++ 프로그램입니다. 다중 소스 빌드를 위해 함수 선언(sum.h), 함수 정의(sum.cpp), 호출 부(main.cpp)로 소스를 분할하여 작성하였으며, 이를 자동 빌드하기 위해 Makefile을 구성하였습니다.

- sum: 인자로 전달된 정수 n까지 루프를 돌며 1부터 n까지의 누적 합을 계산하여 반환합니다.
- main: sum.h 헤더를 참조하여 sum(10)을 호출하고, 출력 포맷에 맞추어 printf("result=%d\n", s)로 결과를 출력합니다.
- Makefile: g++ 컴파일러를 이용하여 main.cpp와 sum.cpp를 각각 오브젝트 파일로 생성한 뒤 sum-test 실행 파일로 연결 및 빌드합니다.

## 2. Git 변경 이력 (Commit History)
과제 요구사항인 2회 이상의 커밋 규칙을 준수하여 4단계로 나누어 변경 내역을 관리했습니다.

- Commit 1: Add sum modules (sum.h, sum.cpp 추가)
- Commit 2: Add main.cpp (main.cpp 추가)
- Commit 3: Add Makefile (Makefile 추가)
- Commit 4: Add README.md (README.md 추가)

## 3. 실행 결과 검증
로컬 환경에서 컴파일을 수행하고 정상 결과를 도출했음을 검증했습니다.

```bash
$ make
g++ -c -o main.o main.cpp
g++ -c -o sum.o sum.cpp
g++ -o sum-test main.o sum.o

$ ./sum-test
result=55
```
