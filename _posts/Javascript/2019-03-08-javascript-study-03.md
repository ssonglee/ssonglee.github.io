---
layout: post
title: Javascript
categories: [Javascript]
---
> JAVASCRIPT STUDY

```
var text1 = 'Hello';
var text2 = ['H','e','l','l','o'];

위 두개가 다른점은?

console.log(typeof text1) string
console.log(typeof text2) object
```

<strong>mutable(바뀔수있는) vs. immutable(바뀔 수 없는)</strong>

<p>배열은 mutable</p>

```
var text1 = ['H','e','l','l','o'];
text1[0] = 'b';
console.log(text1); ['b','e','l','l','o'];
```

<strong>배열</strong>

```
var brands = ['Apple','Coca-cola','Starbucks'];
```

<strong>배열 속 배열</strong>

```
var products = [
[‘iPhone’,’iMac’,’Macbook’],
[‘Coke’,’Diet Coke’],
[‘Americano’,’Latte’,’Tea’]
];

```

```
Macbook을 출력 하고 싶으면?
console.log(products[0][2]);

Diet Coke를 출력 하고 싶으면?
console.log(products[1][1]);

배열 속에 배열을 변수로 저장 할 수 있다.
var appleProducts = products[0];

```

<strong>객체 Object</strong>

```
var person = ['Donwook','30','Korea'];
console.log(person[2]);
```
<p>배열 출력 방식은 정보가 많으면 많을 수록 호출하기 힘들다(직관적이지 않음)</p>
<p>그래서! 객체방식이 있다</p>

```
var person = {
  name = 'Dongwook',
  age = '30',
  nationality = 'Korea'
}
console.log(typeof person); object

같은 방식 console.log(person['name']);
같은 방식 console.log(person.name);
```

<strong>함수</strong>

{% highlight python %}
  function logTask(task) {
    console.log(task + ':완료');
    congole.log('-');
  }
  logTask('보고서 작성');
  logTask('재고확인');
  logTask('해외주문');
  logTask('담담자파견');
  logTask('영수증발행');
{% endhighlight %}
<p class="txt_point">중복된 코드가 적으면 적을 수록 일이 적다! 그리고 눈에 잘 들어옴</p>

<strong>예제</strong>

```
expressMultiplication(3,4);
expressMultiplication(3,2);
expressMultiplication(7,5);
expressMultiplication(8,9);
expressMultiplication(5,5);
expressMultiplication(9,9);

function expressMultiplication(a,b) {
  console.log(String(a) + '*' + String(b) + '=' String(a*b);
}

```








