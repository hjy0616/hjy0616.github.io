---
layout: post
title: javascript 기초
description: >
    javascript 기초 (기존 개발자들이 빠르게 보고 사용할 수 있을 정도만 만들어놓음)
sitemap: false
hide_last_modified: false
categories:
  - study
  - languages
---

# javascript
- javascript는 웹 프론트 엔드 (Front-End) 언어
- HTML 문서에 내장
- 스크립트 언어
- 문장과 문장을 구분하기 위해 세미콜론 ; 사용

* toc
{:toc .large-only}

## 작성 시
~~~
<script> </script> 태그 안에 작성
~~~

### 예
~~~html
<h1>JavaScript</h1>
<script>
  document.write(1+1); //웹페이지 출력시 사용
</script>
<h1>html</h1>
1+1
~~~

## 이벤트
- input태그를 통해 type을 지정가능 value에 안에있는 내용 작성이 가능
- alert을 통해 경고창 이벤트 발생
- 각 속성은 속성에 맞게 이벤트 발생
* [참고 URL](https://www.w3schools.com/tags/ev_onkeydown.asp)
~~~
<input type="button" value="hi" onclick="alert('hi')">
<input type="text" onchange="alert('changed')">
<input type="text" onkeydown="alert('key down!')">
~~~

## 변수
- var 키워드로 선언하는 방법과 var 없이 선언이 가능
- 자바스크립트에는 변수 타입이 없다.
- //, /**/은 주석

~~~javascript
/////var 키워드 선언
var test;
var test1 = 112;

////var 없이 선언
hi = "hi";
~~~

## 식별자
- 첫번째 문자는 알파벳(A-Z,a-z), 언더스코어(_), &문자만 가능
- 두번째 이상 문자는 알파벳, 언더스코어(_), 0-9, $사용 가능
- 대소문자는 구분되어 다루어진다.
- hi와 Hi는 다른 식별자

## 지역변수, 전역변수

- 지역변수 : 함수 내에 var 키워드 선언, 선언된 함수 내에서만 사용
- 전역변수 : 함수 밖에 선언되거나 함수 내에 var 키워드 없이 선언, 프로그램 전역에서 사용

~~~javascript
var x; //지역변수
function g() {
  var y; //지역변수 y선언
  x = 100; //전역 변수
}
~~~

### this 키워드로 전역변수 접근가능

~~~javascript
var y; // 전역변수
function x() {
var u; // 지역변수
i = 1; // 지역변수
this.y = 100; // 전역변수 y에 100저장
}
~~~

## 연산자
| 연산 종류 | 연산자 |
| ------ | -------- |
| 산술 | + - * / % |
| 증감 | ++ --|
| 비트 | & ^ ~ ...|
| 시프트 | >> << >>> |
| 대입 | = *= /= += -= &= ^= ... |
| 비교 | > < >= <= == !=|
|논리 | && ! ...|
| 조건 | ? : |

### 산술 연산자
- 기본으로 알고있는 + - * / %
- /가 나누기 %가 나머지다
- 연산의 결과는 항상 실수로 나온다.

~~~javascript
var x = 100;
var y = 100 + x*2/4 - 3;
var z = x / 10;
var total = x % 2;
document.write("x : " + x + "<br><br>");
document.write("100 + x*2/4 - 3 = " + y + "<br>");
document.write("x/10 = " + z + "<br>");
document.write("x%2 = " + total + "<br>");
~~~

### 증감 연산자
- 전위 연산자와 후위 연산자가 있다.

| 연산자 | 내용 |
| ----- | ----|
| a++ | 1증가 후 증가 전의 값을 반환|
| a -- |1감소 후 감소 전의 값을 반환|
| ++a | 1증가 후 증가한 값을 반환|
| --a | 1감소 후 감소된 값 반환 |

### 대입연산자
- 오른쪽의 결과를 왼쪽 변수에 대입

| 연산자 | 내용 |
| ----- | ---- |
| a = b | b값을 a에 대입|
| a += b | a = a + b |
| a -= b | a= a -b |
| a *= b | a = a * b |
| a /= b | a = a / b |
| a %= b | a = a % b |
| a &= b | a = a & b |
| a ^= b | a = a ^ b |
| a <<= b | a = a << b |
| a >>= b | a = a >> b |
| a >>>= b | a = a >>> b |

### 비교 연산자
- 두 값을 비교 후 true 혹은 false의 결과를 출력해주는 연산

| 연산자 종류|
| ----- |
| a < b |
| a > b |
| a <= b |
| a >= b |
| a == b |
| a != b |

### 논리 연산자
- 기본으로 알고 있는 논리연산이다.
- 연산자 종류로는 And &&, or ||, Not !


### 조건 연산자

~~~javascript
var x=10 , y=8;
var total = (x>y) ? x : y; //x > y가 true라면 x 값 10가 total에 대입
// false라면 8 대입
~~~


## 조건문
- if, switch, while, for 등에 사용된다.

### if
- ~ 라면 출력값 형태

~~~javascript
var x;
var y = prompt("점수를 입력하세요", 100);
y = parseInt(y); // 문자열을 숫자로 바꿈
if(y >= 90) // score가 90 이상
x = "A";
else if(y >= 80) // 80 이상 90 미만
x = "B";
else if(y >= 70) // 70 이상 80 미만
x = "C";
else if(y >= 60) // 60 이상 70 미만
x = "D";
else // 60 미만
x = "F";
~~~

### switch
- 값에 따라서 서로 다른 코드를 실행해줄때 Switch문을 사용
- break를 사용하면 break문을 만날때까지 코드 실행

~~~javascript
var day="월";
switch(day) {
case "월":
case "화":
case "수":
case "목":
case "금": document.write("정상영업");
break;
case "토":
case "일": document.write("휴일");
break;
}
~~~

## 함수(function)
- 하나의 특별한 목적의 작업을 수행하도록 설계된 독립적인 블록
- 필요할때마다 호출해서 사용 가능

~~~javascript
function addNum(x, y) {
    return x + y;
}
document.write(addNum(2, 3));
~~~


## 객체
- 객체는 자신만의 고유한 구성
- ex) 음료수: {이름: 환타, 색: 주황색, 탄산 유무: 유}
- 객체 구성으로는 여러개의 프로퍼티(property)와 메소드로 구성
  - 프로퍼티 : 객체의 고유한 속성(변수)
  - 메소드(method) : 함수

