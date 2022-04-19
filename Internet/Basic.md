# 인터넷은 어떻게 작동될까?
인터넷은 컴퓨터들이 서로 통신 가능하게 하는 거대한 네트워크이다.  
컴퓨터가 통신하기 위해서는 무선 혹은 유선으로 연결되어 있어야 한다.  

![image](https://user-images.githubusercontent.com/70744494/163911694-d9bce02f-87c4-44e4-a1da-9478e83ef3e0.png)

  각각의 컴퓨터는 **라우터**를 통해 네트워크에 연결된다. 라우터는 메시지를 올바르게 전달하는 역할을 한다. 
라우터는 각각의 라우터들과도 연결 가능한데, 이를 통해 네트워크 속의 네트워크를 형성하여 무한히 확장할 수 있다. 

![image](https://user-images.githubusercontent.com/70744494/163911947-db61daa1-5660-4ba5-b974-f4c9ba705ca6.png)  
  
  이렇게 구축한 네트워크를 **모뎀**을 이용해 전화 시설에 연결한다. 모뎀은 네트워크의 정보를 전화 시설에서 처리할 수 있는 정보로 바꾸는 역할을 한다.

![image](https://user-images.githubusercontent.com/70744494/163914036-70dfa7fe-08bf-4c97-8245-9a32a2fcd6fa.png)


우리의 네트워크는 다른 네트워크로 메시지를 보내기 위해 인터넷 서비스 제공 업체 (Internet Service Provide, **ISP**)에 연결된다. 
**ISP**는 여러 개의 네트워크가 연결되는 특수한 라우터를 관리하고 다른 ISP의 라우터에도 액세스 할 수 있게 하는 회사이다.
 우리의 네트워크는 ISP 네트워크의 네트워크를 통해 대상 네트워크로 전달된다. 

![image](https://user-images.githubusercontent.com/70744494/163913967-abd939f5-1a74-4bdd-9ea1-4d5ec7fca266.png)

### 컴퓨터 찾기
네트워크에 연결된 모든 컴퓨터는 고유한 **IP (Internet Protocol)주소**를 가진다.  
ex) ``192.168.2.10``

**도메인 네임**은 사람이 읽을 수 있는 IP 주소의 이름을 지정한다.
우리는 인터넷을 사용할 때 도메인 네임을 이용해 IP 주소를 찾아간다.  
ex) ``google.com`` 의 IP 주소는 ``173.194.121.31``이다.

![image](https://user-images.githubusercontent.com/70744494/163915105-3198b905-9404-449d-a076-a99ae5fbb61a.png)

### 인터넷과 웹
웹과 인터넷은 다르다. 인터넷은 수십억 대의 컴퓨터를 연결하는 기술 인프라를 의미하고, 웹은 그 인프라 기반 위에 구축된 서비스를 의미한다.  
인터넷 위에 구축된 다른 서비스들로는 이메일, IRC(Internet Relay Chat, 실시간 채팅 프로토콜) 등이 있다.

# HTTP란?
HTTP (HyperText Transfer Protocol) 는 HTML 문서 같은 리소스들을 가져올 수 있게 해 주는 프로토콜이다. 
클라이언트-서버 프로토콜로, 사용자(클라이언트)가 브라우저에서 URL 또는 다른 것을 통해 서비스를 요청(request)하면 
서버에서는 해당 요청사항에 맞는 결과를 찾아 사용자에게 응답(response)하는 형태로 동작한다.
사용자 요청에 응답한 하나의 완전한 문서는 텍스트, 레이아웃 설명, 이미지, 비디오, 스크립트 등 불러온(fetched) 하위 문서들로 재구성된다.

![image](https://user-images.githubusercontent.com/70744494/163918559-859c7edc-3d78-4bfd-81e1-1d544f0273ed.png)

  - 요청 (request) : 클라이언트에 의해 전송되는 메시지
  - 응답 (response) : 서버에서 응답으로 전송되는 메시지

HTTP는 애플리케이션 계층의 프로토콜로, HTML 문서만이 HTTP 통신을 위한 유일한 정보 문서는 아니다.  



# 브라우저의 작동 원리
# DNS와 작동 원리
# 도메인 네임은 무엇인가?

# 호스팅은 무엇인가?

출처 : [Web개발 학습하기 - MDN](https://developer.mozilla.org/ko/docs/Learn/Common_questions/How_does_the_Internet_work), [HTTP 개요 - MDN](https://developer.mozilla.org/ko/docs/Web/HTTP/Overview), [HTTP란 무엇인가? - MDN](https://velog.io/@surim014/HTTP%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80)
