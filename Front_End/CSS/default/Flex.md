[TOC]



# Flex

`Flexible Box`, `Flexbox`

레이아웃 배치 전용 기능으로 고안되었습니다. 그래서 레이아웃을 만들 때 딱히 사용할게 없어서 쓰던 float이나 inline-block등을 이용한 기존 방식보다 훨씬 강력하고 편리한 기능들이 많아요.

## Flex Container

### display

```css
.cotainer {
    display:flex;
    /*display:inline-flex;*/
}
```

##### `flex` : 전체 컨테이너

##### `inline - flex` : 아이템 크기 만큼

## 배치 방향 설정 `flex-direction`



```css
.container{
    flex-direction: row; (기본값) 아이템들이 행(가로)방향
    flex-direction: column; 아이템들이 열(세로) 방향
    flex-direction: row-reverse; 역순
    flex-direction: column-reverse; 역순
    
}
```



## 줄넘김 처리 설정 `flex-wrap`

```css
.container{
    flex-wrap: nowrap; (기본값) 아이템 줄바꿈 X
    flex-wrap: wrap;  줄바꿈!
    flex-wrap: wrap-reverse; 줄바꿈이긴 한데.. 반대로
}
```



### `flex-flow`

두가지 옵션을`flex-flow: row wrap;` 으로 줄여서 작성할 수 있다.

## 메인축 방향 정렬 `jstify-content`

```css
.container{
    justify-content: flex-start; (기본값) 아이템 시작점 정렬
    justify-content: flex-end; 아이템 끝점 정렬
    justify-content: center; 아이템 중앙 정렬
    justify-content: space-between; 아이템 `사이` 균일 하게
    justify-content: space-around; 아이템 "둘레"에 균일한 간격
    justify-content: space-evenly; 아이템 사이와 양끝에 균일한 간격(IE X Edge X)
}
```



## 수직축 방향 정렬 `algin-items`

```css
.container{
    align-items: stretch; (기본값) 아이템 수직축 방향 끝까지 쭈욱 늘어남
    align-items: flex-start; 아이템들의 시작점 정렬
    align-items: flex-end; 아이템들의 끝점 정렬
    align-items: center; 아이템들을 중앙 정렬
    align-items: baseline; 아이템 text 베이스라인 기준 정렬
    
    
}
```

## 여러 행 정렬 `align-content`

```css
.container{
    flex-wrap: wrap;행 2줄 이상 수직축
    align-content: stretch; (기본값) 아이템 끝까지 늘이기
    align-content: flex-start; 아이템 시작점 정렬
    align-content: flex-end;  아이템 끝점 정렬
    align-content: space-between; 아이템 사이 균일 하게
    align-content: space-around; 아이템 둘레 균일 하게
    align-content: space-evenly; (IE X Edge X)
}
```



# Flex items Attr

## 유연한 박스의 기본 영역 `flex-basis`

```css
.item{
    flex-basis: auto; 기본값
    flex-basis: 0;; 
    flex-basis: 50%;; 
    flex-basis: 300px; 
    flex-basis: 10rem; 
    flex-basis: content; 
    
}
```

Flex 아이템의 기본 크기를 설정합니다.



## 유연하게 늘리기 `flex-grow`

```css
.itmel{
    flex-grow: 1;
    flex-grow: 1; 기본값
}
예시)
/* 1:2:1의 비율로 세팅할 경우 */
.item:nth-child(1) { flex-grow: 1; }
.item:nth-child(2) { flex-grow: 2; }
.item:nth-child(3) { flex-grow: 1; }
```

**아이템 여백을 기준**으로 비율을 줘서 크기를 늘립니다.

## 유연하게 줄이기 `flex-shrink`

### felx  `flex-grow`, `flex-shrink`, `flex-basis`

```css
.item {
	flex: 1;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 0%; */
	flex: 1 1 auto;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: auto; */
	flex: 1 500px;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 500px; */
}
```

## 수직축으로 아이템 정렬 `align-self`

## 배치순서 `order`

## Z-index