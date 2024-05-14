Regular Expression, 정규 표현식이라고 부른다.

### RegExp.prototype.exec

- 잘 안쓰는 것 같음
- 패턴 매칭 결과를 배열로 반환
- g 플래그가 지정되어도 첫번째 매칭 결과만 반환

```jsx
const target = 'Is this all there is?';
const regExp = /is/g;

console.log(regExp.exec(target)); // ["is"]
```

### RegExp.prototype.test

- 패턴 매칭 결과를 불리언 값으로 반환

```jsx
const target = 'Is this all there is?';
const regExp = /is/;

console.log(regExp.exec(target)); // true
```

### RegExp.prototype.match

- 위의 문법과 조금 다름
- g 플래그가 지정되면 모든 매칭 결과를 배열로 반환

```jsx
const target = 'Is this all there is?';
const regExp = /is/g;

console.log(target.match(regExp)); // ["is", "is"]
```

# 플래그

- `i`(ignore care) - 대소문자 구별하지 않고 패턴 검색
- `g`(Global) - 모든 문자열을 전역 검색
- `m`(Multi line) - 문자열의 행이 바뀌더라도 패턴 검색 계속

# 패턴

- 정규 표현식은 패턴과 플래그로 구성된다.
- 패턴은 `/`로 열고 닫으며 문자열의 따옴표는 생략한다.

### ig: 전역, 대소문자 구별 없이

```jsx
const target = 'Is this all there is?';
const regExp = /is/ig;

// 대소문자 구별 없이 전역으로 is 매칭
console.log(target.match(regExp); // ["Is", "is", "is"]
```

### {n}: 앞선 패턴이 n번 반복되는 문자열

```jsx
const target = 'A AA B BB Aa Bb AAA';

const regExp = /A{2}/g;

console.log(match(regExp)); // ["AA", "AA"]
```

### {n, }: 앞선 패턴이 n번 이상 반복되는 문자열

```jsx
const target = 'A AA B BB Aa Bb AAA';

const regExp = /A{2, }/g;

console.log(match(regExp)); // ["AA", "AAA"]
```

### +: 앞선 패턴이 최소 한번 이상 반복되는 문자열(단어 레벨로 검색)

```jsx
const target = 'A AA B BB Aa Bb AAA';

const regExp = /A+/g;

console.log(match(regExp)); // ["A", "AA", "A", "AAA"]
```

### |: OR

```jsx
const target = 'A AA B BB Aa Bb';

const regExp = /A|B/g;

console.log(match(regExp)); // ["A", "A", "A", "B", "B", "B", "A", "B"]
```

### [-]: 범위 지정

```jsx
const target = 'A AA BB ZZ Aa Bb';

// 대문자 검색
const regExp = /[A-Z]+/g;

console.log(match(regExp)); // ["A", "AA", "BB", "ZZ", "A", "B"]
```

```jsx
const target = 'A AA BB ZZ Aa Bb';

// 대소문자 구분 안하려면
const regExp = /[A-Za-z]+/g;

console.log(match(regExp)); // ["A", "AA", "BB", "ZZ", "A", "B"]
```

```jsx
const target = 'A AA BB ZZ Aa Bb';

// 숫자 검색
const regExp = /[0-9]+/g;

console.log(match(regExp)); // ["A", "AA", "BB", "ZZ", "A", "B"]
```

### \d: 숫자

### \D: 숫자가 아닌 문자

### \w: 알파벳, 숫자, 언더스코어

- `[A-Za-z0-9_]`와 같음

### \W: 알파벳, 숫자, 언더스코어가 아닌 문자

### [^]: not

- `[^0-9]`는 숫자를 제외한 문자를 의미한다.

### ^: 문자열의 시작

- `/^https/`는 ‘https’로 시작하는지를 검색한다.

### $: 문자열의 마지막을 의미한다.

# https://regexr.com/
