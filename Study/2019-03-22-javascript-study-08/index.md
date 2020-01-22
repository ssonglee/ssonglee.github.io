---
layout: post
title:  "공포의 2등 찾기 문제"
subtitle: "for문 응용 시작!"
type: "Javascript"
study: true
text: true
author: "Song LEEE"
---

## for 문 너무 어려워요ㅠ^ㅠ

<br>

<p class="txt_point02">파라미터로 배열 arr을 받고, arr에서 두번째로 큰 숫자를 리턴시켜주는 함수를 작성해보자</p>

{% highlight python %}

function getSecondBiggestNumber(arr) {

}

console.log(getSecondBiggestNumber([4,7,2,1,9,3,6,5]));
console.log(getSecondBiggestNumber([80,2,44,21,92,3,51]));
console.log(getSecondBiggestNumber([4,7,6,5]));

{% endhighlight %}

<p>해보소</p>

<p class="txt_point02">type1</p>

{% highlight python %}

function getSecondBiggestNumber(arr) {
  var firstNum = 0;
  var SecondNum = 0;
  for (var i = 0; i < arr; i++){
    if(secondNum < firstNum && seconNum < arr[i]){
      secondNum = arr[i]
    }
    if(first < arr[i]){
      secondNum = firstNum ;
      firstNum = arr[i];
    }
  }
  return secondNum;
}

console.log(getSecondBiggestNumber([4,7,2,1,9,3,6,5]));
console.log(getSecondBiggestNumber([80,2,44,21,92,3,51]));
console.log(getSecondBiggestNumber([4,7,6,5]));

{% endhighlight %}

<p class="txt_point02">type2</p>

{% highlight python %}

function getSecondBiggestNumber(arr) {
  var first = arr[0];
  var second = arr[0];
  for (var i = 1; i < arr.length; i++ ){
    if (arr[i] >= first ){
      second = first;
      first = arr[i];
    }else if (arr[i] > second){
      second=arr[i];
    }
  }
  return second;
}

console.log(getSecondBiggestNumber([4,7,2,1,9,3,6,5]));
console.log(getSecondBiggestNumber([80,2,44,21,92,3,51]));
console.log(getSecondBiggestNumber([4,7,6,5]));

{% endhighlight %}

1. 1등과 2등에 해당하는 변수를 만들어 준다.
2. 입력된 arr의 두번째 숫자부터 마지막 숫자까지 반복해준다.
3. 그 안에서 1등과 2등을 매번 업데이트 해준다. 즉 arr[i]가 1등보다 크거나 같은 경우,<br>
1등과 2등을 함께 업데이트 해준다. arr[1]가 1등보다는 작지만 2등보다는 클 경우에는 2등만 업데이트 해준다.
4. 마지막으로 리턴~

<p class="txt_point">???</p>





