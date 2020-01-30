---
layout: post
title:  "javascript의 간략한 문법"
subtitle: "자주 쓰이는 표현을 더 간략하게 쓸 수 있게 해주는 문법<br>(Syntactic - 문법적인 Sugar - 설탕)"
type: "Javascript"
study: true
text: true
author: "Song LEEE"
order: 3
date: 07 Mar 2019
---

# Assignment Operator
<p>다음 두 줄은 같은 의미이다</p>
```
x=x+1;
x+=1;
```
<br>

<p>다음 두 줄은 같은 의미이다</p>
```
x=x+2;
x+=2;
```
<br>

<p>다음 두 줄은 같은 의미이다</p>
```
x=x*1;
x*=1;
```
<br>

<p>다음 두 줄은 같은 의미이다</p>
```
x=x-3;
x-=3;
```
<br>

<p>다음 두 줄은 같은 의미이다</p>
```
x=x/2;
x/=2;
```
<br>

## 증가(increment) 감소(decrement)

<p>다음 세 줄은 같은 의미이다</p>
```
x=x+1;
x+=1;
x++;
```
<br>

<p>다음 세 줄은 같은 의미이다</p>
```
x=x-1;
x-=1;
x--;
```
<br>

## 예제

```
가로길이 var width = 10;
세로길이 var height = 20;
```

### QA. 둘레의 길이 구하기

```
var perimeter;
perimeter = 2*(width + height);

console.log('둘레:' + perimeter);
```

### QA. 넓이 구하기

```
var area;
area = width * height;

console.log('넓이:' + area);
```

## 문자열

<p>주의! <code>""</code> 에 주의하자!</p>

```
var text3='it's cool'; - 오류
var text3="it's cool"; - 통과
```

<br>

## 형 변환

<p>Chrome 개발자 도구에서</p>
```
var favoriteNumber = window.prompt('가장 좋아하는 숫자를 적어주세요');
```
<br>
<p>웹 창에 숫자7을 입력하고 개발자 도구에서</p>
```
favoriteNumber; 입력하면 '7'이 나옴
```

```
typeof favoriteNumber; 하면 'number' 라고 숫자형이라고 알려준다
```

<br>

### 예제

```
var material1 = '3';
var material2 = 3;
var material3 = '4';
var material4 = 10;
```
<p>형 변환을 사용해서 result1 에는 문자열 '30'을 result2에는 숫자형 40을 만들어보자</p>


```
var result1;
result1 = String(material2 * material4);

var result2;
result2 = Number(material3) * material4;    

```

<br>

## 배열

```
var brands = ['Apple','Coca-cola','Starbucks'];
var iPad = [800,'Black',true]; - iPad의 가격, 색상, 재고유무를 표현 
(java는 배열의 한가지 자료만 넣을 수 있다.)

typeof brands;
'object'

brands[1];
'Coca-cola'

brnads[0];
'Apple
```

### 배열을 쓸 때는 0번부터! 배열의 각 자리는 index라 설명한다.