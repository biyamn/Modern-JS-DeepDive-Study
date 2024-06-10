# :fire: 44장. REST API

- REST: HTTP 장점을 최대한 활용할 수 있는 아키텍처. HTTP를 기반으로 클라이언트가 서버의 리소스에 접근하는 방식을 규정한 아키텍처.
- RESTful: REST의 기본 원칙을 성실하게 지킨 서비스 디자인.

## :one: REST API의 구성

다음 3가지 요소로 구성된다.
- 자원: 자원. URI로 표현.
- 행위: 자원에 대한 행위. HTTP 요청 메서드로 표현.
- 표현: 자원에 대한 행위의 구체적 내용. 페이로드로 표현.

---

## :two: REST API 설계 원칙

기본 원칙은 2가지 이다.
- URI는 리소스를 표현하는데 집중한다.
  - 명사를 사용한다.
- 행위에 대한 정의는 HTTP 요청 메서드를 통해 한다.
  - 주로 5가지 요청 메서드(GET, POST, PUT, PATCH, DELETE)를 사용하여 CRUD를 구현한다.
  - 행위는 URI에 표현하지 않는다.
 
### json-server로 REST API 실습

⬇️ json-server 설치와 실행 방법 <br />
https://www.npmjs.com/package/json-server

```javascript
// db.json
{
  "todos": [
    {
      "id": "1",
      "content": "HTML",
      "completed": true
    },
    {
      "id": "2",
      "content": "CSS",
      "completed": false
    },
    {
      "id": "3",
      "content": "Javascript",
      "completed": true
    }
  ]
}
```

```html
<!-- get_index.html
     todos 데이터 전체 목록이 뜬다. -->


<!DOCTYPE html>
<html lang="en">
<body>
    <pre></pre>
    <script>
        const xhr = new XMLHttpRequest();
        xhr.open('GET', '/todos');
        xhr.send();
        xhr.onload = () => {
            if (xhr.status === 200) {
                document.querySelector('pre').textContent = xhr.response;
            } else {
                console.error('Error', xhr.status, xhr.statusText);
            }
        };
    </script>
</body>
</html>
```

```html
<!-- get_retrieve.html
     todos 데이터 중 URI로 지목된 항목만 뜬다. -->

<!DOCTYPE html>
<html lang="en">
<body>
    <pre></pre>
    <script>
        const xhr = new XMLHttpRequest();
        xhr.open('GET', '/todos/1');
        xhr.send();
        xhr.onload = () => {
            if (xhr.status === 200) {
                document.querySelector('pre').textContent = xhr.response;
            } else {
                console.error('Error', xhr.status, xhr.statusText);
            }
        }
    </script>
</body>
</html>
```

```html
<!-- post.html
     새로운 리소스를 생성한다. -->

<!DOCTYPE html>
<html lang="en">
<body>
    <pre></pre>
    <script>
        const xhr = new XMLHttpRequest();
        xhr.open('POST', '/todos');
        xhr.setRequestHeader('content-type', 'application/json');
        xhr.send(JSON.stringify({id: 4, content: 'Angular', completed: false}));
        xhr.onload = () => {
            if (xhr.status === 200 || xhr.status === 201) {
                document.querySelector('pre').textContent = xhr.response;
            } else {
                console.error('Error', xhr.status, xhr.statusText);
            }
        }
    </script>
</body>
</html>

<!-- db.json을 확인하면 입력한 리소스가 저장되어있음을 확인할 수 있다. -->
```

```html
<!-- put.html
     특정 리소스 전체를 교체한다. -->

<!DOCTYPE html>
<html lang="en">
<body>
    <pre></pre>
    <script>
        const xhr = new XMLHttpRequest();
        xhr.open('PUT', '/todos/4');
        xhr.setRequestHeader('content-type', 'application/json');
        xhr.send(JSON.stringify({id: 4, content: 'React', completed: true}));
        xhr.onload = () => {
            if (xhr.status === 200) {
                document.querySelector('pre').textContent = xhr.response;
            } else {
                console.error('Error', xhr.status, xhr.statusText);
            }
        }
    </script>
</body>
</html>

<!-- 4번 항목 content가 'Angular'에서 'React'로 변경되었음을 확인할 수 있다. -->
```

```html
<!-- patch.html
     특정 리소스의 일부를 수정한다. -->

<!DOCTYPE html>
<html lang="en">
<body>
    <pre></pre>
    <script>
        const xhr = new XMLHttpRequest();
        xhr.open('PATCH', '/todos/4');
        xhr.setRequestHeader('content-type', 'application/json');
        xhr.send(JSON.stringify({completed: false}));
        xhr.onload = () => {
            if (xhr.status === 200) {
                document.querySelector('pre').textContent = xhr.response;
            } else {
                console.error('Error', xhr.status, xhr.statusText);
            }
        }
    </script>
</body>
</html>

<!-- 4번 항목 completed의 내용이 true에서 false로 수정되었음을 확인할 수 있다. -->
```

```html
<!-- delete.html
     특정 리소스를 삭제한다. -->

<!DOCTYPE html>
<html lang="en">
<body>
    <pre></pre>
    <script>
        const xhr = new XMLHttpRequest();
        xhr.open('DELETE', '/todos/4');
        xhr.send();
        xhr.onload = () => {
            if (xhr.status === 200) {
                document.querySelector('pre').textContent = xhr.response;
            } else {
                console.error('Error', xhr.status, xhr.statusText);
            }
        }
    </script>
</body>
</html>

<!-- 4번 항목이 삭제되었음을 확인할 수 있다. -->
```
