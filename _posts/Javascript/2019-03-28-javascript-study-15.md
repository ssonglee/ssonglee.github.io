---
layout: post
title: while문 break문 그리고 continue 문
categories: [Javascript]
---
> JAVASCRIPT STUDY

<strong>while문</strong>

{% highlight python %}
var brans = ['Apple', 'Coca-cola', 'Starbucks', 'Amazon', 'Disney', 'BMW'];
for (var i = 0; i < 6; i++){
  console.log(brans[i]);
}
{% endhighlight %}

<br>
<br>

<p>기존 for 문을 이용하여 배열을 나열할때 원리는 i=0 이고 i 가 6보다 작을때까지 반복을 해준다. 그리고 i는 1씩 증가를 하게 된다. 배열 방법이 for 문 말고 다른것도 있다! </p>

<br>

<p class="txt_point">while문</p>

{% highlight python %}
var i = 0;
while (i < 6){
  console.log(brans[i]);
  i++;
}
{% endhighlight %}

<br>

<p>var i = 0 이라는 변수를 만들어 주고 for 문 처럼 i < 6 조건문을 적어준다 그래고 i++ 증가함을 말하면 5일때 까지 반복되어 배열을 나열해준다.</p>

<br>

<p>방식의 차이겠지만 for 문을 할 수 있는건 while 문을 쓸 수 있고 반대로 while 문을 쓸 수 있는건 for 문을 쓸 수 있다.</p>

<strong>break문</strong>

<p>while문의 조건 부분과 상관없이 반복문에서 나오고 싶으면 break문을 쓰면 된다.</p>

<br>

{% highlight python %}
var i = 100;
while(true){
  //i가 23의 배수면 반복문을 끝냄
  if(i % 23 == 0){
    break;
  }
  i++;
}
console.log(i);
{% endhighlight %}

<p class="txt_point">답은? 115</p>

<strong>continue문</strong>

<p>만약 현재 진행되고 있는 수행부분을 중단시키고 바로 조건 부분을 다시 확인하고 싶으면 continue문을 쓰면 된다.</p>

{% highlight python %}
var i = 0;
while (i < 15) {
  i = i + 1;
  // i가 홀수면 console.log(i)에 들어가지 못하고 조건부분으로 돌아감
  if (i % 2 == 1){
    continue;
  }
  console.log(i);
}
{% endhighlight %}

<p class="txt_point">답은? 2 4 6 8 10 12 14</p>