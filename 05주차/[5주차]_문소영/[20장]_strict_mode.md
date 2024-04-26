# strict mode란?
- let, var, const와 같은 키워드를 사용하지 않고 변수를 선언할 경우, reference error가 뜰 것 같지만 선언된 변수는 전역 변수처럼 사용할 수 있다. 이런 걸 암묵적 전역이라고 한다. 
- 이 경우, 오류가 발생할 가능성이 커지기 때문에 이를 지원하기 위해 strict mode(엄격 모드)가 추가 되었다. 자바스크립트 언어의 문법을 좀 더 엄격히 적용하여 오류를 발생시킬 가능성이 높거나 자바스크립트 엔진의 최적화 작업에 문제를 일으킬 수 있는 코드에 대해 명시적인 에러를 발생시킨다. 

# strict mode의 적용
- 전역의 선두 또는 함수 몸체의 선두에 'use strict';를 추가한다. 전역의 선두에 추가하면 스크립트 전체에 strict mode가 적용된다. (하지만 코드의 선두에 위치 시키지 않으면 strict mode가 제대로 동작하지 않는다.)

# 전역에 strict mode를 적용하는 것은 피하자.
- 전역에 적용한 strict mode는(스크립트 단위로 적용된 strict mode의 경우) 다른 스크립트에 영향을 주지 않고 스크립트 단위로 적용된다. 
- 하지만 strict mode 스크립트와 non-strict mode 스크립트를 혼용하는 것은 오류를 발생시킬 수 있다.

# 함수 단위로 strict mode를 적용하는 것도 피하자
- 어떤 함수는 strict mode를 적용하고 어떤 함수는 적용하지 않는 것은 바람직하지 않으며, 모든 함수에 일일이 strict mode를 적용하는 것은 번거로운 일이다. 

# strict mode가 발생시키는 에러
## 암묵적 전역
- 선언하지 않은 변수를 참조하면 ReferenceError가 발생한다.
    ```
    (function(){
        'use strice';
        x=1;
        console.log(x) //ReferenceError: x is not defined
    }());
    ```

## 변수, 함수, 매개변수의 삭제
- delete 연산자로 변수, 함수, 매개변수를 삭제하면 SyntaxError가 발생한다. 
    ```
    (function(){
        'use strice';
        var x=1;
        delete x; // Syntax Error
    }());
    ```

## 매개변수 이름의 중복
- 중복된 매개 변수 이름을 사용하면 SyntaxError 발생

## with 문의 사용
- with문을 사용하면 SyntaxError가 발생한다. with 문은 전달된 객체를 스코프 체인에 추가한다. with 문은 동일한 객체의 프로퍼티를 반복해서 사용할 때 객체 이름을 생략할 수 있어서 코드가 간단해지는 효과가 있지만 성능과 가독성이 나빠지는 문제가 있다.
    ```
    (function(){
        'use strict';

        with({x : 1}){
            console.log(x);
        }
    }());

# strict mode 적용에 의한 변화
## 일반 함수의 this
- strict mode에서 함수를 일반 함수로서 호출하면 this에 undefined가 바인딩된다. 생성자 함수가 아닌 일반 함수 내부에서는 this를 사용할 필요가 없기 때문이다. 이때 에러는 발생하지 않는다.
## arguments 객체
- strict mode에서는 매개변수에 전달된 인수를 재할당하여 변경해도 arguments 객체에 반영되지 않는다.