### 객체의 종류
- 객체의 유형
+ 코어 객체
  + 자바스크립트 언어가 실행되는 어디서나 사용 가능
  + 표준 객체
  + Array, Date, String, Math 타입 등
  + 웹페이지 자바스크립트 코드에서 or 서버에서 사용가능
+ HTML DOM 객체
  - 각 HTML 태그들을 객체화 한것
  - 문서의 내용과 모양을 제어하기 위한 목적
  - W3C의 표준 객체
+ 브라우저 객체
  - 자바스크립트로 브라우저를 제어하기 위해 사용하는 객체
  - 비표준 객체
  + 객체 접근을 위해 .(점) 연산자 이용

~~~
test.property = value; //이런식
~~~

## 배열
- 여러개의 원소들을 연속적으로 저장
- 전체를 하나의 단위로 다루는 데이터 구조

~~~javascript
var test = ["hi", "test", "test1"];
var name = test[0]; //name에 test배열 0번째 자리 들어감
test[1] = "test2"; //test자리에 test2 저장
~~~

### 배열만들기
- 배열 만드는 종류는 2가지다
  - []로 배열 만들기
  - Array 객체로 배열만들기
- 배열의 크기는 고정되지 않고 추가 시 늘어난다

~~~javascript
var test = new Array("a", "b", "c", "d");
~~~
