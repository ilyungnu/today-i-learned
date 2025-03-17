# \<details> 화살표 제거

```scss
summary::-webkit-details-marker {
  /* safari */
  display: none;
}
summary {
  list-style-type: none; /* safari 외 브라우저 */
}
```

# 글꼴 고정폭 적용 방법

```scss
font-feature-settings: "tnum";
font-variant-numeric: tabular-nums;
```

- 고정폭 글꼴(monospaced font) 사용
- OpenType 포맷을 제공하는 글꼴(예, Pretendard)에 고정폭 스타일 적용

# \<table> 테두리와 셀의 테두리 사이 간격 제거

```css
border-collapse: collapse;
```

- `collapse`: 간격 제거
- `separate`: 간격 생성

# \<textarea> 크기 고정

```css
textarea {
  resize: none;
}
```

- `<textarea>`에 `readonly` 속성 추가

input의 autocomplete 속성값으로 off를 넣어주면 된다

# \<a> tag 밑줄, 보라색 삭제

```css
a {
  color: black;
}
a:link {
  text-decoration: none;
}
a:visited {
  text-decoration: none;
}
a:hover {
  text-decoration: none;
}
a:focus {
  text-decoration: none;
}
a:active {
  text-decoration: none;
}
```

`:visited`, `:link`는 `:any-link`로 통합할 수 있으나, 현재 기준 Safari 브라우저에서 제대로 동작하지 않는다.(추후 지원 예정)
