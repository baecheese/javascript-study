# Javascript and Web-Frontend
![](https://s3.ap-northeast-2.amazonaws.com/grepp-cloudfront/programmers_imgs/learn/thumb-course-javascript-webfrontend.jpg)

* [Lecture Page)(https://programmers.co.kr/learn/courses/10)

## 1. HTML, CSS, Javascript
###  HTML, CSS, JS
* HTML : 웹 페이지의 구조
* CSS : 웹 페이지 안에 존재하는 요소들의 스타일
* JS : JS로직을 통해 문서의 구조와 스타일에 변화를 줄 수 있음

### 브라우저에서는 Javascript에서 HTML, CSS에 접근할 수 있는 API를 제공한다.

## 2. Window 객체
* Javascript 실행 시 가장 상위에 존재하는 객체
	* Javascript는 브라우저에서 제공한 window object를 이용해 HTML과 CSS에 접근 및 조작
	* 객체 바인드된 메소드에서 실행한 this가 아닌 경우, this는 window를 가리킴 -> 브라우저에서 자바스크립트 실행 시 가장 상위니까
* 표시된 웹페이지의 정보에 접근하여 변경 가능하다.

### 이용 예시
![](2st-consolImage)
* 크롬 개발자도구 콘솔에서 변수, 메소드를 선언 -> window에 선언한 것
#### window.location
	* 현재 페이지 위치의 정보를 알려준다
``` js
window.location.href = “이동하려는 URL”
```
	* 페이지 이동을 원할 땐 위와 같이 선언해주면 이동 됨
#### window.navigator
* 윈도우 자체의 정보
#### window.screen
* 현재 브라우저 정보
#### window.document
* 현재 브라우저에 적용되어있는 파일 정보 (HTML, CSS..)
##### document.styleSheets
* css에 반영된 것들 정보

## 3. CSS
### 문법
``` css
selector { property_name : value; ... }

/* example */
p {
   color : red;
}
```
	* 선택자를 통해 특정 요소를 선택해서 스타일 적용
	* example
		* p : seletor
		* color : property
		* red : property value

### 적용
1. head 태그 안에 <link> 태그 사용
``` css
 <link rel="stylesheet" href="[css file]">
```
2. head 태그 안에 <style> 태그를 사용해 직접 정의
``` css
 <style>
       ...
 </style>
```
3. html element안에 직접 속성으로 정의
``` css
    <p style="color:red">...</p>
```

### 스타일 적용 우선순위
* 스타일 정의가 충돌하는 경우 브라우저가 우선순위를 통해 스타일 따름
	1. html 안에서 element 태그 내에 정의한 스타일
	2. head에서 스타일 태그에서 정의한 스타일
	3. link를 통해 외부 파일에서 정의된 스타일


## 3. Document Object Model (DOM)
* 컴퓨터가 문서를 잘 처리할 수 있도록 문서 구조를 약속한 것
	* 자바스크립트를 통해 HTML문서에 접근 가능한 이유는 HTML 문서 DOM(Document Object Model)에 따라 기술되고, 이 DOM인터페이스를 통해 기술된 HTML가 객체로서 자바스크립트에 연결
### Tree 
#### 부모 ㅡ 자식 관계의 구조
![](https://i.stack.imgur.com/xw5Hm.png)
	* 위의 그림이라면 a가 parent, b가 children
``` html
<html>
	<head>
	</head>
	<body>
	</body>
</html>
```
	* HTML (parent tag) 
		* html = parent tag
		* head, body = children tag

### Element API
![](document_parent_children)
![](document_children_nextElementSibling)
* document를 통해 접근 가능
	* .children 
	* .parentNode
	* .firstElementChild
	* .lastElementChild
	* .nextElementSibling
	* .previousElementSibling

## 4. Document API
### 문서의 Element를 선택하는 방법
* document.getElementBy~ : 단일 엘리먼트를 선택하는 메소드
	* .getElementByID : 해당하는 id에 대한 태그가 반환
* document.getElementsBy~ : 다중 엘리먼트를 선택하는 메소드
### Element API
![](5st-Document-API/Document-API-getElement-inner)
* .innerHTML
	* element의 html 변경할 수 있음
* .innerText 
	* 	element의 text 변경할 수 있음
* .style
	* css를 변경

#### getAttribute / setAttribute
![](Document-src)
* 이미지 태그에 대해서는 API가 src 프로퍼티 속성을 동기화해주지만, 그 외에 것에서는 동기화해주지 않음
	* 이럴 땐 getAttribute 으로 가져올 수 있음
	* setAttribute로 변경도 가능
#####  예시
![](Document-src-getsetAttribute)


