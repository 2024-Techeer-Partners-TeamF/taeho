##### HTTP란?
네트워크 장치간에 정보를 전송하도록 설계된 계층 프로토콜<br/>
HTTP는 기본적으로 request와 response구조로 이루어져 있으며, 모든 통신이 요청과 응답으로 이루어진다.<br/>
___
HTTP Request는 Start Line, Headers, blank line, Body로 이루어진다.<br/>
- Start line    
  - HTTP Request Message의 시작 라인으로 HTTP Method, Request target, HTTP version의 3가지 부분으로 구성된다. 
  - 예시) GET /test.html HTTP/1.1
[HTTP Method] [Request target] [HTTP version]
- Header 
  - request에 대한 추가 정보를 담고 있는 부분. general headers, request headers, entity headers, response headers의 4가지로 이루어져 있음.
  - General Header : 요청, 응답 메시지에 적용되는 기본적인 정보. Body에서 최종적으로 전송되는 데이터와는 관련이 없는 헤더.
  - Request Header : HTTP 요청에서 사용되지만 메시지의 컨텐츠와 관련이 없는 패치될 리소스나 클라이언트 자체에 대한 자세한 정보를 포함하는 헤더.
  - Entity Header : 콘텐츠 길이나 MIME 타입과 같이 Entity body에 대한 자세한 정보를 포함하는 헤더.
- Body
  - HTTP Request가 전송하는 데이터를 담고 있는 부분으로 전송하는 데이터가 없다면 비어 있다. POST 요청인 경우, HTML 폼 데이터가 포함되어 있다.
```
POST /test HTTP/1.1

Accept: application/json
Accept-Encoding: gzip, deflate
Connection: keep-alive
Content-Length: 83
Content-Type: application/json
Host: google.com
User-Agent: HTTPie/0.9.3

{
    "test_id": "tmp_1234567",
    "order_id": "8237352"   //실제 전송하려는 데이터들을 담고있다.
}
```
___
HTTP Response는 HTTP 상태코드(status line), HTTP 응답헤더(headers), blank line, 선택 사항인 HTTP본문(body)가 포함된다.
- Status line
  - HTTP Response의 상태를 간략하게 나타내 주는 부분으로, HTTP version, Status code, Status Text의 3가지 부분으로 나뉘어져 있다.
    - HTTP/1.1 200 OK [HTTP version] [Status Code] [Status Text]
  - Status code
    - 200번대(성공)
      - 200 OK. 성공적 요청.
      - 201 created 요청에 의해 자원이 생성됨.
      - 202 Accepted 요청이 접수되었으나 처리가 완료되지 않았음.
      - 204 No content 서버가 요청을 수행했으나 본문에 보낼 데이터가 없음.
    - 300번대 (리다이렉션)
      - 301 Moved Permanently : 리다이렉트시 요청 메서드가 Get으로 변하고, 본문이 제거될 수 있음.
      - 302 Found : 요청한 리소스의 URI가 일시적으로 변경되었음.
      - 303 See Other : 클라이언트가 요청한 리소스를 다른 URI에서 GET 요청을 통해 얻어야 할 때 서버가 클라이언트로 직접 보내는 응답
      - 304 Not Modified : 캐시를 목적으로 사용. 응답이 수정되지 않았음을 알림
    - 400번대 (클라이언트 측에서 오류 발생 )
      - 400 Bad Request : 클라이언트가 잘못된 요청을 해서 서버가 요청을 이해할 수 없음
      - 401 Unauthorized : 클라이언트가 해당 리소스에 대한 인증이 필요함
      - 403 Forbidden : 서버가 요청을 이해했지만 승인을 거부함(미승인)
      - 404 Not Found : 요청 리소스를 찾을 수 없음
    - 500번대 (서버측에서 오류가 발생)
      - 500 Internal Server Error : 서버 문제로 오류 발생. 처리 방법 알 수 없음.
      - 502 Bad Gateway : 서버가 요청을 처리하는 데 필요한 응답을 얻기 위해 Gateway로 작업하는 동안 잘못된 응답을 수신했음
      - 503 Service Unavailable : 서비스 이용 불가. 요청을 처리할 준비가 되지 않음.
___
##### API<br/>
Application Programming Interface. 한 프로그램에서 다른 프로그램으로 데이터를 주고받기 위한 방법
https://youtu.be/ckSdPNKM2pY