---
layout: post
title: Javascript
categories: [Javascript]
---
> JAVASCRIPT STUDY(Syntactic Sugar)

<p>자주 쓰이는 표현을 더 간략하게 쓸 수 있게 해주는 문법(Syntactic - 문법적인 Sugar - 설탕)</p>

<strong>Assignment Operator</strong>

<p>다음 두 줄은 같은 의미이다</p>
```
x=x+1;
x+=1;
```
<p>다음 두 줄은 같은 의미이다</p>
```
x=x+2;
x+=2;
```

<p>다음 두 줄은 같은 의미이다</p>
```
x=x*1;
x*=1;
```

<p>다음 두 줄은 같은 의미이다</p>
```
x=x-3;
x-=3;
```

<p>다음 두 줄은 같은 의미이다</p>
```
x=x/2;
x/=2;
```
<br>

<strong>증가(increment) 감소(decrement)</strong>

<p>다음 세 줄은 같은 의미이다</p>
```
x=x+1;
x+=1;
x++;
```

<p>다음 세 줄은 같은 의미이다</p>
```
x=x-1;
x-=1;
x--;
```
<br>

<strong>예제</strong>

{% highlight python %}
가로길이 var width = 10;
세로길이 var height = 20;
{% endhighlight %}

<p class="txt_point">QA. 둘레의 길이 구하기</p>

{% highlight python %}
var perimeter;
perimeter = 2*(width + height);

console.log('둘레:' + perimeter);
{% endhighlight %}

<p class="txt_point">QA. 넓이 구하기</p>

{% highlight python %}
var area;
area = width * height;

console.log('넓이:' + area);
{% endhighlight %}

<strong>문자열</strong>

<p class="txt_point">주의!</p>

```
var text3='it's cool'; - 오류
var text3="it's cool"; - 통과
```

<br>

<strong>형 변환</strong>

<p class="txt_point">Chrome 개발자 도구에서</p>
```
var favoriteNumber = window.prompt('가장 좋아하는 숫자를 적어주세요');
```
<p>웹 창에 숫자7을 입력하구 개발자 도구에서</p>
```
favoriteNumber; 입력하면 '7'이 나옴
```

```
typeof favoriteNumber; 하면 'number' 라고 숫자형이라고 알려줌
```

<br>

<strong>예제</strong>

```
var material1 = '3';
var material2 = 3;
var material3 = '4';
var material4 = 10;
```
<p>형 변환을 사용해서 result1 에는 문자열 '30'을 result2에는 숫자형 40을 만들어보자</p>

{% highlight python %}
var result1;
result1 = String(material2 * material4);

var result2;
result2 = Number(material3) * material4;    
{% endhighlight %}

<br>

<strong>배열</strong>

```
var brands = ['Apple','Coca-cola','Starbucks'];
var iPad = [800,'Black',true]; - iPad의 가격, 색상, 재고유무를 표현 (java는 배열의 한가지 자료만 넣을 수 있다.)

typeof brands;
'object'

brands[1];
'Coca-cola'

brnads[0];
'Apple
```

<p class="txt_point">배열을 쓸 때는 0번부터! 배열의 각 자리는 index라 설명한다.</p>






