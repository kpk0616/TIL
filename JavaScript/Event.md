# 이벤트란
이벤트(event)는 사용자의 행동에 따라 브라우저에서 나타나는 사건을 의미한다.

## 이벤트의 종류
### 마우스 이벤트
- click : 마우스를 클릭했을 때 이벤트 발생
- dbclick : 마우스를 더블클릭했을 때 이벤트 발생
- mouseover : 마우스를 오버했을 때 이벤트 발생
- mouseout : 마우스를 아웃했을 때 이벤트 발생
- mousedown : 마우스를 눌렀을 때 이벤트 발생
- mouseup : 마우스를 떼었을 때 이벤트 발생
- mousemove : 마우스를 움직였을 때 이벤트 발생
- contextmenu : context menu (마우스 오른쪽 버튼 눌렀을 때 나오는 메뉴) 가 나오기 전 이벤트 발생
### 키 이벤트
- keydown : 키를 눌렀을 때 이벤트 발생
- keyup : 키를 떼었을 때 이벤트 발생
- keypress : 키를 누른 상태에서 이벤트 발생
### 폼 이벤트
- focus : 요소에 포커스가 이동되었을 때 이벤트 발생
- blur : 요소에 포커스가 벗어났을 때 이벤트 발생
- change : 요소에 값이 변경되었을 때 이벤트 발생
- submit : submit 버튼 눌렀을 때 이벤트 발생
- reset : reset 버튼을 눌렀을 때 이벤트 발생
- select : input이나 textarea 요소 안의 텍스트를 드래그해 선택했을 때 이벤트 발생
### 로드 및 기타 이벤트
- load : 페이지 로딩 완료되었을 때 이벤트 발생
- abort : 이미지 로딩 중단되었을 때 이벤트 발생
- unload : 페이지가 다른 곳으로 이동될 때 이벤트 발생
- resize : 요소에 사이즈 변경되었을 때 이벤트 발생
- scroll : 스크롤바 움직였을 때 이벤트 발생

## 이벤트 연결
- 이벤트 핸들러(handler)를 이용해 이벤트를 처리한다.
- 이벤트 핸들러는 on ~ 으로 시작한다.
1) 인라인 방식  
``<태그명 on이벤트 = JS코드> </태그명>``
```
<div onclick="alert('클릭했습니다1.')">클릭</div>
  <div onclick="view()">클릭</div>
    
<script>
   function view() {
     alert("클릭했습니다2.");
   }
</script> 
  ```  
2) 고전 방식  
(1) ``객체.on이벤트명 = function() {  }``  
```
<div class="hello">
    <h1>HIHIHI</h1>
</div>

<script>
const title = document.querySelector("div.hello:first-child h1");
console.log(title);

function handleTitleClick() {
    console.log("title was clicked!");
    title.style.color = "blue"
}
title.addEventListener("click", handleTitleClick);
</script>
```
(2) function 함수명() {}  객체.on이벤트명 = 함수명  
```
<script>
     var bt = document.getElementById("bt");
     function view() {
        alert("클릭했습니다!!!");
     }
     
     bt.onclick = view;
     
     /*
     // bt.onclick = view; 와 같은 역할
     bt.onclick = function() {
        view();
     }
     */
</script>
```
## script 태그
- HTML과 JS 연결 시 script 태그 이용, body 태그 최하단에 위치하는 것이 가장 좋다.
```
<body>
<script src="app.js"></script>
</body>
```
### body 태그 최하단이 가장 좋은 이유
브라우저는 다음의 방식으로 동작한다.
1. HTML을 읽는다.
2. HTML을 파싱한다. (parsing : 일련의 문자열을 기계어로 번역하는 과정)
3. DOM 트리를 생성한다. (DOM : 문서 객체 모델, The Document Object Model)
4. Render 트리 (Dom Tree + CSS의 CSSOM Tree 결합)가 생성된다.
5. Display에 표시한다.  

1,2,3의 순서에서 HTML을 파싱한 후 DOM 트리를 생성하는 과정에서 브라우저가 HTML 태그들을 읽다 ``<script>`` 를 만나면 
파싱을 중단하고 javascript 파일을 로드 후 javascript 코드를 파싱한다. 완료되면 그 후 HTML 파싱이 계속된다.
 이로 인해 HTML 태그들 사이 script 태그가 위치하게 되면 두 가지 문제가 발생한다.
 1. HTML을 읽는 과정에 스크립트를 만나면 중단 시점이 생기고 그만큼 Display에 표시되는 것이 지연된다.
 2. DOM 트리가 생성되기 전에 자바스크립트가 생성되지도 않은 DOM의 조작을 시도할 수 있다.  


위 같은 상황을 막기 위해 script 태그는 body 태그 최하단에 위치하는 것이 가장 좋다.
