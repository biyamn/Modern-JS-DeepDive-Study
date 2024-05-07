# Number 생성자 함수
- 생성자 함수의 인수로 숫자가 아닌 값을 전달하면 인수를 숫자로 강제 변환한 후, 숫자를 할당한 Number 래퍼 객체를 생성한다.
```
const numObj = new Number();
console.log(numObj); // Number {[[PrimitiveValue]]: 0}
numObj = new Number(10);
console.log(numObj); // Number {[[PrimitiveValue]]: 10}
numObj = new Number('hello');
console.log(numObj); // Number {[[PrimitiveValue]]: NaN}
```

# Number 프로퍼티
## Number.EPSILON
- 부동소수점을 비교하는 함수. 1과 1보다 큰 숫자 중에서 가장 작은 숫자와의 차이와 같다.
## Number.MAX_VALUE
- 자바스크립트에서 표현할 수 있는 가장 큰 양수 값
## Number.MIN_VALUE
- 자바스크립트에서 표현할 수 있는 가장 작은 양수 값
## Number.MAX_SAFE_INTEGER
- 안전하게 표현할 수 있는 가장 큰 정수 값
## Number.MIN_SAFE_INTEGER
- 안전하게 표현할 수 있는 가장 작은 정수 값
## Number.POSITIVE_INFINITY
- 양의 무한대
## Number.NEGATIVE_INFINITY
- 음의 무한대
## Number.NAN
- 숫자가 아님을 나타내는 숫자값

# Number 메서드
## Number.isFinite
- 인수로 전달된 숫자값이 정상적인 유한수, 즉 infinity 또는 -infinity가 아닌지 검사하여 그 결과를 불리언으로 반환
```
Number.isFinite(0); //true
Number.isFinite(Infinity) //false
```

## Number.isInteger
- 인수로 전달된 숫자값이 정수인지 검사하여 그 결과를 불리언 값으로 반환한다. 
```
Number.isInteger(0); //true
Number.isInteger(Infinity) //false
```

## Number.isNaN
- 인수로 전달된 숫자값이 NaN인지 검사하여 그 결과를 불리언 값으로 반환한다.

## Number.isSafeInteger
- 안전한 정수인지 검사하여 그 결과를 불리언 값으로 반환한다. 검사전에 인수를 숫자로 암묵적 타입 변환하지 않는다.
## Number.prototype.toExponential
- 숫자를 지수 표기법으로 변환하여 문자열로 반환한다. 지수 표기법이란 매우 크거나 작은 숫자를 표기할 때 주로 사용하며 e앞에 있는 숫자에 10의 n승을 곱하는 형식으로 수를 나타내는 방식이다. 
## Number.prototype.toFixed
- 숫자를 반올림하여 문자열로 반환한다. 반올림하는 소수점 이하 자릿수를 나타내는 0~20 사이의 정수값을 인수로 전달할 수 있다. 
## Number.prototype.toPrecision
- 인수로 전달받은 전체 자릿수까지 유효하도록 나머지 자릿수를 반올림하여 문자열로 반환.인수를 생략하면 기본값 0이 지정된다.
## Number.prototype.toString
- 숫자를 문자열로 변환하여 반환.
```
(10).toString(); //'10'
(10).toString(2); //'10000' 이진수 문자열을 반환
```