# Selector 태그 선택 방법
##### A | 태그
##### #id | 아이디
##### A B | A태그 안에 B태그
##### #id | A id안에 A태그
##### .className | class태그
##### A.className | A태그안에 class태그
##### A, B | A와 B태그
##### * | 전체
##### A * |  A태그 안에 
##### A + B | A태그 옆에 B태그
##### A ~ B | A태그 와 B태그 사이
##### A > B | A태그 바로 밑에 B태그
##### :first-child | 태그의 첫번째 요소
##### :only-child | 태그의 유일한 요소
##### :last-child | 태그의 마지막 요소
##### :nth-child(A) | 태그의 첫번재로부터 A번째 요소
##### :nth-last-child(A) | 태그의 마지막으로부터 A번째 요소
##### :first-of-type | 해당 태그의 첫번째 자식 선택
##### :nth-of-type(An+B )
> `odd` 홀수 선택 <br> `even` 짝수 선택 <br> `An + B` 방정식 적용 가능
##### :only-of-type | 오직 하나의 자식을 가진 태그를 선택
##### :last-of-type | 태그의 마지막 자식태그를 선택
##### :empty | 태그가 비었을 때
##### :not(x) | x를 제외한
##### [attribute] | 속성 선택
##### A[attribute] | A태그의 특정 속성이 포함된 태그
##### [attribute="value"] | A태크 > 특정 속성 > 특정 값 을 선택
```css
/* <a> elements with a title attribute */
a[title] {
  color: purple;
}

/* <a> elements with an href matching "https://example.org" */
a[href="https://example.org"] {
  color: green;
}

/* <a> elements with an href containing "example" */
a[href*="example"] {
  font-size: 2em;
}

/* <a> elements with an href ending ".org" */
a[href$=".org"] {
  font-style: italic;
}

/* <a> elements whose class attribute contains the word "logo" */
a[class~="logo"] {
  padding: 2px;
}
```
#### 구문
<pre>
[attr]
attr이라는 이름의 특성을 가진 요소를 선택합니다.
[attr=value]
attr이라는 이름의 특성값이 정확히 value인 요소를 선택합니다.
[attr~=value]
attr이라는 이름의 특성값이 정확히 value인 요소를 선택합니다. attr 특성은 공백으로 구분한 여러 개의 값을 가지고 있을 수 있습니다.
[attr|=value]
attr이라는 특성값을 가지고 있으며, 그 특성값이 정확히 value이거나 value로 시작하면서 -(U+002D) 문자가 곧바로 뒤에 따라 붙으면 이 요소를 선택합니다. 보통 언어 서브코드(en-US, ko-KR 등)가 일치하는지 확인할 때 사용합니다.
[attr^=value]
attr이라는 특성값을 가지고 있으며, 접두사로 value가 값에 포함되어 있으면 이 요소를 선택합니다.
[attr$=value]
attr이라는 특성값을 가지고 있으며, 접미사로 value가 값에 포함되어 있으면 이 요소를 선택합니다.
[attr*=value]
attr이라는 특성값을 가지고 있으며, 값 안에 value라는 문자열이 적어도 하나 이상 존재한다면 이 요소를 선택합니다.
[attr operator value i]
괄호를 닫기 전에 i 혹은 I를 붙여주면 값의 대소문자를 구분하지 않습니다. (ASCII 범위 내에 존재하는 문자에 한해서 적용됩니다)
[attr operator value s] 
괄호를 닫기 전에 s 혹은 S를 붙여주면 값의 대소문자를 구분합니다. (ASCII 범위 내에 존재하는 문자에 한해서 적용됩니다)
</pre>

## 출처
https://flukeout.github.io/<br>
https://developer.mozilla.org/ko/docs/Web/CSS/Attribute_selectors
