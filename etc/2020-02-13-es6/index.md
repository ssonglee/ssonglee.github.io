---
layout: post
title:  "ES6?"
subtitle: "ES5 와 ES6"
type: "Javascript 참조"
etc: true
text: true
order: 5
date: 13 Feb 2020
---

ECMAScript는 자바스크립트 표준 단체인 ECMA가 제정하는 자바스크립트 표준이다. 

<br>

_ECMAScript는 브라우저에서 사용되는 자바스크립트 부분만 표준으로 정의한다._

<br>

현재 우리가 사용하고 있는 자바스크립트는 ES5이며, 이전에는 ES1 ~ ES3까지 존재하고 있다. (ES4는 논쟁요소가 많아 폐기 됨)

<br>

## let과 const

기존에 자바스크립트에서는 <code>var</code>를 이용하여 변수를 선언했다. <br>
다른 프로그래밍 언어는 보통 블럭단위 유효범위를 가지고 있지만, <code>var</code>는 함수에 대해서만 <code>Scope</code>를 가지고 있다.

### scope란?

범위, 영역이란 뜻으로 쉽게 생각하면 _범수의 유효범위_ 이다.<br>
즉, 함수를 경계로 변수의 영역이 나뉘어져있다.<br>
[scope에 대한 내용 참조!](https://web-fron선언t-end.tistory.com/23)

<br>

### let, const 의 장점

ES5에서는 var 키워드를 이용해서 변수를 선언했다.<br>
var로 선언한 변수의 값은 언제나 변경할 수 있어서 변경 불가능한 상수변수를 선언할 방법이 없었다.<br>
그래서 일반 변수와 구분하기 위해 상수값에 대한 명명 규칙을 영문 대문자와 언더스코어만 제한하는 방식을 많이 사용했다고 한다.<br>
또한, 타 언어들과 달리 자바스크립트에서 var로 선언한 변수는 함수 단위의 스코프를 갖기 때문에<br>
if문이나 for문 블록 내에서 var를 선언한 변수들도 블록 외부에서 접근할 수 있다. 
<br>
let , const를 사용해서 얻을 수 있는 이점들을 봐보면 

#### 블록 스코프 지원
let, const로 선언한 변수는 블록스코프를 가진다.<br>
반면에 var로 선언한 변수는 함수 스코프를 가지므로 의도하지 않은 곳에서도 변수변경이 가능하게 되어 에러가 발생할 수 있다.<br>
변수 선언에 let, const를 사용하면 이러한 실수와 오류를 줄일 수 있다.<br>

#### ES5

{% highlight python %}
function sayHello(name) {
  if (!name) {
    var errorMessage = '"name" parameter should be non empty String.';
    
    alert(errorMessage);
  }
  
  console.log('Hello, ' + name + '!');
  console.log(errorMessage); // '"name" parameter should be non empty String.'
}
{% endhighlight %}


{% highlight python %}

{% endhighlight %}

{% highlight python %}

{% endhighlight %}

{% highlight python %}

{% endhighlight %}

{% highlight python %}

{% endhighlight %}

{% highlight python %}

{% endhighlight %}

{% highlight python %}

{% endhighlight %}

{% highlight python %}

{% endhighlight %}

{% highlight python %}

{% endhighlight %}

