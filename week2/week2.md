# [2주차] 실시간 세션 자료 및 미션

## 2주차 학습 미션

### 1. Spring WebFlux
Spring Webflux는 기존 SpringMVC에서 비동기, Reactive Streams back pressure를 지원한다.

- reactive-stack web module
- spring framework 5에서 사용
- rxJava, coroutines(kotlin)과 함께 이용
- 서비스간 호출이 많은 MSA 아키텍쳐에 용이
- 목적
    - 적은 양의 스레드로 동시성 핸들링
    - 함수형 프로그래밍 사용 위해

**[WebFlux vs MVC]**

**MVC** 
• 동기적 블로킹
• (동기) 호출과 응답이 동시에 이뤄지며, (블로킹) 함수가 종료될 때까지 다음 코드가 실행되지 않는, wait 시키는 방식
• 요청마다 스레드 생성, 효율성 위해 스레드 풀 이용.
• 동시에 여러 요청이 들어온다면 리소스 많이 사용 혹은 스레드 풀에 부담
• Thread Pool : 미리 설정해둔 개수만큼 스레드를 생성해두는 방식, 준비된 상태
    ◦ 기능 저하 방지, 다수 요청 처리 위해 사용
    ◦ pool 사이즈를 잘 조절하여 모든 스레드가 바쁘게 일할 수 있도록 해야함 → load balance

**WebFlux**
• 비동기적 논블로킹
• (비동기) 호출과 처리응답의 시점이 다르며, (논블로킹) 함수가 처리를 응답할 때까지 기다리지 않고 다음 코드 실행하는 방식
• 이벤트 루프 돌면서 요청이 발생할 경우, 핸들러에게 요청 처리를 위임하며, 완료되면 callback 응답
    ◦ 동시에 여러 요청 부담 없이 처리 가능
    ◦ 모든 코드가 논블로킹이어야 의미 있음
    ◦ 반응현 라이브러리 필요 ex. RXJava

netty : async-non blocking server

### 2. REST API
**REST API 디자인 가이드**
1. URI는 정보의 자원을 표현
2. 자원에 대한 행위는 HTTP Method(GET, POST, PUT, DELETE)로 표현
```
GET /members/delete/{id} 잘못된점 : URI는 정보의 자원을 표시, 행위에 대한 표현이 들어가서는 안됨
->
DELETE /members/{id} HTTP Method를 통해 행위를 표현
```
**HTTP METHOD별 역할**
|METHOD|역할|
|---|---|
|POST| 리소스 생성|
|GET|리소스 조회|
|PUT|리소스 수정|
|DELETE|리소스 삭제|

### 3. Functional Programming
