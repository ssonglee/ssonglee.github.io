---
layout: post
title: Javascript switch 문 / for 반복문
categories: [Javascript]
---
> JAVASCRIPT STUDY

<strong>switch문은 간단쓰~</strong>

{% highlight python %}

<script>
  var inputNumber = window.prompt ('한자리 숫자를 적어주세요.');
  switch (inputNumber) {
    case '0':
      alert('Zero!');
      break;
    case '1':
      alert('one');
      break;
    case '7':
      alert('Lucky~');
      break;
    default:
      alert ('Unlucky!');
      break;
  }
</script>

{% endhighlight %}

<p>inputNumber 가 0일 경우 Zero! 1일경우 One! 4일경우 Unlucky!</p>
<p class="txt_point">만약에break가 빠진다면?</p>
<p>다음 케이스로 넘어가서 케이스 0일 경우 Zero 가 나오고 One 이 나오고 Lucky, Unlucky까지 나오게 된다.</p>

{% highlight python %}

var courseName = 'b';
switch (courseName) {
  case = 'c':
    console.log('게살스프 칠리새우');
  case = 'b':
    console.log('유산슬');
  case = 'a':
    console.log('짜장면 짬뽕 탕수육 양장피 팔보채');
    break;
  default:
    console.log('주문이 잘못 되었습니다');
}

{% endhighlight %}
<p>case b 일 경우 결과값 짜장면 짬뽕 탕수육 양장피 팔보채 유산슬</p>

<br>

<br>

<br>

<br>

<strong>for 반복문</strong>

<p>6개의 배열이 있을때?</p> 

```
var brands = ['Apple','Coca-cola','Starbucks','Amazon','BMW'];
```
<p>이렇게 표현할 수 있다. 각 배열들을 호출 시켜주려면 기존 방법은</p>

{% highlight python %}

console.log(brans[0]);
console.log(brans[1]);
console.log(brans[2]);
console.log(brans[3]);
console.log(brans[4]);
console.log(brans[5]);

{% endhighlight %}

<p>100개의 배열이 있다면 100줄의 코드를 사용해야 한다 하지만! for문은 그럴 필요가 없음</p>

```

for (var i = 0; i < 6; i = i + 1 ){
  console.log(brands[i]);
}

```
<p class="txt_point">var i = 0; - 반복문에 사용할 변수 선언</p>
<p class="txt_point">i < 6 - 반복 조건</p>
<p class="txt_point">i = i + 1 - 반복문이 끝나고 실행될 코드</p>
<p class="txt_point">console.log(brands[i]) - 반복시키고 싶은 코드</p>

<br>

{% highlight python %}

  var brands = ['Apple','Coca-cola','Starbucks','Amazon','BMW'];
    for (var i = 0 ; i < 6 ; i = i + 1) {
      console.log(brands[i]);
  }

{% endhighlight %}

<p>하면?</p>

```
Apple Coca-cola Starbucks Amazon BMW

짧은 코드로 같은 결과값을 볼 수 있다!
```








