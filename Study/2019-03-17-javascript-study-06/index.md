---
layout: post
title:  "악몽의 삼각형 만들기"
subtitle: "그동안의 지식으로!"
type: "Javascript"
study: true
text: true
author: "Song LEEE"
---

## 힘들었다 

{% highlight python %}

  function printTriangle(height){
    for (var i = 0; i < height; i = i + 1){
      console.log('*');
    }
  } 

  console.log('높이:5');
  printTriangle(5);
  console.log('높이:3');
  printTriangle(3);
  console.log('높이:1');
  printTriangle(1);

{% endhighlight %}

<p class="txt_point">var i = 0 반복문에 사용할 변수 선언</p>
<p class="txt_point">i < height 반복문 조건</p>
<p class="txt_point">i = i + 1</p>

<p>이렇게 실행하면??</p>

![결과값](https://user-images.githubusercontent.com/43769441/59655855-bb205d00-91d6-11e9-90d1-92f7e4aabc8b.png)

<p class="txt_point02">높이에 맞춘 printTriangle이 호출된다. 높이에 맞춘 *을 가로로 늘려보자~</p>

{% highlight python %}

function printTriangle(height) {
  star = '*';
  for(var i = 0 ; i < height; i = i + 1) {
    star = star + '*';
    console.log(star);
  }
}

console.log('높이:5');
  printTriangle(5);
  console.log('높이:3');
  printTriangle(3);
  console.log('높이:1');
  printTriangle(1);

{% endhighlight %}

![결과값](https://user-images.githubusercontent.com/43769441/59656199-c88a1700-91d7-11e9-9b96-e79a1a2c9b42.png)

<p>star='*'; star 라는 변수를 만들어서 문자열 *을 넣어주고</p>
<p>for 반복문안에 star = star + '*';를 넣어서 추가가 되도록 한다!</p>

<br>

<p class="txt_point">for 반복문을 이용해서 머리쓰는거 넘나 어려운것..ㅠㅠ </p>

<br>

<p class="txt_point">star = '*'에서 * 값을 뺀 상태로 실행 하면 별 한개씩 줄인 삼각형을 볼 수 있당... </p>

