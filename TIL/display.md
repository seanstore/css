# display

display의 속성 값으로는 inline, block, inline-block, none 그리고 Lv3에서 추가된 flow-root, flex, grid, contents가 있다.

`position: absolute | fixed` 또는 `float: left | right`로 선언하게 되면 `display: block`으로 변경된다. 즉, 수평 배치에서 수직 배치로 변경된다.

## inline

흐름 방향이 수평이며, 너비 높이를 줄 수 없다.
수평 마진과 패딩은 줄 수 있지만 수직 마진은 줄 수 없다. 수직 패딩은 줄 수는 있지만 다른 요소를 밀어내지는 못해서 다른 요소와 겹친다.

## block

흐름 방향이 수직이며, 너비 높이를 줄 수 있다.
수평 마진과 패딩, 수직 마진과 패딩 모두 줄 수 있지만 수직 마진은 서로 중첩된다는 특징이 있다.

## inline-block

흐름 방향이 수평이며, 너비 높이를 줄 수 있다.
수평 마진과 패딩, 수직 마진과 패딩 모두 줄 수 있고 block과 다르게 수직 마진이 중첩되지 않는다.

## none

어떤 장치도 표시하거나 접근할 수 없다.
아래의 두 가지 방법으로 구현할 수 있다.

```css
.hidden {
  display: none;
}
```

```html
<p class="desc" hidden></p>
```

## flow-root

block 컨테이너가 되고, 포함된 콘텐츠는 새로운 블록 형식 문맥을 형성한다.
즉, float, margin 속성을 다르게 처리한다.

- 포함한 float 자식 요소는 일반적인 흐름에서 벗어나지만 float된 영역의 높이를 부모 컨테이너가 감지해서 반영한다.
  이를 흔히 float을 해제(clear)한다고 말한다. 자동으로 float이 해제된다.
- 부모 자식 요소의 수직 마진을 병합하지 않는다.

## flex

flex 컨테이너 박스를 생성하고, flex 형식 문맥을 형성한다.
포함된 아이템을 1차원 기반으로 배치한다.
grid와 비교해서 격자에 구애받지 않는 flex만 가능한 배치가 존재한다.
대표적으로 가운데 정렬이 있다.

## grid

grid 컨테이너 박스를 생성하고, grid 형식 문맥을 형성한다.
포함된 아이템을 2차원 기반으로 배치한다.
flex와 비교해서 grid만 가능한 배치가 존재한다.
대표적으로 셀 병합 아이템 배치가 있다.
