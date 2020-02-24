# CSS Selector
HTML 엘리먼트에 CSS 스타일을 적용시킬때 엘리먼트를 선택하기 위한 입니다.
<!-- more -->

#### 1. 태그 이름으로 선택
"data 1 엘리먼트를 선택"
- css-selector : `div`



#### 2. 아이디 값으로 선택
"data 2를 아이디 값으로 선택"
- css-selector : `#text`

#### 3.클래스 값으로 선택
"data 3를 클래스 값으로 선택"
- css-selector : `.no1`
- `.dss-txt` : data2, data 3가 선택 

#### 4. 속성값으로 선택
"data 4를 속성값으로 선택"
- css-selector : `[val="d4"]`, `[id="da4"]`

#### 5. 혼합해서 사용
"span 태그, class 값이 no5인 엘리먼트 선택"
- css-selector : `span.no5`

```html
<div id="wrap">data 1</div>
<p id="text" class="dss-txt no1">data 2</p>
<span class="dss-txt no2" val="d3">data 3</span>
<span id="da4" val="d4">data 4</span>
<span class="no5" >data 5</span>
```

#### 6. not selector
선택된 엘리먼트에서 특정 조건의 엘리먼트를 제거해서 선택
data 2 엘리먼트만 제외한 ds 클래스를 선택
- css-selector : `.ds:not(.dss2)`


#### 7.nth-child 
n번째의 엘리먼트를 선택

data 3 선택하는 방법
- css-selector : `.ds:nth-child(3)` 
뒤의 조건(.ds라는 클래스를 가진 상위 클래스의 자식중에 3번째)이 먼저, 다음 ds라는 클래스를 가진거를 선택

```html
<div>
    <span>data 0</span>
    <p class="ds dss1">data 1</p>
    <p class="ds dss2">data 2</p> # 얘도 3번째 ds
    <p class="ds dss3">data 3</p>
    <p class="ds dss4">data 4</p>
    <div class="wrap">
        <p class="ds dss1">data 1</p>
        <p class="ds dss2">data 2</p>
        <p class="ds dss3">data 3</p> # 얘도 3번째 ds
        <p class="ds dss4">data 4</p>
    </div>
</div>
<div></div>
<div class="ds"> data5</div> # 얘도 3번째 ds
```

#### 8. 계층구조로 엘리먼트 선택
바로 아래 단계의 엘리먼트 선택
- `.wrap-1 > h5` : inner 1선택
모든 하위 엘리먼트를 선택
- `.wrap-1 h5` : inner 1,inner 2선택
```html
<div class="wrap-1">
    <h5>inner 1 </h5>
    <div class="wrap-2">
        <h5>inner 2 </h5>
    </div>
</div>
```
