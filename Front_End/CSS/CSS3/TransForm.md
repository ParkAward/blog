[→ Open in Slid](https://slid.cc/docs/8b68ab78eadb47d3b67e8b0efe697ef2)


---

- Transfrom

- Transition

- Animation


이 세가지는 CSS3 라고 불린다.


‏‏‎ ‎

### TransFrom

- rotate(각도<deg>)\[각도회전\], scale(width, height)\[비율 크기변경\]

```CSS
예시)
.transition{
  transform: rotate(45deg);
  transform: scale(2, 3);
}

.rotate(45deg);
입력한 각도만큼 회전 음수도 입력 가능

.scale(2, 3);
숫자는 비율을 의미
width를 2배, hegiht를 3배 확대
```


‏‏‎ ‎

- skew(X, Y<deg>)\[3차원 각도변경\], translate(X, Y)\[오브젝트 좌표변경\]

```CSS
예시)
.transition{
  transform: skew(10deg, 20deg);
  transform: translate(100px, 200px);
}
.skw(100deg, 20deg);
X축 Y축을 기준으로
입력한 각도만큼 비틂

.translate(100px, 200px);
선택한 오브젝트의 좌표 변경
```


‏‏‎ ‎

- prefix 접두사


\-webkit- 크롬, 사파리


\-moz- 파이어 폭스


\-ms- 익스플로러


\-o- 오페라


모두 적용 = default

## Transition


특정한 조건에 효과주기

- property, duration

```CSS
.transition{
  transition-property: width;
  transition-duration: 2s;
}
.property
효과를 적용하고자 하는 css 속성


.duration
효과가 나타나는데 걸리는 시간
```


‏‏‎ ‎

- timing-function, delay

```CSS
.transition{
  transform-timing-function: linear;
  transition-delay: 1s;
}
.timing-function
효과의 속도
linear은 '일정하게'라는 의미

.delay
특정 조건 하에서 효과 발동
1s '1초 후'라는 의미
```


‏‏‎ ‎

- 가상 선택자 :hover


css에서 미리 만들어 놓은 클래스


'마우스를 올렸을 때'라는 조건

- 종합

```CSS
.transition{
  transition: width 2s linear 1s;
}

마우스를 올리면 '1초 후에'width 값이 300px로, 2초 동안,속도 일정하게

```


transition: \[width\] \[duration\] \[animation type\] \[delay\]


**if** 숫자가 하나일경우 duration을 의미함

# Animation


조건 상관없이 이벤트를 주고 싶을 때

```CSS
.animation{
  animation-name: changeWidth; //임의로 작성
  animation-duration: 3s;
  animation-timing-function: linear;
  animation-delay: 1s;
  animation-iteration-count 6; //애니메이션 반복횟수
  animation-direction: alternate; 진행방향
}
@keyframes changeWidth{
  from{ width: 300px; }
  to { width: 600px;}
}
```

- direction

  - altername: from -> to -> from

  - normal from -> to, from -> to

  - reverse: to -> from, to -> from

### 종합: animation: \[name\] \[duration\] \[timing\] \[delay\] \[count\] \[direction\]


으로 사용할 수 있음.


**@keyframes는 애니메이션 적용에 필수니 꼭꼭 같이 쓰자!**


‏‏‎ ‎

# Transfrom & Animation

```CSS
.box1{
  animation: rotation 1500ms linear infinite alternate;
  //적는 순서는 상관없다. 
  //다만 숫자가 먼저 나타는게 [지속시간] [딜레이] 라는 것.
  //infinite 는 무한 반복
}

@keyframes rotation{
  from { transform: rotate(-10deg);}
  to { transform: rotate(10deg); }
}


```

```CSS
prefix 적용
@-webkit-keyframes rotation{
  from { -webkit-transfrom: rotate(-10deg);}
  to { -webkit-transfrom: rotate(10deg); }
}
만약 prefix를 애니메이션에 적용했을 경우
keyfrmes도 prefix를 적용해야합니다.

없을 경우 없는 것 끼리 적용합니다.
```
