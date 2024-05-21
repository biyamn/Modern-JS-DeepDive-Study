# :fire: 7번째 데이터 타입 Symbol

- ES6에서 새로이 도입된 데이터 타입.
- 원시 타입.
- 유일무이한 값.
- 충돌 위험이 없는 유일한 프로퍼티 키를 만들기 위해 사용한다.

---

## :one: 생성

### :memo: Symbol 함수

```javascript
const mySymbol = Symbol();
```

- 심벌 값은 외부로 노출되지 않아 확인할 수 없다.
- 문자열을 인수로 전달할 수 있다. 문자열의 내용은 디버깅을 위한, 심벌 값에 대한 설명. 
- 객체처럼 접근하면 래퍼 객체를 생성한다.
- 문자열이나 숫자로의 암묵적 타입 변환이 불가하다.
- 불리언 타입으로의 암묵적 타입 변환은 가능하다. 이를 통해 if문 등에서 존재 확인이 가능하다.

### :memo: Symbol.for/symbol.keyFor 메서드

- Symbol.for()
  - 인수로 전달 받은 문자열을 키로 사용하여 키와 심벌 값의 쌍들이 저장되어있는 _전역 심벌 레지스트리_ 에서 해당 키와 일치하는 심벌 값을 검색한다.
  - 검색에 성공하면 검색된 심벌 값 반환.
  - 검색에 실패하면 새로운 심벌 값 생성 후 그 값을 반환.
 
- Symbol.keyFor()
  - 전역 심벌 레지스트리에 저장된 심벌 값의 키를 추출할 수 있다.
  
---

## :two: 심벌과 상수

- 상수 이름 키 자체에 의미는 있되 값에는 특별한 의미가 없는 경우가 많다. 이 경우, 변경 가능성 및 중복 가능성의 위험성이 있다.
- 이 때 심벌 값으로 상수 값을 생성한다.

```javascript
const Direction = Object.freeze({
  UP: Symbol('up'),
  DOWN: Symbol('down'),
  LEFT: Symbol('left'),
  RIGHT: Symbol('right')
});
```

---

## :three: 심벌과 프로퍼티 키

- 객체의 프로퍼티 키는 빈 문자열을 포함하는 모든 문자열 또는 심벌값으로 만들 수 있으며, 동적으로 생성할 수도 있다.
  
```javascript
const obj = {
  [Symbol.for('mySymbol')]: 1
};
obj[Symbol.for('mySymbol')]; // 1
```

---

## :four: 심벌과 프로퍼티 은닉

- 심벌 값을 프로퍼티 키로 사용하여 프로퍼티를 생성하면 외부에 노출할 필요가 없는 프로퍼티를 은닉할 수 있다.
- Object.getOwnPropertySymbols 메서드로써 프로퍼티를 찾을수 있다.

```javascript
const obj = {
  [Symbol('mySymbol')]: 1
}

const symbolKey1 = Object.getOwnPropertySymbols(obj)[0];
console.log(obj[symbolKey1]); // 1
```

---

## :five: 심벌과 표준 빌트인 객체 확장

- 표준 빌트인 객체에 사용자 정의 메서드를 직접 추가하여 확장하는 것은 권장되지 않는다.
  - 개발자가 직접 추가한 메서드와 차후 표준 사양으로 추가될 메서드의 이름이 중복될 가능성이 이씩 때문이다.
  - 이 때, 심벌 값으로 프로퍼티 키를 생성하여 확장하면 이 사고를 미연에 방지하며 확장이 가능하다.
 
---

## :six: Well-known Symbol

- 자바스크립트가 기본 제공하는 빌트인 심벌 값.
