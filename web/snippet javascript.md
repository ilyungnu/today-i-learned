# \<input> file read

```html
<input id="sqlFileInput" type="file" />
```

```js
const sqlFileInput = document.getElementById("sqlFileInput")

const ReadFile = (CALLBACK, ENCODING) => {
  const READER = new FileReader()
  const FILENAME = event.target.files[0].name

  READER.readAsText(event.target.files[0], ENCODING) //파일읽기
  READER.onload = function () {
    //읽기완료
    CALLBACK(READER, FILENAME)
  }
}

sqlFileInput.addEventListener("input", () => ReadFile(console.log, "UTF-8"))
```

- `READER.result`가 파일의 내용이다

# local storage

브라우저에 key-value로 데이터를 저장할 수 있는 storage다. storage에는 문자열 데이터만 저장할 수 있고, 저장된 데이터는 세션간 공유가 되어 세션이 바뀌어도 저장된 데이터는 사라지지 않고 유지된다. 기본적인 사용법은 아래와 같다.

```js
window.localStorage.setItem(key, value) //저장
window.localStorage.getItem(key) //조회
window.localStorage.removeItem(key) //삭제
window.localStorage.clear() //전체삭제
```

# 숫자가 아닌 문자 제거(replace)

```js
x.replace(/\D/g,"")
```
: 숫자가 아닌 모든 문자를 찾아서 제거한 문자열을 반환

- \D : 숫자가 아닌 모든 문자
- /.../ : 정규식 리터럴
- g : 모든 문자