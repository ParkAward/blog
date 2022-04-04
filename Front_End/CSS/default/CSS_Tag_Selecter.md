# Selector 태그 선택 방법
##### A 태그
##### #id 아이디
##### A B A태그 안에 B태그
##### #id A id안에 A태그
##### .className class태그
##### A.className A태그안에 class태그
##### A, B A와 B태그
##### * 전체
##### A *  A태그 안에 
##### A + B A태그 옆에 B태그
##### A ~ B A태그 와 B태그 사이
##### A > B A태그 바로 밑에 B태그
##### :first-child 태그의 첫번째 요소
##### :only-child 태그의 유일한 요소
##### :last-child 태그의 마지막 요소
##### :nth-child(A) 태그의 첫번재로부터 A번째 요소
##### :nth-last-child(A) 태그의 마지막으로부터 A번째 요소
##### :first-of-type
##### :nth-of-type
##### :nth-of-type(A)
##### :nth-of-type(An+B)
##### :only-of-type
##### :last-of-type
##### :empty
##### :not(x)
##### [attribute]
##### A[attribute]
##### [attribute="value"]
##### [attribute^="value"]
##### [attribute&="value"]
##### [attribute*="value"]
`*` 전체 전택

`A + B` A 옆에 B 선택

`A ~ B` A 와 B 사이 선택

`:first-child` 맨 위의 태그 요소 선택

`:only-child` 하나의 요소만 석택

`:last-child` 마지막 태그 요소 선택

`:nth-child(A)` A번째 요소만 선택

`:nth-last-child(A)` A번재 마지막 요소

`:first-of-type` 해당 요소의 첫 번째를 선택

`:nth-of-type(A)` A번째 요소를 선택 
> `odd` 홀수 선택 <br> `even` 짝수 선택 <br> `An + B` 방정식 적용 가능


## 출처
https://flukeout.github.io/
