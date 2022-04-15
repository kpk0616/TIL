
# DOM이란?
문서 객체 모델(The Document Object Model, 이하 DOM) 은 **HTML, XML 문서의 프로그래밍 인터페이스**이다.
### **프로그래밍 인터페이스**란?
  - 인터페이스란, “상호작용하는 곳”을 의미한다. ex) 터치스크린+손가락, 리모콘, TV 버튼
  - 프로그래밍 인터페이스란, 프로그래밍 언어가 상호작용할 수 있게 해 주는 곳을 의미한다.  

DOM은 문서의 구조화된 표현(structured representation)을 제공하며 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법을 제공하여 그들이 문서 구조, 스타일, 내용 등을 변경할 수 있게 돕는다.
DOM은 HTML 요소 하나하나를 의미하는 것이 아니라 HTML 주문서에 작성한 전체 구조에 맞춰 배치되고, 속성/디자인 등을 배치할 수 있도록 된 상태를 의미한다. HTML로 이루어진 요소들이 기능들을 수행할 객체들로 실체화된 형태이다.
(DOM은 특정 언어에 종속되지 않기 때문에 HTML 요소, JS 요소라 부르지는 않는다. DOM은 어떤 언어(JS, Python...)로든 라이브러리가 갖춰지면 조작 가능한데, DOM이 API를 가지고 있기 때문이다.)
### API (Application Programming Interface)란?
- 어떤 명령을 내리면 그 명령어에 맞춰 기능들을 수행할 수 있도록 만들어놓은 것이다.  

DOM은 각종 Node tree로 구성되어있다.
  - HTML의 ``<head>``, ``<body>`` 등의 태그 안에 ``<div>``, ``<h1>``, 그 안에 ``<li>``, ``<ul>`` 등 각종 요소들이 구조적인 형태로 이루어져 있는데 이런 요소들은 모두 Node 로 이루어져 있고 그 관계도를 트리 형태로 구성한다.
  - first-child / last-child 같은 기능들이 모두 Node의 기능이다.
  - 각 Node들은 클릭 등의 이벤트가 가해지는 EventTarget이기 때문에 이 요소들은 모두 addEventListner 등의 기능들을 가진다.  

초창기에는 자바스크립트와 DOM 가 밀접하게 연결되어 있었지만, 나중에는 각각 분리되어 발전해왔다. 페이지 콘텐츠(the page content)는 DOM 에 저장되고 자바스크립트를 통해 접근하거나 조작할 수 있다. 이것을 방정식으로 표현하면 아래와 같다.
  - API (web or XML page) = DOM + JS (scripting language)
  
출처 : [DOM 소개 - MDN](https://developer.mozilla.org/ko/docs/Web/API/Document_Object_Model/Introduction) , [DOM은 뭐고 가상 DOM은 뭔가요? - 얄팍한 코딩사전](https://www.youtube.com/watch?v=1ojA5mLWts8)
