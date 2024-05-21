## 심벌
다른 값과 중복되지 않는 유일무이한 값이다. 
프로퍼티 키로 사용할 수 있는 값은 빈 문자열을 포함하는 모든 문자열 또는 심벌 값이다.
심벌값은 symbol함수를 호출하여 생성한다.

```javascript
const obj={
     [Symbol.for('mySymbol')]:1
}

obj[Symbol.for('mySymbol')] //1
```