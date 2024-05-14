## String 생성자 함수

표준 빌트인 객체인 String 객체는 생성자 함수 객체다. 따라서 new 연산자와 함게 호출하여 String 인스턴스를 생성할 수 있다.

### String.prototype.indexOf

indexOf 메서드는 대상 문자열에서 인수로 전달받은 문자열을 검색하여 첫 번재 인덱스를 반환한다.

### String.prototype.includes

대상 문자열에 인수로 전달받은 문자열이 포함되어 있는지 확인하여 그 결과를 true 또는 false로 반환한다.

### String.prototype.charAt

대상 문자열에서 인수로 전달받은 인덱스에 위치한 문자를 검색하여 반환한다.

### String.prototype.substring

대상 문자열에서 첫 번째 인수로 전달받은 인덱스에 위치하는 문자부터 두 번째 인수로 전달받은 인덱스에 위치하는 문자와 바로 이전 문자까지의 부분 문자열을 반환한다.

### String.prototype.slice

substring과 같은 역할을 하지만 음수인 인수를 전달할 수 있다.

### String.prototype.trim

대상 문자열 앞뒤에 공백 문자가 있을 경우 이를 제거한 문자열을 반환한다.

### String.prototype.replcae

대상 문자열에서 첫 번째 인수로 전달받은 문자열 또는 정규표현식을 검색하여 두 번째 인수로 전달한 문자열로 치환한 문자열로 반환한다.
