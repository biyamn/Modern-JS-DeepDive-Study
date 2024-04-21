## strict mode
```javascript
function foo(){
    x=10
}

foo();
```
x변수의 선언이 존재하지 않기 때문에 ReferenceError를 발생시킬 것 같지만 자바스크립트 엔진은 암묵적으로 전역 객체에 x 프로퍼티를 동적 생성하고 이러한 현상을 암묵적 전역이라고 한다. 

```javascript
'use strict';
function foo(){
    x=10
}

foo();

function foo(){
   'use strict';
    x=10
}

foo();
```
위의 코드는 x is not defined로 ReferenceError가 뜬다

```javascript
function foo(){
    x=10
    'use strict';
}

foo();
```
코드의 선두에 위치시키지 않으면 제대로 동작하지 않는다. 

