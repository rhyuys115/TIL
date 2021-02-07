# CSS

> 스타일, 레이아웃 등을 통해 문서(HTML)를 표시하는 방법을 지정하는 언어

<br>

## 1. CSS 구문

- 구문은 선택자와 함께 열린다.
- 스타일을 지정할 html 요소를 선택
- 다음 중괄호가 있는데 이 안에는 속상과 값 쌍형태를 가지는 하나 또는 그 이상의 선언이 있다.
- 각 쌍은 우리가 선택한 요소의 속성을 지정하고 속성에 부여할 값을 지정한다.

<br>

### 1.1 선언문

```css
/*선택자(selector*/
h1 {
     /*선언(declartion)*/
    color:blue;
    font-size/*속성(property)*/: 15px/*값(valu)e*/;
}
```

- 속성(property)
  - 사람이 읽을 수 있는 식별자로, 어떤 스타일 기능(글꼴, 너비, 배경색 등) 스타일 기능을 변경할지 나타낸다.
- 값(value)
  - 각 속성에는 값을 부여한다.
  - 값은 어떻게 (글꼴을 이걸로, 배경 색을 저걸로 등) 스타일 기능을 변결할 건지 나타낸다.

<br>

### 1.2 CSS 정의 방법

1. `Inline style`

```html
<h1 style="color: blue; font-size: 100px;">
    Hello
</h1>
```

 해당 태그에 직접 style 속성을 활용

<br>

2. 내부 참조(`Embedding style`)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
      h1 {
          color: blue;
          font-size: 100px;
      }
    </style>
</head>
<body>
  
</body>
</html>
```

head 태그 내에 <style> 에 지정

<br>

3. 외부  참조(`Link style`)

```html
<link rel="stylesheet" href="mystyle.css">
```

​    외부 CSS 파일을<head>내 <link>를 통해 불러오기

<br>

### CSS Selector

