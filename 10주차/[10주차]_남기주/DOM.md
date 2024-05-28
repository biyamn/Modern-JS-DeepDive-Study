### DOM

HTML 문서의 계층적 구조와 정보를 표현하며 이를 제어할 수 있는 API, 즉 프로퍼티와 ㅔ서드를 제공하는 트리 자료구조

### 요소 노드 취득

- id이용
- 태그이용
- class이용
- css선택자

### 공백 테스트 노드
스페이스, 탭, 개행 등의 공백 문자는 텍스트 노드를 생성한다.

### 자식 노드 탐색
- Node.prototype.childNodes
- Element.prototype.children
- Node.prototype.firstChild
- Node.prototype.lastChild
- Element.prototype.firstElementChild
- Element.prototype.lastElementChild

### 부모 노드 탐색
- Node.prototype.parentNode

### 형제 노드 탐색
- Node.prototype.previosSibling
- Node.prototype.nextSibling
- Element.prototype.previosElementSibling
- Element.prototype.nextElementSibling

### 요소 노드의 텍스트 조작
- nodeValue
- textContent