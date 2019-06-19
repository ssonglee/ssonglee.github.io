---
layout: post
title: Javascript for of 반복문
categories: [Javascript]
---
> JAVASCRIPT STUDY

<strong>for of 문과 for in 문 </strong>

{% highlight python %}

var brands = ['NIKE','adidas','Reebok'];
for(var i = 0; i < 3; i++){
  console.log(brands[i]);
}

{% endhighlight %}

<p>기존의 배웠던 for 반복문은.<br> 변수 i 가 할 필요한건 0,1,2 번의 인덱스 값을 불러오는 역할을 할 뿐 하는게 없어서!</p>

{% highlight python %}

var brands = ['NIKE','adidas','Reebok'];
for(value of brands){
  console.log(value);
}

{% endhighlight %}

<p>이렇게 for of 반복문을 이용할 수 있다. value는 어떤 단어든 사용할 수 있음</p>
<p>기존의 for문 보다 좋은게 조건을 쓰지 않아도 되고, 불필요한 변수 i를 안써도 된다.</p>
<p>어떤 방식이 좋을진 알아서 판단하여 쓰소~~</p>

<br>
<br>

<strong>for...in문과 for...of문의 차이</strong>

{% highlight python %}

var arr = ['Americano','Latte','Tea'];

for(var v of arr){
  console.log(v);
}

for(var k in arr) {
  console.log(k);
}

{% endhighlight %}

<p>하면?</p>

![결과값](https://user-images.githubusercontent.com/43769441/59664452-0b55ea00-91ec-11e9-9097-12cd64543faa.png)

<p>확인할 수 있다.</p>

<p>차이는?</p>

<p>배열은 여러개의 index-value 쌍으로 이루어졌다고 볼 수 있는데,<br> 위 코드의 arr 배열의
경우에는 index 0,1,2 고 value는 'Americano' 'Latte' 'Tea' 라고 볼 수 있다.<br>
출력된 결과를 보면 알 수 있듯 for of 문은 배열의 value에 직접 접근하는 반면 for in 문은 index에 접근한다
</p>

<p>그래서!</p>
<p class="txt_point">for in 문으로 value에 접근하기 위해선</p>

```
for(var k in arr){
  console.log(arr[k]);
}
```

<p>접근하면 된다 끝!</p>


