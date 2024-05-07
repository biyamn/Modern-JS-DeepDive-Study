- Math는 수학적인 상수와 함수를 위한 프로퍼티와 메서드를 제공한다. 

# Math 프로퍼티
## Math.PI
- 원주율 값을 반환한다
# Math 메서드
## Math.abs
- 인수로 전달된 숫자의 절대값을 반환한다. 절대값은 반드시 0 또는 양수이어야 한다.
```
Math.abs(1) //1
Math.abs('') //0
Math.abs(undefined) //NaN
Math.abs() //NaN
Math.abs('string') //NaN
```
## Math.round
- 인수로 전달된 숫자의 소수점 이하를 반올림한 정수를 반환한다.
```
Math.round(1.4) //1
Math.round(1.6) //2
Math.round(-1.6) //-2
Math.round() //NaN
Math.round(1) //1
```

## Math.ceil
- 인수로 전달된 숫자의 소수점 이하를 올림한 정수를 반환한다. (소수점 이하 무조건 올림)
## Math.floor
- 인수로 전달된 숫자의 소수점 이하를 내림한 정수를 반환한다. 
## Math.sqrt
- 인수로 전달된 숫자의 제곱근을 반환한다.
## Math.random
- 임의의 난수를 반환한다. Math.random 메서드가 반환한 난수는 0에서 1 미만의 실수다. 즉 0은 포함되지만 1은 포함되지 않는다
## Math.pow
- 첫 번째 인수를 밑으로 두 번째 인수를 지수로 거듭제곱한 결과를 반환한다.
## Math.max
- 전달받은 인수 중에서 가장 큰 수를 반환한다. 인수가 전달되지 않으면 -infinity를 반환한다.
## Math.min
- 전달받은 인수 중에서 가장 작은 수를 반환한다. 인수가 전달되지 않으면 infinity를 반환한다.
