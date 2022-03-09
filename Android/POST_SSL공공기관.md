# 안드로이드 공공도서관 POST로그인

작성시기 22-03-09

> 왜 시도 했을까?<br>
> 공공도서관 열람실 좌석 정보와 '회원정보 바코드'를 보여주는 어플리케이션을 만들고 싶었다.<br>
> '회원정보 바코드'를 보여줄려면 기관 사이트에 로그인을 해야한다.


`HttpURLConnection`을 통해 로그인을 시도 해봤다.

`OutputStream`속에 데이터가 `Null`이기에 왜 그러지가 시작이였다.

이 문제를 알아 보기 위해선 `https`와 **SSL** 을 알아야했다.

![image](https://user-images.githubusercontent.com/101157141/157393354-ddf02fe9-0a01-48f1-a953-e9a5b1d35541.png)

https 는 ssl 프로토콜 위에서 돌아간다고 한다.
