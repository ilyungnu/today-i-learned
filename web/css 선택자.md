# 기본선택자

## 전체선택자 `*`

- 모든 형태의 요소 선택
- 단순 선택자에서 `*` 는 선택사항 → `.warning` = `*.warning`

## 유형선택자 `element`

- 노드 이름을 이용해 요소 선택
- 즉, 문서 내에서 주어진 유형의 모든 요소 선택

## 클래스 선택자 `.`

- 요소의 클래스 속성에 기반해 요소 선택

## ID 선택자 `#`

- id 특성에 따라 요소 선택 `[id=id.value]` 랑 같음

## 특성 선택자 `[]`

- 대소문자는 구별 하지 않으며, 주어진 특성의 존재여부나 그 값에 따라 요소를 선택
- `[attr]` : attr라는 이름의 특성을 가진 요소 선택
- `[attr=value]` : attr라는 특성 값이 정확히 value인 요소 선택
- `[attr|=value]` : attr라는 특성 값을 가지고 있으며, 그 특성값이 정확히 value이거나 value로 시작하면서 `-`문자가 곧바로 뒤에 따라 붙으면 이 요소 선택
  - 보통 언어 서브 코드 (en-US, ko-KR) 가 일치하는지 확인 할 때 사용
- `[attr^=value]` : attr라는 특성 값을 가지고 있으며, 접두사로 value가 값에 포함되어 있으면 이 요소 선택
  - `^` 가 `$` 이면 미포함, `*` 면 하나 이상 포함
- `[attr operator value i]` : 값의 대소문자 구별 안함(아스키 범위 내)
  - `i` 가 `s` 면 구별 함

# 그룹선택자

## `,`

- 일치하는 모든 요소를 선택하여, 스타일 시트 크기를 줄일 수 있다
- 요소는 한줄에 하나 씩 배치해도 되고 여러줄에 배치해도 된다
- 단, 선택한 목록 내의 하나의 선택자라도 브라우저가 지원하지 않으면 전체목록을 무효화한다
  → 이는 `:is()` 를 사용해 무시할 수 있으나, `:is()`가 명시도를 계산하는 방법으로 인해 모든 선택자가 동일한 명시도를 갖게 된다

# 결합자

## 자손결합자 `A B`

- 공백으로 표현, 첫번째 요소의 자손인 노드 선택

## 자식결합자 `A > B`

- 첫번째 노드의 요소의 바로 아래 자식인 노드 선택

## 일반 형제 결합자 `A ~ B`

- 형제, 즉 첫번째 요소를 뒤따르면서 같은 부모를 공유하는 요소 모두 선택

## 인접 형제 결합자 `A + B`

- `~`와 같지만 바로 뒤 하나만 선택

## 열 결합자 `A || B`

- A부터 B사이의 노드요소들 선택

# 의사클래스(가상클래스)

css에서 선택자에 추가하는 키워드로, 선택한 요소가 특정 상태일 때 적용되는 클래스

| 의사클래스      | 설명                                                                   |
| --------------- | ---------------------------------------------------------------------- |
| `:link`         | 방문하지 않은 요소일 때                                                |
| `:visited`      | 방문 한 적이 있는 요소일 때                                            |
| `:any-link`     | 방문여부 상관 없이 선택(link + visited) <br> \*Safari 지원 예정        |
| `:hover`        | 포인팅 장치로 상호작용 중일 때 <br> 예. 요소 위에 마우스가 올려진 상태 |
| `:focus`        | 요소에 초점이 맞춰졌을 때                                              |
| `:focus-within` | 자식요소에 초점이 맞춰졌을 때                                          |
| `:active`       | 요소를 활성화했을 때 <br> 예. 마우스를 누른 순간부터 떼는 시점까지     |

- 의사클래스는 `:link` > `:visited` > `:hover` > `:focus` > `:active` 과 같이 작동순으로 작성해야 override하지 않고 제대로 동작한다.
- `:hover` 터치스크린 기기에서 제대로 작동하지 않을 수 있기 때문에 이을 감안하여 개발해야 한다
