
# DOM이란?
문서 객체 모델(The Document Object Model, 이하 DOM) 은 **HTML, XML 문서의 프로그래밍 인터페이스**이다.
### **프로그래밍 인터페이스**란?
  - 인터페이스란, “상호작용하는 곳”을 의미한다. ex) 터치스크린+손가락, 리모콘, TV 버튼
  - 프로그래밍 인터페이스란, 프로그래밍 언어가 상호작용할 수 있게 해 주는 곳을 의미한다.  

DOM은 문서의 구조화된 표현(structured representation)을 제공하며 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법을 제공하여 그들이 문서 구조, 스타일, 내용 등을 변경할 수 있게 돕는다.  
DOM은 HTML 요소 하나하나를 의미하는 것이 아니라 HTML 주문서에 작성한 전체 구조에 맞춰 배치되고, 속성/디자인 등을 배치할 수 있도록 된 상태를 의미한다. HTML로 이루어진 요소들이 기능들을 수행할 객체들로 실체화된 형태를 DOM이라 한다.  
(DOM은 특정 언어에 종속되지 않기 때문에 HTML 요소, JS 요소라 부르지는 않는다.  
DOM은 어떤 언어(JS, Python...)로든 라이브러리가 갖춰지면 조작 가능한데, DOM이 API를 가지고 있기 때문이다.)  
즉, DOM은 Document Object Model의 약자로, HTML 요소를 Object(JavaScript Object)처럼 조작(Manipulation)할 수 있는 Model을 말한다. DOM으로 HTML을 조작할 수 있다.
### API (Application Programming Interface)란?
- 어떤 명령을 내리면 그 명령어에 맞춰 기능들을 수행할 수 있도록 만들어놓은 것이다.  

DOM은 각종 Node tree로 구성되어있다.
  - HTML의 ``<head>``, ``<body>`` 등의 태그 안에 ``<div>``, ``<h1>``, 그 안에 ``<li>``, ``<ul>`` 등 각종 요소들이 구조적인 형태로 이루어져 있는데 이런 요소들은 모두 Node 로 이루어져 있고 그 관계도를 트리 형태로 구성한다.
  - first-child / last-child 같은 기능들이 모두 Node의 기능이다.
  - 각 Node들은 클릭 등의 이벤트가 가해지는 EventTarget이기 때문에 이 요소들은 모두 addEventListner 등의 기능들을 가진다.  

초창기에는 자바스크립트와 DOM 가 밀접하게 연결되어 있었지만, 나중에는 각각 분리되어 발전해왔다.  
페이지 콘텐츠(the page content)는 DOM 에 저장되고 자바스크립트를 통해 접근하거나 조작할 수 있다. 이것을 방정식으로 표현하면 아래와 같다.
  - API (web or XML page) = DOM + JS (scripting language)
# DOM 조작 방법
- CREATE : ``createElement``
- READ : ``querySelector``, ``querySelectorAll``
- UPDATE : ``textContent``, ``id``, ``classList``, ``setAttribute``
- DELETE : ``remove``, ``removeChild, innerHTML = ""`` , ``textContent = ""``
- APPEND : ``append``, ``appendChild``
### CREATE
- createElement 메소드로 새로운 HTML 요소 생성
```
const divBox = document.createElement('div')
```
### READ
- querySelector로 첫 번째 요소를 가져온다.
- 셀렉터로는 HTML 태그, id, class 세가지가 가장 많이 사용된다.
```
const oneBox = document.querySelector('.box elementName') // 클래스 내에서 해당 엘리먼트 요소를 반환, 여러 개가 있는 경우 제일 첫 번째만
const twoBox = document.querySelector("#id") // == document.getElementByID()
```
- querySelectorAll로 여러 개의 엘리먼트를 한 번에 가져올 수 있다.
- querySelectorAll로 가져온 엘리먼트들은 NodeList라는 유사배열(Array-like Object)로, 배열처럼 for문을 사용할 수 있다.
```
const allBox = document.querySelectorAll('.box')
```
### APPEND
- 생성한 HTML 요소를 트리 구조와 연결한다.
```const divBox = document.createElement('div')
document.body.append(divBox)
```
- append는 한 번에 여러 요소를 연결 할 수 있다.
- appendChild는 한 번에 하나의 요소를 부모 요소에 연결한다.
### UPDATE
- textContent를 변경해 내용을 추가할 수 있다.
```
divBox.textContent = "내용 추가"
```
- classList를 이용해 class를 추가하거나 삭제할 수 있다.
- ``divBox.classList.contains('box-style')``을 이용해 class 포함 여부를 boolean 형태로 반환할 수 있다.
```
divBox.classList.add('box-style')
```
### DELETE
- remove 메소드로 요소를 삭제한다.
```
divBox.remove()
```
- removeChild 메소드로 자식 요소를 삭제한다.
```
Body.removeChild()
```
출처 : [DOM 소개 - MDN](https://developer.mozilla.org/ko/docs/Web/API/Document_Object_Model/Introduction) , [DOM은 뭐고 가상 DOM은 뭔가요? - 얄팍한 코딩사전](https://www.youtube.com/watch?v=1ojA5mLWts8), [DOM 조작 방법](https://velog.io/@sana0803/DOM-%EC%A1%B0%EC%9E%91-%EB%B0%A9%EB%B2%95)
