---
layout: post
title: "Javascript for 문 vs while 문"
type: "Javascript"
subtilte : "차이점 찾아보기"
categories: [Javascript]
---
> JAVASCRIPT STUDY

<strong>for 문과 while 문의 차이를 비교해보자!!</strong>

<strong>로그인 모듈 해보기</strong>

<p class="txt_point02">횟수제한(for문)</p>
{% highlight python %}

// 로그인 성공 여부를 보관하는 변수
var login = false;

// 최대 다섯번의 기회를 준다
for (var i = 0; i < 5; i++){
  var id = window.prompt('아이디를 입력하세요');
  var password = window.prompt('비밀번호를 입력하세요');
  if (id === 'song' && password === '4321') {
    console.log('환영합니다.' + id + '님');
    break;
  } else {
    console.log('아이디와 비밀번호가 일치하지 않습니다.');
  }
}
{% endhighlight %}

<p>먼저 for 문을 사용해서 작성해보면, 최대 다섯번까지 로그인 시도를 할 수 있는데,<br> 다섯번 모두 로그인엥 실패하면 로그인이 되지 않은 채 다음 코드로 넘어간다.</p>

<p class="txt_point02">무제한(while문)</p>

{% highlight python %}

//로그인 성공 여부를 보관하는 변수
var login = false;

//로그인에 성공할때까지 반복 
while (!login) {
  //아이디와 비밀번호를 입력받는다.
  var id = window.prompt('아이디를 입력하세요');
  var password = window.prompt('비밀번호를 입력하세요');

  if (id === 'song' && password === '4321'){
    console.log('환영합니다.' + id + 'id');
    login = true;
  }else {
    console.log('아이디와 비밀번호가 일치하지 않습니다.');
  }
}

{% endhighlight %}

<p>저러면 login 의 값이 false 인 동안, 로그인이 완료되지 않는 동안 while 문은 계속 반복한다.<br>로그인에 성공 할 때 까지 반복문에 머물러 있게 된다.</p>
<p>for 문과 while 문의 차이는 물론 이분법적으로 나눌 수 있는 얘기는 아니지만<br> 일반적으로 반복 횟수가 예측 가능할 땐 for 문을 사용하는것이 눈에 잘 들어온다.</p>