# 박스 모델

- 모든 HTML 요소는 Box형태의 영역을 가지고 있음
- Box는 콘텐트, 패딩, 테두리, 마진으로 구성됨

![https://poiemaweb.com/img/box-model.png](https://poiemaweb.com/img/box-model.png)

- 브라우저는 박스 모델의 크기와 프로퍼티(색, 배경, 모양 등), 위치를 근거로 하여 렌더링을 실행
- 웹디자인은 콘텐츠를 담을 [박스 모델을 정의](https://poiemaweb.com/css3-display#1-display-%ED%94%84%EB%A1%9C%ED%8D%BC%ED%8B%B0)하고 CSS 프로퍼티를 통해 스타일([배경](https://poiemaweb.com/css3-background), [폰트와 텍스트](https://poiemaweb.com/css3-font-text)
   등)과 [위치](https://poiemaweb.com/css3-position) 및 [정렬](https://poiemaweb.com/css3-float)을 지정하는 것이라고 할 수 있다.
- 박스모델을 구성하는 : 콘텐트, 패딩, 테두리, 마진
  | 명칭 | 설명 |
  | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
  | Content | 요소의 텍스트나 이미지 등의 실제 내용이 위치하는 영역이다. width, height 프로퍼티를 갖는다. |
  | Padding | 테두리(Border) 안쪽에 위치하는 요소의 내부 여백 영역이다. padding 프로퍼티 값은 패딩 영역의 두께를 의미하며 기본색은 투명(transparent)이다. 요소에 적용된 배경의 컬러, 이미지는 패딩 영역까지 적용된다. |
  | Border | 테두리 영역으로 border 프로퍼티 값은 테두리의 두께를 의미한다. |
  | Margin | 테두리(Border) 바깥에 위치하는 요소의 외부 여백 영역이다. margin 프로퍼티 값은 마진 영역의 두께를 의미한다. 기본적으로 투명(transparent)하며 배경색을 지정할 수 없다. |
  ![https://poiemaweb.com/img/chrome-devtools.png](https://poiemaweb.com/img/chrome-devtools.png)

# 1. width/ height 프로퍼티

- 요소의 너비와 높이를 지정하기 위해 사용
- 이때 **지정되는 요소의 너비와 높이는 콘텐츠 영역을 대상**으로 함
- 만일 width와 height로 지정한 콘텐츠 영역보다 실제 콘텐츠가 크면 **콘텐츠 영역을 넘치게 된다는 것**에 유의
- `overflow: hidden` : 넘친 콘텐츠를 감출 수 있음
- 기본적으로 width와 height 프로퍼티는 콘텐츠 영역을 대상으로 요소의 너비와 높이를 지정하므로 박스 전체 크기는 다음과 같이 계산
  - 전체 너비: width + left padding + right padding + left border + right border + left margin + right margin
  - 전체 높이: height + top padding + bottom padding + top border + bottom border + top margin + bottom margin
    ![https://poiemaweb.com/img/box-model-calc.png](https://poiemaweb.com/img/box-model-calc.png)
  - 전체 너비: 492px = 20px + 6px + 20px + 400px + 20px + 6px + 20px
  - 전체 높이: 192px = 20px + 6px + 20px + 100px + 20px + 6px + 20px
- 예를 들어 block 요소의 경우, width는 부모 요소의 100%, height는 콘텐츠의 높이로 지정
- 명시적으로 지정하기 위해서는 px, % 등의 [크기 단위](https://poiemaweb.com/css3-units#section-1)를 사용
- width와 height 프로퍼티를 비롯한 모든 박스모델 관련 프로퍼티 (margin,padding,border, box-sizing 등)은 [상속](https://poiemaweb.com/css3-inheritance-cascading)되지 않는다.

# 2. margin, padding 프로퍼티

- 콘텐츠의 4개의 방향에 대하여 지정 가능(top, right, left, bottom)
- 1개의 프로퍼티 만으로 4방향의 프로퍼티 한번에 지정
  - 4개의 값: 위, 오른쪽, 아래, 왼쪽 → 시계방향
    - margin: 25px 50px 75px 100px;
  - 3개의 값: 위, 오른쪽/왼쪽, 아래
    - margin: 25px 50px 75px;
  - 2개의 값: 위/아래, 오/왼
    - margin: 25px 50px;
  - 1개의 값: 위/아래/오/왼
    - margin: 25px;
- `margin: auto` 해당 요소를 브라우저 중앙에 위치 (중앙정렬 방법: [Horizontal & Vertical Centering](https://poiemaweb.com/snippet-centering))
- `max-width` 요소 너비가 브라우저 너비보다 클 때 사용, 브라우저 너비가 요소의 너비보다 좁아질 때 자동으로 요소의 너비가 줄어든다.
- 예를 들어 `max-width: 300px;`의 경우, 브라우저의 너비가 300px보다 작아지면 요소 너비는 브라우저의 너비에 따라서 작아진다. `min-width: 300px;`의 경우 브라우저의 너비가 300px보다 작아져도 요소 너비는 지정 너비(300px)을 유지한다.

# 3. border 프로퍼티

## 3.1 border-style

- 프로퍼티 값의 갯수에 따라 4개 방향(top, right, left, bottom)에 대하여 지정 가능

## 3.2 border-width

- 두께 지정, 4개의 방향 지정 가능
- `border-width`프로퍼티는 `border-style`과 함께 사용하지 않으면 적용되지 않는다.

## 3.3 border-color

- 색상 지정, 4개의 방향 지정 가능
- `border-width`프로퍼티는 `border-style`과 함께 사용하지 않으면 적용되지 않는다.

## 3.4 border-radius

- 모서리 둥글게, 단위(px, em 등)와 %를 사용
- 개별 지정 가능, 4개 모서리 한번에 지정 가능

## 3.5 border

- `border-width`, `border-style`, `border-color`를 한번에 설정하기 위한 shorthand 프로퍼티

# 4. box-sizing 프로퍼티

- width, height 프로피터의 대상 영역을 변경할 수 있음
- 기본 값은 content-box
  - width, height 프로퍼티의 대상 영역이 content 영역을 의미
- border-box로 지정하면 마진을 제외한 박스 모델 전체를 width, height 프로퍼티의 대상 영역으로 지정할 수 있어서 CSS Layout을 직관적으로 사용할 수 있게 한다.

![https://poiemaweb.com/img/box-sizing.png](https://poiemaweb.com/img/box-sizing.png)

- box-sizing 프로퍼티는 상속되지 않는다. 따라서 box-sizing 프로퍼티를 사용하도록 초기화하려면 아래와 같이 정의

```css
html {
  box-sizing: border-box;
}
*,
*:before,
*:after {
  box-sizing: inherit;
}
```
