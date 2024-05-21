## 정규 표현식

일정한 패턴을 가진 문자열의 집합을 표현하기 위해 사용하는 형식 언어다.

### RegExp.prototype.exec

인수로 전달받은 문자열에 대해 정규 표현식의 패턴을 검색하여 매칭 결과를 배열로 반환한다.

```javascript
const target = "Is this all there is?";
const regExp = /is/;

regExp.exec(target);
```

### RegExp.prototype.test

인수로 전달받은 문자열에 대해 정규 표현식의 패턴을 검색하여 매칭 결과를 불리언값으로 반환한다.

```javascript
const target = "Is this all there is?";
const regExp = /is/;

regExp.test(target);
```

### RegExp.prototype.match

인수로 전달받은 문자열에 대해 정규 표현식의 패턴을 검색하여 매칭 결과를 배열로 반환한다.

```javascript
const target = "Is this all there is?";
const regExp = /is/;

regExp.match(target);
```

exec메서드는 문자열 내의 모든 패턴을 검색하는 g플래그를 사용해도 첫 번째 매칭 결과를 반환하지만 match 메서드는 그렇지 않다.


