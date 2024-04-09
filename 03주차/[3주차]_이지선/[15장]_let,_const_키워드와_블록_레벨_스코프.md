**들어가기 전에…**

- const 키워드와 객체라는 소단원에 흥미가 간다. 객체를 const로 선언하면 변수명 자체는 변경이 안되는데 객체 안의 프로퍼티는 변경할 수 있다고 알고 있다. 그걸 말하는 걸까?

---

# var의 문제점

- 중복 선언 가능
- 함수 레벨 스코프
- 변수 호이스팅

# let

- 변수 중복 선언 금지
- 블록 레벨 스코프
- 변수 호이스팅

  - 변수 호이스팅이 발생하지 않는 것처럼 동작함
  - 선언 단계와 초기화 단계가 분리되어 진행되기 때문! 그 다음 할당

  ```jsx
  // 런타임 이전에 선언 단계 실행. 아직 초기화되지 않았음
  // 초기화 이전의 일시적 사각지대에서는 변수를 참조할 수 없어 참조 에러가 난다.
  console.log(foo); // ReferenceError: foo is not defined

  // 변수 초기화 단계. 변수 선언문에서 초기화 단계(undefined)가 실행된다.
  let foo;
  console.log(foo); // undefined

  // 할당문에서 할당 단계가 실행된다.
  foo = 1;
  console.log(foo); // 1
  ```

# const

- 상수를 선언하기 위해 사용된다.
- 반드시 선언과 동시에 초기화해야 한다.

  ```jsx
  const foo // SyntaxError: Missing initializer in const declaration

  const foo = 1; // Good
  ```

- 재할당이 금지된다.
- 변수를 선언할 때는 일단 const 키워드를 사용하자. 그리고 재할당이 필요하다면 그때 let 키워드로 변경해도 결코 늦지 않다!

### const 키워드와 객체

- const 키워드는 재할당을 금지할 뿐 불변을 의미하지는 않는다.
- const 키워드로 선언된 변수에 객체를 할당한 경우 값을 변경할 수 있다.

```jsx
const person = {
  name: "Lee",
};

person.name = "Kim";

console.log(person.name); // Kim
```
