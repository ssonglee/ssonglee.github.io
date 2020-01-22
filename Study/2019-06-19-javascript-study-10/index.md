---
layout: post
title:  "Javascript Math 정리 노트"
subtitle: "Math 정리 노트"
type: "Javascript"
study: true
text: true
author: "Song LEEE"
---

## 절대값 (Absolute Number)

<p>어떤 값의 양수(Positive Number)버전이라고 할 수 있다. 음수의 -5의 절대값은 양수 5이고<br>양수 5의 절대값은 그래도 양수 5이다.</p>

<p class="txt_point">Math.abs(x)를 하면 x의 값이 리턴된다.</p>

```
console.log(Math.abs(-10); 결과 : 10
console.log(Math.abs(10); 결과 : 10

```

## 최대값 (Maximun)

<p class="txt_point">Math.max 함수에 파라미터로 여러 수를 넘겨주면, 그 중 가장 큰 값이 리턴된다.</p>

```
console.log(Math.max(2,-1,4,5,0)) 결과 : 5
```

## 최소값 (Minimun)

<p class="txt_point">Math.min 함수에 파라미터로 여러수를 넘겨주면 그 중 가장 작은 값이 리턴 된다.</p>

```
console.log(Math.min(2,-1,4,5,0)) 결과 : -1
```

## 제곱근 (Square Root)

<p>'제곱근(Square Root)'은 제곱의 반대라고 생각하면 된다. 5의 제곱이 25이기 때문에 25의 제곱근은 5이다. 7의 제곱은 49이기 때문에 49의 제곱근은 7이다.</p>

<p class="txt_point">Math.sqrt(x)를 하면 x의 제곱근이 리턴된다.</p>

```
console.log(Math.sqrt(25)); 결과 : 5
console.log(Math.sqrt(49)); 결과 : 7
```

## 반올림 (Round)

<p class="txt_point">Math.round(x)를 하면 x의 반올림된 값이 리턴된다.</p>

<p>소수점 부분이 0.5 이상이면 가장 가까운 정수값으로 올라가고, 소수점 부분이 0.5 미만이면 가장 가까운 정수값으로 내려간다.</p>

```

console.log(Math.round(2.3)); 결과 : 2
console.log(Math.round(2.4)); 결과 : 2
console.log(Math.round(2.49)); 결과 : 2
console.log(Math.round(2.5)); 결과 : 3
console.log(Math.round(2.6)); 결과 : 3

```

## 버림과 올림 (Floor and Ceil)

<p class="txt_point">Math.floor(x)을 하면 x의 버림값이 Math.ceil(x)을 하면 x의 올림값이 리턴된다.</p>

<p>이 경우 소수 부분이 얼마인지와는 상관 없다.</p>

```

console.log(Math.floor(2.4)); 결과 : 2
console.log(Math.floor(2.49)); 결과 : 2
console.log(Math.floor(2.8)); 결과 : 2
console.log(Math.ceil(2.4)); 결과 : 3
console.log(Math.ceil(2.49)); 결과 : 3
console.log(Math.ceil(2.8)); 결과 : 3

```

##  난수 (Random)

<p class="txt_point">Math.random을 하면 0이상 1이하의 값이 랜덤으로 리턴된다.</p>

```

console.log(Math.random()); 결과 0.23098542098509
console.log(Math.random()); 여기에 결과값 적는건 사실 의미 없음 
console.log(Math.random());
console.log(Math.random());
console.log(Math.random());

```

<p class="txt_point02">그리고 이 뿐만 아니라 '삼각함수 계산' 이나 '로그' 같은 더 깊은 수학 계산도 가능하다.</p>

[참고사이트!](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Math)







