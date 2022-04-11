[→ Open in Slid](https://slid.cc/docs/db6a9d3a2e3f449caca1d4ea785fb1de)


---

## 미디어쿼리 소개


\- pc뿐만 아니라 모바일과 태블릿에도 대응되는 웹사이트를 만들기 위해


\- 모바일에 대응되는 반응형 또는 적응형 웹사이트를 만들 때 사용되는 CSS 구문

```CSS
.media{
  width: 500px;
  height: 500px;
  background-color: red;
}
@meida (min-width: 320px) and (max-width 800px){
  .media{
  width: 300px;
  height: 300px;
  background-color: yellow;
   }
}
```


min-width와 max-width로


브라우저의 가로폭이 최소 32px 최대 800px에서 media 클래스에 작동

---


반응형 웹 확인 방법 1. 크롬 개발자도구 2. 다음 Troy Labs

## 미디어쿼리 사용시 주의사항

### viweport

```HTML
<meta name="viewport" content="width=device-widthm initial=1.0">
```


미디어쿼리가 제대로 작동하지 않는 문제가 발생할 수 있으므로


viewport로 너비와 배율을 설정해야 모바일 디바이스에서 의도한 화면을 볼 수 있음.


‏‏‎ ‎


다양한 **디지털 기기**의 화면 상에 표시되는 영역을 의미


너비와 배율을 설정할 때 사용하는 메타 태그의 속성 중 하나


‏‏‎ ‎


**.width=device-width** : viewprot의 가로폭 = 디바이스의 가로폭


**.inital-scale=1.0** : 비율은 항상 1.0

---

```CSS
.media{
  width: 500px;
  height: 500px;
  background-color: yellow;
}
@media (min-width: 320px) and (max-width: 800px){
  .media{
    width: 300px;
    height: 300px;
    background-color: none;
  }
}
```


미디어쿼리 외부 영역에 있는 CSS 속성을 상속 받음


만약 상속을 받지 않고자 하면 속성값을 None으로 표시


‏‏‎ ‎
