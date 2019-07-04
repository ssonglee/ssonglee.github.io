---
layout: post
title: Javascript Data 정리 
categories: [Javascript]
---
> JAVASCRIPT STUDY

<p class="txt_point02">날짜와 관련된 프로그램을 짜고 싶다면? Date 객체를 활용 하면 됩니다!</p>

<h2>객체 만들기</h2>

<p>객체를 만들어야 활용 할 수 있는데, 두가지 방법이 있다.</p>

<strong>현재 날짜로 설정</strong>

<p class="txt_point">파라미터 없이 new Date()를 하면 현재 날짜로 설정되어 있는 Date 객체가 생성되어 리턴된다.</p>

{% highlight python %}
var date = new Date();
{% endhighlight %}

<br>
<br>

<strong>원하는 날짜로 설정 </strong>

<p class="txt_point">파라미터를 써주면 원하는 날짜로 설정할 수도 있다. 만약 날씨만 쓸 경우, 0시 0분 0초로 지정된다.</p>

{% highlight python %}
// 1988년 6월 11일 5시 25분 30초
var date1 = new Date('June 11, 1988 05:25:30');
var date2 = new Date('1988-06-11T05:25:30');

// 1988년 12월 15일 (날짜만)
var date3 = new Date('1999-12-15');
var date4 = new Date('12/15/1999');
var date5 = new Date('December 15 1999');
var date6 = new Date('Dec 15 1999');
{% endhighlight %}

<br>
<br>

<strong>날짜 정보 받아오기</strong>

<p class="txt_point">이제 Date 객체의 메소드들을 활용하면 되는데 이러한 기능들이 있다!</p>

{% highlight python %}
var date = new Date('June 11, 1988 05:25:30');

console.log(date.getFullYear());
console.log(date.getMonth());
console.log(date.getDate());
console.log(date.getDay());
console.log(date.getHours());
console.log(date.getMinutes());
console.log(date.getMilliseconds());
console.log(date.toString());
console.log(date.toLocaleString());
console.log(date.toLocaleDateString());
console.log(date.toLocaleTimeString());
{% endhighlight %}

<br>
<br>

```
1988
5
11
6
5
25
30
0
Sat Jun 11 1988 05:25:30 GMT+1000 (KDT)
6/11/1988, 5:25:30 AM
6/11/1988
5:25:30 AM
```

<br>
<br>

<p class="txt_point02">getTime() 메서드는 1970년 1월 1일 자정으로부터 몇 ms가 지났는지 알려준다</p>

{% highlight python %}
var date = new Date('June 11, 1988 05:25:30');
console.log(date.getTime());
{% endhighlight %}

<br>
<br>

```
581973930000
```

<br>
<br>

<p class="txt_point02">이 ms값에 나눗셈을 적절히 사용하면 초,분,시,일 등의 단위로 변환할 수 있다.</p>

{% highlight python %}
var date = new Date('June 11, 1988 05:25:30');
console.log(date.getTime() + 'ms');
console.log(date.getTime()/1000 + '초');
console.log(date.getTime()/1000/60 + '분');
console.log(date.getTime()/1000/60/60 + '시간');
{% endhighlight %}

<br>
<br>

```
581973930000ms
581973930초
9699565.5분
161659.425시간
```

<p  class="txt_point">주의할 점!</p>

<p class="txt_point02">getMonth()경우, 0 부터 시작하기 때문에 2는 3월을 의미한다. <br> 또한 getDay()는 날짜가 아니라 요일을 리턴해주고, 일요일인 0부터 시작해서 3은 수요일을 뜻한다.</p>

<br>

<strong>그리고~</strong>

[참고!](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Date/prototype)




