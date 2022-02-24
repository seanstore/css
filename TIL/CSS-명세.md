# CSS 명세

## 값 정의 구문 이해하기

### 값의 유형

- 키워드: 예약어로 대소문자를 구별하지 않고, 따옴표 없이 사용된다.
- 기본 데이터 타입: 꺽쇠 안에 데이터 타입을 명시하는 형태로 사용된다.
  `<string>`, `<url>`, `<percentage>`, `<position>`...
  - 꺽쇠 안에 따옴표를 포함한 속성 이름이 명시되는 경우에는 그 이름의 속성 값을 참조한다.
    `<'grid-template'>`

### 결합 기호

1. 공백: 공백으로 연결되어 있는 두 값 모두 필수이며 순서가 유지되어야 한다.
2. &&(and): &&로 연결되어 있는 두 값 모두 필수이며 순서는 상관 없다.
3. ||(or): ||로 연결되어 있는 두 값 중 하나 이상 필수이며 순서는 상관 없다.
4. |(only): |로 연결되어 있는 두 값 중 하나만 선택해야 한다.
5. \[](group)

1~4번 순서로 우선순위가 높으며 우선순위에 따라 먼저 해석해야 한다.

```txt
a b | c || d && e f
```

그룹으로 먼저 묶어 놓으면 해석하기 쉽다.

```txt
[a b] | [c || [d && [e f]]]
```

### 증가 기호

- \*: 횟수 제한 없음
- +: 1회 이상
- ?: 0 또는 1회
- {A}: A회
- {A, B}: A회 이상 B회 이하
- {A,}: A회 이상
- #{1, A}: 1회 이상 A회 이하
  `<length>#{1, 4}`
- []!: 그룹에서 1회 이상

<img width="780" alt="스크린샷 2022-02-24 오후 4 02 54" src="https://user-images.githubusercontent.com/100114050/155475115-aa58b4fa-28fc-4342-967a-e5c05514a95a.png">

|(only), ||(or)에서 관심 없는 값을 제거하면 된다.

```txt
[<'font-style'> || <'font-weight'>]? <'font-size'>[/<'line-height'>]? <'font-family'>
```

```css
font: italic bold 16px/24px Sans-serif;
font: bold italic 16px/24px Sans-serif;
font: bold 16px Sans-serif;
font: 16px Sans-serif;
```
