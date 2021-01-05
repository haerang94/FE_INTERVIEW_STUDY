
### HTTP 

- HTTP (Hypertext Transfer Protocal)은 인터넷 상에서 데이터를 주고 받기 위한 **클라이언트/서버 모델**을 따르는 프로토콜
- WWW (world wide web)에서 하이퍼텍스트 문서를 교환하기 위해 사용되는 통신규약
- TCP/IP 프로토콜 위에서 동작한다. **포트 80번**을 사용하여 통신한다

- HTML 문서, 이미지, 동영상, 오디오, 텍스트 문서 등 의 모든 종류의 데이터를 전송한다
- 하이퍼텍스트 기반으로 데이터 전송 = 링크 기반으로 데이터에 접속하겠다 
- 첫 표준은 HTTP/1.1이며 이후로 HTTP/2, HTTP/3이 등장했다.

### 클라이언트/서버 모델 

- **클라이언트**
  - 클라이언트 소프트웨어(ie,crome같은 브라우저)가 설치된 컴퓨터를 이용해서 서버에 요청한다. URI를 통해 서버에 접속하고 데이터를 요청한다.
  <BR/>
- **서버**
  - 클라이언트 요청을 받아 해석하고 응답하는 소프트웨어(Apache, nginx, IIS, lighttpd)가 설치된 컴퓨터
  - 웹서버는 표준 포트인 80번 포트로 서비스 한다 


### HTTP/1.1

#### 비연결지향(connectionless)
  - 클라이언트가 서버에 리소스 요청한 후 응답 받으면 연결을 끊어버리는 특징이다. 
  - 서버에 부담을 주지 않도록 클라이언트 요청을 처리하면 연결을 끊어 서버의 부담을 줄인다. 하지만 리소스를 요청할 때마다 새롭게 연결해야 되므로 오버헤드 비용이 발생한다.
  - **오버 헤드 해결 방법**: 요청 헤더 **connection:keep-alive** 속성으로 지속적 연결 상태(persistent connection)을 유지한다.
    요청을 할 때마다 연결하지 않고 기존의 연결을 재사용하는 방식으로 HTTP/1.1부터는 지속적 연결 상태가 기본이고 해제하기 위해서는 명시적으로 요청 헤더를 수정해야 한다.

#### 무상태성 (stateless)
- 각각의 요청은 독립적이라고 여겨지는 특성으로 서버는 클라이언트의 상태를 유지하지 않는다.
- 요청이 처리되면 연결이 끊어지기 때문에 클라이언트의 이전 상태를 알 수 없다. connectless로부터 파생되는 특징이다.
- 클라이언트가 과거에 로그인을 해도 로그 정보를 유지할 수 없다. 웹 서비스를 하기위해서 쿠키나 세션 또는 토큰 방식의 OAuth 및 JWT가 사용된다.

- 동시 전송이 불가능하고 요청과 응답이 순차적으로 이루어진다. HTTP문서 안 다수의 리소스를 처리하려면 Latency(대기시간)이 길어진다
- 

#### HTTP/1.1 단점
- HOL (Head of Line) blocking: 특정 응답의 지연
  - http/1.1의 connection 당 하나의 요청 처리를 개선하는 방법 중 파이프라이닝이 존재
  - connection을 통해 다수개의 파일을 요청/응답 받는 기법 
  
  
  
- RTT (round trip time) 증가
- 무거운 header 구조 (ex. 쿠키)




### 출처 
- [HTTP 프로토콜이란?](https://shlee0882.tistory.com/107)
- [HTTP](https://github.com/baeharam/Must-Know-About-Frontend/blob/master/Notes/network/http.md)
- [network](https://github.com/brave-people/brave-tech-interview/blob/master/contents/network.md#dns%EC%97%90-%EB%8C%80%ED%95%B4%EC%84%9C-%EC%84%A4%EB%AA%85%ED%95%98%EC%84%B8%EC%9A%94)
- [HTTP/1.1 VS HTTP/2](https://ijbgo.tistory.com/26)



