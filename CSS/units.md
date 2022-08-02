# CSS 프로퍼티 값의 단위

# 1. 키워드

- 각 프로퍼티에 따라 사용할 수 있는 키워드가 존재
- 예를 들어 [display 프로퍼티](https://poiemaweb.com/css3-display#1-display-%ED%94%84%EB%A1%9C%ED%8D%BC%ED%8B%B0)의 값으로 사용할 수 있는 키워드는 `block`, `inline`, `inline-block` , `none`이 있다.

# 2. 크기 단위

- cm, mm, inch 등의 단위도 존재하나 CSS에서 사용하는 대표적인 크기 단위는 `px`, `em`, `%`이다.
- `px`은 절대값이고 `em`, `%`는 상대값이다.
- 대부분 브라우저의 폰트 사이즈 기본값은 16px, 1em, 100%이다. 프로퍼티 값이 0인 경우, 단위를 생략할 수 있다.

## 2.1 px

- `px`는 픽셀(화소) 단위
- 요소의 크기나 이미지의 크기 지정에 주로 사용
- 1`px`은 화소 1개의 크기
- 픽셀은 디바이스 해상도에 따라 상대적인 크기를 갖는다. 디바이스 별로 픽셀(화소)의 크기는 제각각이기 때문에 픽셀을 기준으로 하는 단위는 명확하지 않다.
  - 따라서 **대부분의 브라우저는 1`px`을 1/96 인치의 절대단위로 인식**

## 2.2 %

- `%` 는 백분률 단위의 상대 단위
- 요소에 지정된 사이즈(상속된 사이즈나 디폴트 사이즈)에 상대적인 사이즈를 설정

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      body {
        font-size: 14px;
        text-align: center;
      }
      div {
        font-size: 120%; /* 14px * 1.2 = 16.8px */
        font-weight: bold;
        padding: 2em; /* 16.8px * 2 = 33.6px */
        background-color: rgba(255, 0, 0, 0.2);
      }
    </style>
  </head>
  <body>
    <div>Font size: 14px * 120% → 16.8px</div>
  </body>
</html>
```

## 2.3 em

- `em` 은 배수 단위로 상대 단위
- 요소에 지정된 사이즈(상속된 사이즈나 디폴트 사이즈)에 상대적인 사이즈를 설정
- 예를 들어 1`em` 은 요소에 지정된 사이즈와 같고 2`em` 은 요소에 지정된 사이즈의 2배
- 폰트 사이즈 설정이나 콘텐츠를 포함하는 컨테이너의 크기 설정에 사용하면 상대적인 설정이 가능하여 편리
- 중첩된 자식 요소에 `em` 을 지정하면 모든 자식 요소의 사이즈에 영향을 미치기 때문에 주의

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      body {
        font-size: 14px;
        text-align: center;
      }
      div {
        font-size: 1.2em; /* 14px * 1.2 = 16.8px */
        font-weight: bold;
        padding: 2em; /* 16.8px * 2 = 33.6px */
        background-color: rgba(255, 0, 0, 0.2);
      }
    </style>
  </head>
  <body>
    <div>Font size: 1.2em → 14px * 1.2 = 16.8px</div>
  </body>
</html>
```

## 2.4 rem

- `rem` 은 최상위 요소(html)의 사이즈를 기준으로 삼는다.
- `rem`의 r은 root
- Reset CSS를 사용하여 사전에 html 요소의 font-size 지정이 필요하다. font-size 미지정 시에는 16px가 적용된다.

## 2.5 Viewport 단위(vh, vw, vmin, vmax)

- 반응형 웹 디자인은 화면의 크기에 동적으로 대응하기 위해 `%` 단위를 자주 사용
- 하지만 `%` 단위는 `em` 과 같이 상속에 의해 부모 요소에 상대적 영향을 받는다.
- Viewport 단위는 상대적인 단위로 [viewport](https://poiemaweb.com/css3-responsive-web-design#viewport-meta-tag)를 기준으로 한 상대적 사이즈
- IE 8 이하는 지원하지 않으며 IE 9 ~ 11, Edge는 지원이 완전하지 않으므로 주의가 필요하다.

| 단위 | Description                                |
| ---- | ------------------------------------------ |
| vw   | viewport 너비의 1/100                      |
| vh   | viewport 높이의 1/100                      |
| vmin | viewport 너비 또는 높이 중 작은 쪽의 1/100 |
| vmax | viewport 너비 또는 높이 중 큰 쪽의 1/100   |

# 3. 색상 표현 단위

- 색상을 지정하기 위해 키워드를 사용할 수 있다. (ex, red, blue…)
- 사용이 간편하다는 장점이 있으나 표현할 수 있는 색상의 수는 제한됨
- 색상을 표현할 수 있는 키워드 리스트는 [W3C css3-color](https://www.w3.org/TR/css3-color/)를 참고하기 바란다.
- 더욱 다양한 색상을 표현하기 위해 다음과 같은 색상 표현 단위를 사용할 수 있다. [HTML COLOR CODES](http://htmlcolorcodes.com/)
  를 참조하면 편리하다.

| 단위                                            | 사용예                 |
| ----------------------------------------------- | ---------------------- |
| HEX 코드 단위 (Hexadecimal Colors)              | #000000                |
| RGB (Red, Green, Blue)                          | rgb(255, 255, 0)       |
| RGBA (Red, Green, Blue, Alpha/투명도)           | rgba(255, 255, 0, 1)   |
| HSL (Hue/색상, Saturation/채도, Lightness/명도) | hsl(0, 100%, 25%)      |
| HSLA (Hue, Saturation, Lightness, Alpha)        | hsla(60, 100%, 50%, 1) |
