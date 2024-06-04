## What I Learned
2024/05/28 마지막 기초 웹 스터디

### 301, 303 요청을 하였을때, 왜 httpstat.us 페이지의 메인으로 redirect될까?

redirection과 관련이 있는 300번대 상태 코드 중 301번은  Moved Permanently로, 요청한 페이지 등이 영구적으로 다른 곳으로 이동되었기에 새로운 url로 redirect를 해주고 303번 See Other는 리소스를 다른 URI에서 GET 요청을 통해 얻어야 할 때, 그 url로 redirect를 해준다. 

### 401 요청을 하였을 때, 네트워크 탭의 상태를 보고 어떻게 인증해야 하는지 www-Authenticate 헤더를 기반으로 설명해보자.

클라이언트 측에서 필요한 인증 정보(인코딩한 비밀번호 등)을 WWW-Authenticate 헤더에 포함해 전달한다.

### Google에 “Hello”를 입력하여 결과물을 보고, 네트워크 요청 탭에서 캐시 관련 정보가 어디에 저장되어 있는지 분석하여 보자.

Cache-Control 헤더에서 캐시의 저장 여부를 물어보고 웹브라우저에 저장한다.



### 더 알고 싶은 상태코드를 직접 체험해보고, 해당 상태코드에서 진행한 요청 헤더, 응답 헤더를 직접 정리하여 분석해보자.

서버에 요청을 수행할 수 있는 기능이 없다는 의미를 가진 상태코드 501을 체험해 보았다.

요청 헤더는

HTTP/1.1 501 Not Implemented

Content-Length: 19

Content-Type: text/plain

Date: Tue, 04 Jun 2024 02:45:23 GMT

Server: Kestrel

Strict-Transport-Security: max-age=2592000

Request-Context: appId=cid-v1:3548b0f5-7f75-492f-82bb-b6eb0e864e53

이고

응답 헤더는

GET /501 HTTP/1.1

Accept:text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7

Accept-Encoding: gzip, deflate, br, zstd

Accept-Language: ko-KR,ko;q=0.9

Cache-Control: max-age=0

Connection: keep-alive

Cookie: ARRAffinity=c5e90f0d5e6f37f5e2cc43fc8b88c4ecdb32ccbcfaec54b421e66970b3c785de; ARRAffinitySameSite=c5e90f0d5e6f37f5e2cc43fc8b88c4ecdb32ccbcfaec54b421e66970b3c785de; _ga=GA1.2.336639729.1717468571; _gid=GA1.2.772054477.1717468571; _gat=1; 
_ga_GPBEMSR86L=GS1.2.1717468572.1.1.1717469112.0.0.0

Host: httpstat.us

Referer: https://httpstat.us/

Sec-Fetch-Dest: document

Sec-Fetch-Mode: navigate

Sec-Fetch-Site: same-origin

Sec-Fetch-User: ?1

Upgrade-Insecure-Requests: 1

User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/125.0.0.0 Safari/537.36

sec-ch-ua: "Google Chrome";v="125", "Chromium";v="125", "Not.A/Brand";v="24"

sec-ch-ua-mobile: ?0

sec-ch-ua-platform: "Windows"

이다.