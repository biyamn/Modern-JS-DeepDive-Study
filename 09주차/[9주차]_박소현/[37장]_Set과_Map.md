# :fire: 37장. Set과 Map

## :one: Set

**정의: 중복되지 않는 유일한 값들의 집합**
- 수학적 집합 특성과 일치 → 교집합, 합집합, 차집합, 여집합 등 구현 가능.

- 동일한 값 중복 불허.
- 요소 순서에 의미가 없다.
- 인덱스로 요소 접근 불가.
- 객체나 배열과 같이 자바스크립트의 모든 값을 요소로 저장할 수 있다.
- Set 객체는 이터러블(for...of문 순회, 스프레드 문법, 배열 디스트럭처링의 대상 가능)

### :memo: Set의 프로퍼티와 메서드

```javascript
/**
1. Set 객체 생성 : Set 생성자 함수는 이터러블을 인수로 받아 Set 객체를 생성한다. */

const set1 = new Set([1, 2, 3, 3]);
const set2 = new Set('hello');

console.log(set1); // Set(3) {1, 2, 3}
console.log(set2); // Set(4) {'h', 'e', 'l', 'o'};

/**
2. 요소 개수 : Set.prototype.size 접근자 프로퍼티 사용. */

console.log(set1.size); // 3

/**
3. 요소 추가
- Set.prototype.add 메서드 사용.
- 갱신된 Set 객체 반환(메서드 체이닝 가능).
- 중복된 요소 추가할 경우 무시된다.(NaN과 ±0의 중복도 거른다!)  */

console.log(set1.add(4).add(5)); // Set(5) {1, 2, 3, 4, 5}

/**
4. 요소 존재 여부 확인 : Set.prototype.has 메서드 사용. 불리언 값 반환. */
console.log(set1.has(2)); // true
console.log(set1.has(7)); // false

/**
5. 요소 삭제
- Set.prototype.delete 메서드 사용. 삭제 성공 여부 불리언 값 반환.
- 인덱스가 아닌 요소값을 인수로 전달. */

console.log(set1.delete(5)); // true
console.log(set1); // Set(4){1, 2, 3, 4}

/**
6. 일괄 삭제 : Set.prototype.clear 메서드 사용. undefined 반환. */

set2.clear();

/**
7. 요소 순회
- Set.prototype.forEach 메서드 사용.
- 콜백 함수 인수는 (현재 순회 중인 요소값, 현재 순회 중인 요소값, 현재 순회 중인 Set 객체 자체)이다. 첫번째 인수와 두번째 인수가 같다.
- for...of 문으로도 순회할 수 있다.

```

### :memo: Set의 집합 연산

```






```









