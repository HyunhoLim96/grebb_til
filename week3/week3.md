# 1. JWT(Json Web Token)
 - Json를 이용해 사용자 정보를 저장하는 claims 기반 web token
 - Header, Payload, Signature로 이루어져 있으며 '.' 으로 구분
### Header
토큰과 사용하는 알고리즘 타입을 지정
### Payload
토큰 제목, 발급자, 만료일 등 토큰에 대한 정보를 포함
### Signature
BASE64URL방식으로 인코딩한 Header와 Payload를 Secret Key와 함께 다시 인코딩하여 생성

# 2. Optional
NullPointerException을 방지하기 위해 null이 올 수 있는 값을 감싼 Wrapper Class

### Not Null
Optional.of() 메소드를 통해 생성
### Nullable
Optional.ofNullable() 메소드를 통해 생성
### Null 처리
.orElse(), .orElseThrow()를 통해 null을 처리할 수 있다.

# 3. Stream
 - 컬렉션(배열 포함)의 저장 요소를 하나씩 참조해서 람다식으로 처리할 수 있도록 해주는 반복자
 - 중간연산, 최종연산
### findFirst(), findAny() 차이
 - 직렬연산에서는 두 메소드 모두 가장 먼저 찾은 값을 반환
 - 병렬연산에서 findAny는 가장 먼저 찾은 값을 반환하는 반면, findFirst는 발견한 값들 중 스트림 순으로 가장 빠른 값을 반환
