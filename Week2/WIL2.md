# 1. HTTP에 대해 정리하라

- ## HTTP란?
  
  HyperText Transfer Protocal의 약자.
  
  - Hypertext : 다른 페이지의 링크를 담고 있는 문서
    
  - Transfer : 이동 통신
    
  - Protocal : 규약
    
  
  서로 다른 시스템들 사이에서 통신을 주고 받게 해주는 application 계층의 protocol
  

- ## HTTP 특징
  
  - Transfer layer
    
    TCP/IP 기반으로 서버와 클라이언트 간의 요청&응답 전송
    
  - 비 연결성(connectionless)
    
    클라이언트와 서버가 한번 연결을 맺은 후, 클라이언트의 요청에 대해 서버가 응답을 마치면 연결 끊김
    
  - 무상태성(stateless)
    
    서버는 클라이언트와 연결에 대한 정보를 저장하지않음.
    
    서버는 클라이언트를 식별하지 못함.
    
- ## HTTP 연결
  
  1. TCP 연결을 열어줌. (새연결 혹은 기존 연결을 재사용 가능.)
    
  2. HTTP메세지 전송.
    
  3. 서버가 보낸 응답을 읽음.
    
  4. 연결을 닫거나 다른 요청을 위해 재사용.
    
- ## HTTP Message
  
  HTTP Message > request(요청) + response(응답)
  

- ## HTTP Method
  
  클라이언트가 서버에 특정 요청을 보낼때, 웹서버에게 요청하는 목적 및 그 종류를 알리는 수단으로 사용
  
  주로 밑 명령어 사용
  
  - GET: 리소스 조회
    
  - POST: 요청 데이터 처리, 주로 등록에 사용
    
  - PUT: 리소스를 대체, 해당 리소스가 없으면 생성
    
  - PATCH: 리소스 부분 변경
    
  - DELETE: 리소스 삭제
    

다음 내용은 위와는 다른 Method

- HEAD: GET과 동일하지만 메시지 부분을 제외하고, 상태 줄과 헤더만 반
  
- OPTIONS: 대상 리소스에 대한 통신 가능 옵션(메서드)을 설명(주로 CORS에서 사용)
  
- CONNECT: 대상 리소스로 식별되는 서버에 대한 터널을 설정
  
- TRACE: 대상 리소스에 대한 경로를 따라 메시지 루프백 테스트를 수행
  

- ## HTTP 상태 코드
  
  번호마다 가진 의미가 다름.
  
  - 1xx (Informational): 요청이 수신되어 처리중

- 2xx (Successful): 요청 정상 처리

- 3xx (Redirection): 요청을 완료하려면 추가 행동이 필요

- 4xx (Client Error): 클라이언트 오류, 잘못된 문법등으로 서버가 요청을 수행할 수 없음

- 5xx (Server Error): 서버 오류, 서버가 정상 요청을 처리하지 못함

아래는 자주 사용하는 HTTP 상태 코드

- 200 : 클라이언트의 요청을 정상적으로 수행함

- 201 : 클라이언트가 어떠한 리소스 생성을 요청, 해당 리소스가 성공적으로 생성됨(POST를 통한 리소스 생성 작업 시)

- 204 : 클라이언트가 어떠한 리소스 삭제를 요청, 해당 리소스가 성공적으로 삭제됨

- 400 : 클라이언트의 요청이 부적절 할 경우 사용하는 응답 코드

- 401 : 클라이언트가 인증되지 않은 상태에서 보호된 리소스를 요청했을 때 사용하는 응답 코드

- 403 : 유저 인증상태와 관계 없이 응답하고 싶지 않은 리소스를 클라이언트가 요청했을 때 사용하는 응답 코드

- 404 : 클라이언트가 요청한 리소스에서는 사용 불가능한 Method를 이용했을 경우 사용하는 응답 코드

- 500 : 서버에 문제가 있을 경우 사용하는 응답 코드

- 502 : 게이트웨이 오류

# 2. HTTPS가 무엇인지 정리하고, HTTP와 비교하라

- https는 http를 더욱 안전하게 하기 위해 확장한 버전이다.
  
  기존 http에 ssl/ tls 기술을 결합한 것이다.
  

# 3. 아래 API에 대한 RESTful한 URI를 설계하라

- 이벤트 목록 조회: GET /api/events
  
- 이벤트 조회: GET /api/events/{id}
  
- 이벤트 등록: POST /api/events/
  
- 이벤트 수정: PUT /api/events/{id}
  
- 이벤트 삭제: DELETE /api/events/{id}
  
- 이벤트 상태 변경: PATCH /api/events/{id}
  
- 특정 이벤트의 주문 목록 조회: GET /api/events/{id}/orders
  
- 멤버 목록 조회: GET /api/members
  
- 특정 멤버 권한 변경: PUT /api/members/{id}/authorities
  
- 특정 멤버 정보 조회: GET /api/members/{id}/informations
  
- 특정 멤버 정보 변경: PUT /api/members/{id}/informations
  
- 멤버 등록: POST /api/members
