# File Redirection

## Standerd Stream

일반적으로 표준 입력, 표준 출력, 표준 오류 출력으로 분류<br>스트림은 문자열로 콘솔에 출력되도록 설정되어 있음

> stdin : 키보드입력
>
> stdout : 화면출력
>
> stderr : 오류 내용 출력

-----

`>` 연산자는 표준 출력을 재지정

```shell
ls > ls.txt
```

`>>`연산자는 파일이 존재하지 않는다면 파일을 생성,<br>존재한다면 파일내용을 지우지 않고 이어서 작성

```shell
ls >> ls.txt
```

<details>
    <summary> 파일 스크립터 번호</summary>
    <li>0 : 표준 입력</li>
    <li>1 : 표준 출력</li>
    <li>2 : 표준 에러</li>
</details>

```shell
예시) error 2> err.txt
```

----

```shell
cat < hello.txt > text.txt
```

1. hello.txt의 내용을 cat 명령어의 입력 스트림으로 전송
2. cat 명령어는 hello.txt 파일의 내용을 출력
3. cat 명령어의 출력 스트림을 text.txt로 벼녁ㅇ
4. cat 명령어의 출력 스트림은 화면이 아닌 text.txt에 저장