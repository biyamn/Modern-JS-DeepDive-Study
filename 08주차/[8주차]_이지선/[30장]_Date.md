# Date

- 표준 빌트인 객체이자 생성자 함수
- KST는 UTC(국제 표준 시이며 GMT라고도 불림)에 9시간을 더한 시간

# Date 생성자 함수

1. new Date()

   ```jsx
   new Date(); // Mon JUl 06 2020 01:03:18 GMT+0900 (대한민국 표준시)
   ```

2. new Date(milliseconds)
   - 인수로 전달된 밀리초만큼 경과한 날짜와 시간을 나타내는 Date 객체 반환
3. new Date(dateString)

   - 지정된 날짜와 시간을 나타내는 Date 객체 반환

   ```jsx
   new Date('May 26, 2020 10:00:00);
   new Date('2020/03/26/10:00:00');
   ```

4. new Date(year, month[, day, hour, minute, second, millisecond])

# Date 매서드

1. Date.now

   - 1970년 1월 1일 00:00:00(UTC)를 기점으로 현재 시간까지 경과한 밀리초를 숫자로 반환

   ```jsx
   const now = Date.now(); // 14028230923

   new Date(now); // Mon JUl 06 2020 01:03:18 GMT+0900 (대한민국 표준시)
   ```

2. Date.parse
   - 전달된 인수까지의 밀리초를 숫자로 반환
3. Date.UTC
4. Date.prototype.getFullYear/getMonth/getDate/getHours/getMinutes/getSeconds/getMilliseconds
   - 반환
5. Date.prototype.setFullYear/setMonth(0~11)/setDate(1~31)/setHours(0~23)/setMinutes(0~59)/setSeconds/setMilliseconds(0~999)

   - 설정

   ```jsx
   const today = new Date();

   today.setFullYear(2000);
   today.getFullYear(); // 2000
   ```

6. Date.prototype.getTime/Date.prototype.setTime
   - 기점으로 Date 객체의 시간까지 경과된 밀리초 반환, 설정
7. Date.prototype.toString
8. Date.prototype.toTimeString
9. Date.prototype.toISOString
10. Date.prototype.toLocaleString

    ```jsx
    const today = new Date('2020/7/24/12:30');

    today.toSring();
    today.toLocaleString('ko-KR');
    ```

11. Date.prototype.toLocaleTimeString
    - 시간만
