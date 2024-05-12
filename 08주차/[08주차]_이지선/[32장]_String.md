### String.prototype.indexOf

- 인수로 전달받은 문자열의 첫번째 인덱스를 반환. 없으면 -1을 반환

### String.prototype.search

- 인수로 전달받은 정규표현식과 매치하는 문자열의 인덱스를 반환. 없으면 -1을 반환.

### String.prototype.includes

- 인수로 전달받은 문자열이 포함되어 있는지 확인하여 불리언으로 반환.

### String.prototype.startsWith

### String.prototype.endsWith

### String.prototype.charAt

- 인수의 인덱스에 위치한 문자를 검색하여 반환
- 예) for문으로 문자열을 한 자씩 출력할 때

### String.prototype.substring

- 인수의 첫번째 인덱스부터 두번째 인덱스 직전까지의 문자열 반환
- 두번째 인수 생략 가능, 이때 끝까지 반환
  ```jsx
  const str = 'Hello World';

  str.substring(1, 4); // ell
  ```

### String.prototype.slice

- substring과 동일하나 음수인 인수 전달 가능

### String.prototype.toUpperCase

### String.prototype.toLowerCase

### String.prototype.trim

### String.prototype.repeat

```jsx
const str = 'abc';
str.repeact(2);
('abcabc');
```

### String.prototype.replace

첫번째 인수로 문자열 또는 정규표현식을 받아 두번째 인수로 치환한 문자열 반환

### String.prototype.split

첫번째 인수로 문자열 또는 정규표현식을 받아 분리한 후 배열 반환
