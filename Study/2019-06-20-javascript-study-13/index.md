---
layout: post
title:  "Javascript Array 정리"
subtitle: "배열이란!"
type: "Javascirpt"
study: true
text: true
author: "Song LEEE"
---

## 배열의 길이

<p class="txt_point">length 속성은 배열의 길이를 담고 있다.</p>

{% highlight python %}
var brands = ['Apple','Coca-cola','Starbucks'];
  console.log(brands.length);
{% endhighlight %}

```
결과 : 3
```

<br>
<br>
<br>

## 배열에서 특정 값 찾기

<p class="txt_point">문자열에 썼던 indexOf가 배열에서도 똑같이 동작한다.array.indexOf(item)을 하면<br>array배열에 item이 포함되어 있는지 확인할 수 있다.</p>

1. 만약 포함되어 있다면 item이 있는 인덱스가 리턴된다.
2. 포함되어 있지 않다면 -1이 리턴된다.
3. 여러 번 포함되어 있으면 처음 발견된 인덱스가 리턴된다.

{% highlight python %}
var brands = ['Apple','Coca-cola','Starbucks'];
console.log(brands.indexOf('Starbucks'));
console.log(brands.indexOf('Kakao'));
{% endhighlight %}

```
결과 : 2
결과 : -1
```

<br>
<br>
<br>

## 배열에 값 추가

<p class="txt_point">array.push(item1)을 하면 item1이 array 배열의 끝에 추가된다.</p>
<p class="txt_point">array.push(item1,item2,item3)을 하면 item1, item2, item3이 array 배열의 끝에 순서대로 추가된다.</p>

{% highlight python %}
var brands = ['Apple','Coca-cola','Starbucks'];

brands.push('kakao');
console.log(brands);

brands.push('Samsung','LG','Facebook');
console.log(brands);
{% endhighlight %}

```
결과 : ['Apple','Coca-cola','Starbucks','Kakao']
결과 : ['Apple','Coca-cola','Starbucks','Samsung','LG','Facebook']
```

<br>
<br>
<br>

## 배열에서 값 빼기

<p class="txt_point">array.pop()을 하면 배열 array의 마지막 요소가 배열에서 빠지고, 그 마지막 요소가 리턴된다.</p>

{% highlight python %}
var brands = ['Apple','Coca-cola','Starbucks'];

var lastBrand = brands.pop();

console.log(lastBrand);
console.log(Brand);
{% endhighlight %}

```
결과 : Starbucks
결과 : ['Apple','Coca-cola']
```

<br>
<br>
<br>

## 배열을 문자열로 바꾸기

<p class="txt_point">그리고 여기서 brands.join()이라고 한번 해보면 모든 내용이 하나로 합쳐진다! 와우</p>

{% highlight python %}
var brands = ['Apple','Coca-cola','Starbucks'];
console.log(brands.join());
{% endhighlight %}

```
결과 : Apple,Coca-cola,Starbucks
```

<br>
<br>
<br>

그리고? 더 많은 정보를 알고 싶다면 [참고!](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array)



