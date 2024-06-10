# :fire: 43장. Ajax

## :one: Ajax란?

- 자바스크립트를 사용하여 브라우저가 서버에게 비동기 방식으로 데이터를 요청하고, 서버가 응답한 데이터를 수신하여 웹페이지를 동적으로 갱신하는 프로그래밍 방식.
- XMLHttpRequest 객체 기반. 이는 HTTP 비동기 통신을 위한 메서드와 프로퍼티를 제공한다.
- 기존의 웹페이지와는 달리, 웹페이지의 변경에 필요한 데이터만 비동기 방식으로 전송받아 그 부분만 한정적으로 렌더링하는 방식 → 브라우저도 데스크톱 앱과 유사한 빠른 퍼포먼스가 가능해짐.

#### Ajax의 장점 
- 불필요한 데이터 통신 발생하지 않는다.
- 불필요한 부분은 다시 렌더링 하지 않으므로 화면이 순간적으로 깜박이는 현상이 발생하지 않는다.
- 클라이언트 서버의 통신이 비동기 방식으로 동작하기 때문에 블로킹이 발생하지 않는다.

---

## :two: JSON

- 클라이언트와 서버 간 HTTP 통신을 위한 텍스트 데이터 포맷.
- 자바스크립트에 종속되지 않는 언어 독립형 데이터 포맷.
- 객체 리터럴과 유사하게, 키와 값으로 구성된 순수한 텍스트.
- 키는 반드시 큰따옴표로 묶어야한다!
- JSON.stringify 메서드로 객체를 JSON 포맷의 문자열로 변환한다.
```javascript
 JSON.stringify(value[, replacer[, space]])
// replacer는 JSON 문자열이 반환되기 전 그 값을 변환하는 함수 또는 배열이다.
// space는 최종 문자열의 간격을 제어한다.
```

- JSON.parse 메서드로 JSON 포맷의 문자열을 객체로 변환한다.
```javascript
  JSON.parse(text[, reviver])
// reviver가 주어지면 분석한 값을 반환하기 전에 변환한다.
```
https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify

---

## :three: XMLHttpRequest

- 자바스크립트를 사용한 HTTP 요청 전송에 사용되는 객체.
- 생성자 함수를 호출하여 생성한다.
- Web API 이므로 브라우저 환경에서만 실행된다.

### HTTP 요청 전송

- XMLHttpRequest.prototype.open 메서드로 HTTP 요청을 초기화.
- 필요에 따라 XMLHttpRequest.prototype.setRequestHeader 메서드로 특정 HTTP 요청의 헤더 값 설정.
- XMLHttpRequest.prototype.send 메서드로 HTTP 요청을 전송한다.
```javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', '/users');
xhr.setRequestHeader('content-type', 'application/json');
xhr.send();
```

### HTTP 응답 처리

- 서버가 전송한 응답을 처리하려면, XMLHttpRequest 객체가 발생시키는 이벤트를 캐치해야한다.
- HTTP 요청의 현재 상태를 나타내는 readyState 프로퍼티 값이 변경된 경우 발생하는 readystatechange 이벤트를 캐치하여 HTTP 응답을 처리할 수 있다.
```javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', '/users');
xhr.send();
xhr.onreadystatechange = () => {
  if (xhr.readyState !== XMLHttpRequest.DONE) return;
  if (xhr.status === 200) {
    console.log(JSON.pare(xhr.response));
  } else {
    console.error('Error', xhr.status, xhr.statusText);
  }
}
```
