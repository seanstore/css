# position

## static

배치 기준이 없는 것과 같다. 그냥 흐름에 따라 배치된다.
left, right, top, bottom, z-index 속성을 사용할 수 없다.

## relative

박스의 현재 위치를 기준으로 배치된다.
배치를 변경할 때 다른 박스의 흐름을 깨지 않는다.
left, right, top, bottom, z-index, inset 속성을 사용할 수 있다.

## absolute

일반적인 흐름에서 완전히 이탈한다.
부모 박스가 relative, absolute, fixed, transform 일 때, 부모 박스를 기준으로 배치된다.
left, right, top, bottom, z-index, inset 속성을 사용할 수 있다.

## fixed

뷰포트가 배치 기준이다.
부모 요소에 transform 속성이 있으면 transform 속성이 있는 부모 요소가 배치 기준이 된다.
left, right, top, bottom, z-index, inset 속성을 사용할 수 있다.

## sticky

스크롤 박스가 배치 기준이다.
평소에는 static 상태와 같이 일반적인 흐름에 따르지만 스크롤 위치가 임계점에 이르면 fixed와 같이 박스가 화면에 고정된다.
left, right, top, bottom, z-index, inset 속성을 사용할 수 있다.

## z-index

z-index는 부모에 종속된다. 즉, 자식 요소의 z-index 절대값이 아무리 커도 부모 요소의 z-index 값이 형제 요소보다 낮다면 형제 요소가 가장 위로 올라온다.
