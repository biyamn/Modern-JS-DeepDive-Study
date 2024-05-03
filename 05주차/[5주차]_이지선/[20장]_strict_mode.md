# ‘use strict’;

- 전역의 선두 혹은 함수 몸체의 **선두**에 ‘use strict’를 추가한다.
- ES6에서 도입된 클래스와 모듈은 기본적으로 strict mode가 적용된다.
- 근데 ESLint를 사용하는 걸 더 추천하심. https://poiemaweb.com/eslint
  - 필히 ESLint를 사용할 것을 권함

# strict mode가 발생시키는 에러

- 선언하지 않은 변수를 참조하면(암묵적 전역) ReferenceError 발생
- 변수, 함수, 매개변수를 delete 연산자로 삭제하면 SyntaxError 발생
- 중복된 매개변수 이름을 사용하면 SyntaxError 발생(`(x, x) ⇒ x + x`)
- with문 사용시 SyntaxError 발생(사용하지 않는 것이 좋음)
