---
layout: post
title:  "Javascript return"
subtitle: "악몽의 return"
type: "Javascript"
study: true
text: true
author: "Song LEEE"
order: 5
date: 10 Mar 2019
---

### JAVASCRIPT STUDY

#### 드디어 return 어렵다...

{% highlight python %}
  function inchToCentimeter(inch) {
    var centimeter = inch * 2.54;
    return centimeter;
  }
  var result1 = inchToCentimeter(2);
  var result2 = inchToCentimeter(5);

  console.log(result1 + 'inch');
  console.log(result2);
  console.log(inchToCentimeter(1) + inchToCentimeter(5));

  결과값
  5.08inch
  12.7
  15.23999999
{% endhighlight %}

> return은 한국말로 돌려주다

1. inchToCentimeter 함수가 호출된다.
2. inch 의 값으로 2가 들어가기 때문에 centimeter에는 2*2.54인 5.08이 결과값으로 나온다
3. return centimeter 를 하기 때문에 inchToCentimeter 함수는 5.08을 돌려주게 된다.
4. 함수를 호출한 부분인 inchToCentimeter(2)는 5.08을 돌려받아서 inchToCentimeter(2)가 5.08로 대체 된다고 보면 된다.

<strong> 따라서! result1에는 5.08이 저장된다.</strong>