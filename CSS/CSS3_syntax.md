# CSS 기본 문법

# CSS(Cascading Style Sheets)는?

- HTML이나 XML과 같은 구조화된 문서를 화면, 종이 등에 어떻게 렌더링할 것인지를 정의하기 위한 언어
- HTML의 각 요소의 style을 정의하여 화면 등에 어떻게 렌더링하면 되는지 브라우저에게 설명하기 위한 언어

![https://poiemaweb.com/img/html-css.png](https://poiemaweb.com/img/html-css.png)

- HTML5 이전 버전에서는 style을 컨트롤할 수 있는 태그(font, center)가 존재하여 CSS가 없이도 어느 정도의 스타일 표현이 가능하였으나 정보와 구조를 담당하는 HTML의 본연의 역할과 동떨어진 기능까지 추가됨으로서 복잡하고 혼란스러운 언어가 되어버림
  - 그래서 HTML5에서는 **HTML은 정보와 구조화, CSS는 styling의 정의**라는 본연의 임무에 충실한 명확한 구분이 이루어짐
- HTML과 CSS는 각자의 문법을 갖는 별개의 언어
- HTML은 CSS를 포함할 수 있으나, HTML없이 단독으로 존재하는 CSS는 의미없음

# CSS3의 용어

## 1. 셀렉터 (Selector, 선택자)

- 스타일을 적용하고자하는 HTML 요소를 선택하기 위해 CSS에서 제공하는 수단
  ![https://poiemaweb.com/img/css-syntax.png](https://poiemaweb.com/img/css-syntax.png)
- 위와 같은 구문을 Rule Set(또는 Rule)이라 하며 셀렉터에 의해 선택된 특정 HTML요소를 어떻게 렌더링할 것인지 브라우저에 지시하는 역할
- HTML문서에 속해 있는 셀렉터를 통해 모든 h1 요소를 선택한 후 선택된 h1 요소의 스타일을 선언 블록에서 정의하고 있음
- 위와 같은 Rule Set의 집합을 스타일시트라고 함

## 2. 프로퍼티 (Property, 속성)

- 셀렉터로 HTML 요소를 선택하고 `{}` 내에 프로퍼티(속성)와 값을 지정하는 것으로 다양한 style 정의
- 프로퍼티는 [표준 스펙](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference#Keyword_index)으로 이미 지정되어 있는 것을 사용하여야하며 사용자가 임의로 정의할 수 없음
- 여러 개의 프로퍼티를 연속해서 지정할 수 있으며 `세미콜론(;)`으로 구분

## 3. 값 (Value, 속성값)

- 프로퍼티의 값은 해당 프로퍼티에 사용할 수 있는 값을 `키워드`나 `크기 단위` 또는 `색상 표현 단위` 등의 [특정 단위](https://poiemaweb.com/css3-units)로 지정

```css
p {
  color: red;
  font-size: 12px;
}
```

## 4. HTML과 CSS의 연동

- HTML은 CSS를 포함할 수 있음
- CSS를 가지고 있지 않은 HTML은 브라우저에서 기본으로 적용하는 CSS에 의해 렌더링 됨

### 4.1 Link style

- 가장 일반적인 방법
- HTML에서 외부에 있는 CSS파일을 로드하는 방식

```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="css/style.css" />
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a web page.</p>
  </body>
</html>
```

### 4.2 Embedding style

- HTML 내부에 CSS를 포함시키는 방식
- 매우 간단한 웹페이지의 경우는 문제 없지만, Link style 사용하는 편이 나음
- **HTML과 CSS는 서로 역할이 다르니까 다른 파일로 구분되어 작성하고 관리하는 것이 바람직**

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      h1 {
        color: red;
      }
      p {
        background: aqua;
      }
    </style>
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a web page.</p>
  </body>
</html>
```

### 4.3 Inline style

- HTML요소의 style프로퍼티에 CSS를 기술하는 방식
- 자바스크립트가 동적으로 CSS를 생성할 때 사용하는 경우
- 하지만 일반적으로 Link style을 사용하는 편이 좋음

```html
<!DOCTYPE html>
<html>
  <body>
    <h1 style="color: red">Hello World</h1>
    <p style="background: aqua">This is a web page.</p>
  </body>
</html>
```

## 5. Reset CSS 사용하기

- 모든 웹 브라우저는 디폴트 스타일(브라우저가 내장하고 있는 기본 스타일)을 가지고 있어 CSS가 없어도 작동
- 그런데 웹 브라우저에 따라 티폴트 스타일이 상이하고 지원하는 tag, style도 제각각이어서 주의 필요
- Reset CSS는 기본적인 HTML요소의 CSS를 초기화하는 용도로 사용
- === 브라우저 별로 제각각인 디폴트 스타일을 하나의 스타일로 통일시켜 주는 역할
- 자주 사용되는 Reset CSS
  - [Eric Meyer’s reset](http://meyerweb.com/eric/tools/css/reset/)
  - [normalize.css](https://necolas.github.io/normalize.css/)

## 6. CSS versions

| Version | Year |
| ------- | ---- |
| CSS3    | 2005 |
| CSS2    | 1998 |
| CSS1    | 1996 |
