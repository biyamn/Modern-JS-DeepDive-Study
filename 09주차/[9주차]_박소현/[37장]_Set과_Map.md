# :fire: 37장. Set과 Map

## :one: Set

**정의: 중복되지 않는 유일한 값들의 집합**
- 수학적 집합 특성과 일치 → 교집합, 합집합, 차집합, 여집합 등 구현 가능.

- 동일한 값 중복 불허.
- 요소 순서에 의미가 없다.
- 인덱스로 요소 접근 불가.
- 객체나 배열과 같이 자바스크립트의 모든 값을 요소로 저장할 수 있다.

### :memo: Set의 프로퍼티와 메서드

```javascript
/**
1. 객체 생성 : Set 생성자 함수는 이터러블을 인수로 받아 Set 객체를 생성한다. */

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
- 콜백 함수 인수는 (현재 순회 중인 요소값, 첫번째 인수와 같은 값, 현재 순회 중인 Set 객체 자체)이다.
- Set 객체는 이터러블(for...of문 순회, 스프레드 문법, 배열 디스트럭처링 할당의 대상 가능) */

set1.forEach((v, v2, set) => console.log(v, v2, set));
//1 1 Set(4) {1, 2, 3, 4}
//2 2 Set(4) {1, 2, 3, 4}
//3 3 Set(4) {1, 2, 3, 4}
//4 4 Set(4) {1, 2, 3, 4}

```

### :memo: Set의 집합 연산

``` javascript
/**
1. 교집합 */

Set.prototype.intersection = function (set) {
    return new Set([...this].filter(v => set.has(v)));
}

/**
2. 합집합 */

Set.prototype.union = function (set) {
    return new Set ([...this, ...set]);
}

/**
3. 차집합 */

Set.prototype.difference = function (set) {
    return new Set([...this].filter(v => !set.has(v)));
}

/**
4. 부분집합과 상위집합 */

Set.prototype.isSuperset = function (subset) {
    const supersetArr = [...this];
    return [...subset].every(v => supersetArr.includes(v));
}
```

---

## :two: Map

**정의: 키와 값의 쌍으로 이루어진 컬렉션**

- 객체와의 차이 
    - 모든 값을 키로 사용 가능. (객체는 문자열과 심벌값만 가능하다)
    - 이터러블. (객체는 언이터러블하다)
    - 요소 개수 확인할 때 length 프로퍼티가 아니라 Map.prototype.size 프로퍼티를 사용한다.

- 중복된 키를 갖는 요소는 덮어쓰여진다.

### :memo: Map의 프로퍼티와 메서드

```javascript
/**
1. 객체 생성
- Map 생성자 함수에 인수를 전달하지 않으면 빈 Map 객체가 생성된다.
- 인수는 이터러블이며, 키와 값의 쌍으로 이루어진 요소로 구성되어야한다. */

const map = new Map([['Key1', 'Value1'], ['Key2', 'Value2']]);

/**
2. 요소 개수 : Map.prototype.size 접근자 프로퍼티 사용. */

console.log(map.size); // 2

/**
3. 요소 추가
- Map.prototype.set 메서드 사용.
- 갱신된 Map 객체 반환(메서드 체이닝 가능).
- 중복된 요소 추가할 경우 무시된다.(NaN과 ±0의 중복도 거른다!)  */

console.log(map.set('Key3', 'Value3').set('Key4', 'Value4'));

/**
4. 요소 취득 : Map.prototype.get 메서드 사용. */

console.log(map.get('Key3'));

/**
5. 요소 존재 여부 확인 : Map.prototype.has 메서드 사용. 불리언 값 반환. */

console.log(map.has('Key3')); // true
console.log(map.has('Key10')); // false

/**
6. 요소 삭제
- Map.prototype.delete 메서드 사용. 삭제 성공 여부 불리언 값 반환. */

console.log(map.delete('Key4')); // true
console.log(map);

/**
7. 일괄 삭제 : Map.prototype.clear 메서드 사용. undefined 반환. */

const map2 = new Map([[1, 1]]);
map2.clear();

/**
8. 요소 순회
- Map.prototype.forEach 메서드 사용.
- 콜백 함수 인수는 (현재 순회 중인 요소값, 첫번째 인수와 같은 값, 현재 순회 중인 Set 객체 자체)이다.
- Map 객체는 이터러블(for...of문 순회, 스프레드 문법, 배열 디스트럭처링 할당의 대상 가능)
- 이터레이터인 객체를 반환하는 메서드를 제공한다.
    - Map.prototype.keys → 요소키를 값으로 갖는 이터러블 & 이터레이터 객체 반환
    - Map.prototype.values → 요소값을 값으로 갖는 이터러블 & 이터레이터 객체 반환
    - Map.prototype.entries  → 요소키와 요소값을 값으로 갖는 이터러블 & 이터레이터 객체 반환 */

map.forEach((v, v2, set) => console.log(v, v2, set));
// Value1 Key1 Map(3) { 'Key1' => 'Value1', 'Key2' => 'Value2', 'Key3' => 'Value3' }
// Value2 Key2 Map(3) { 'Key1' => 'Value1', 'Key2' => 'Value2', 'Key3' => 'Value3' }
// Value3 Key3 Map(3) { 'Key1' => 'Value1', 'Key2' => 'Value2', 'Key3' => 'Value3' }

console.log(map.key()); // [Map Iterator] { 'Key1', 'Key2', 'Key3' }

console.log(map.values()); // [Map Iterator] { 'Value1', 'Value2', 'Value3' }

console.log(map.entries());
/**
[Map Entries] {
  [ 'Key1', 'Value1' ],
  [ 'Key2', 'Value2' ],
  [ 'Key3', 'Value3' ]
}
*/
```
