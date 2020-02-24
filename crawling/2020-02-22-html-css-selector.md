# HTML
- Hyper Text Markup Language
- 웹 문서를 작성하는 마크업 언어입니다.

<!-- more -->
- 웹페이지를 구성하는 언어에는 3종류가 있습니다.
  - HTML : 화면의 레이아웃이나 텍스트
  - CSS : 화면의 색상 크기 등의 스타일
  - Javascript : 화면의 클릭, 드래그 등등의 이벤트


## 1.1 HTML의 구성요소
**`Document`**
- 페이지 전체
**`element`**
- 계층적 구조로 이루어져 있으며 모여서 Document가 됩니다.
- 시작 태그와 끝 태그로 구성되어 있습니다. `<div> </div>`
**`Tag`**
- 시작태그와 끝 태그로 엘리먼트를 구성합니다.
- 시작 태그에는 여러가지 속성값들이 들어 있습니다.
- 태그와 태그 사이에는 문자열 데이터를 가질수 있습니다.
- 태그의 이름에 따라서 태그의 목적이 달라집니다.
**`Attribute`**
- 시작 태그 안에 포함되는 속성값입니다.
- `id`, `class` : 엘리먼트를 선택하기 위한 목적으로 만들어진 속성값입니다.
- 이 외에도 다양한 속성값이 존재 합니다.

### 1.2 속성값
**`id`** : 웹페이지에서 유일한 값입니다.
**`class`** :
- 웹 페이지 내에서 여러개의 class가 존재합니다.
- 하나의 엘리먼트에 여러개의 class를 부여할수 있습니다.
**`type`** : 엘리먼트 형태를 결정합니다. (button, checkbox 등)
**`style`** : CSS 스타일 값을 적용할수 있습니다.

```html
<div class="wrapper">
    <button id="btn-1" class="bt no1"type="button" style="color:red;" >HTML 1</button>
    <button id="btn-2" class="bt no2"type="button">HTML 2</button>
</div>
```


### 1.3 태그의 종류
**`Head`** : 제목을 나타낼때 사용합니다. h1부터 숫자가 커질수록 작아집니다.
```html
<h1>Python</h1>
<h6>HTML</h6>
```
**`p`** : 한줄의 문자열을 출력하기 위한 태그입니다.
```html
<span>파이썬은 재미있습니다.</span>
<span>내일은 휴강입니다.</span>
```
**`div`** : 레이아웃을 나타내는 태그이고, 가장 많이 사용됩니다.
```html
<div>
    <p>html 1</p>
    <p>html 2</p>
</div>
<div>
    <p>html 3</p>
</div>
```

**`table`** : row와 column이 있는 테이블 모양을 나타낼때 사용되는 태그입니다.
```html
<table>
    <caption>테이블 제목</caption>
    <thead>
        <tr>
            <th>코드</th>
            <th>회사명</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>0001</td>
            <td>애플</td>
        </tr>
        <tr>
             <td>0002</td>
            <td>네이버</td>
        </tr>
    </tbody>
</table>
```
**`ul`**,**`li`** : 리스트를 나타내는 태그입니다. 하나의 ul에 다수의 li태그를 가집니다.
```html
<ul>
    <li>data 1</li>
    <li>data 2</li>
    <li>data 3</li>
</ul>
```

**`a`** : 링크를 출력하는 태그입니다. `href` 속성값에 이동할 URL을 입력합니다.
```html
<a href="howardhowonyu.github.io" target="_blank">Howard's nest</a>
```

**`img`** : 이미지를 불러오는 태그 입니다. `src` 속성값에 이미지의 URL을 입력합니다.
```html

<img style ="width:200px;"src="이곳에 이미지의 URL을 입력합니다.">
```
**`iframe`** : 외부 URL 링크의 페이지를 보여주기 위한 태그입니다.
```html
<iframe src="https://howardhowonyu.github.io/" width="100%;" height="400px;"></iframe>
```
**`input`** : 여러 형태의 값을 입력받는 요소들을 만드는 태그입니다.
- text : 문자를 입력받습니다.
- password : 비밀번호(****)형태로 입력 받습니다.
- radio : n지 선다의 답을 받습니다.
- checkbox : 체크박스를 만듭니다.
```html
<input type="text"></input>
<input type="password" placeholder="비밀번호"></input>
<input type="radio" name="data">radio 1</input>
<input type="radio" name="data">radio 2</input>
<input type="checkbox">checkbox 1</input>
```

**`select,option`**:  옵션을 선택할수 있는 드랍다운 형태를 만드는  태그입니다.
```html
<select>
<option>data 1</option>
<option>data 2</option>
</select>
```

