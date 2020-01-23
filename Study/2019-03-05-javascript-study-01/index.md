---
layout: post
title:  "변수와 상수"
subtitle: "알아두면 뼈가되고 살이되는 스크립트"
type: "Javascript"
study: true
text: true
date: "05 MAY 2019" 
---

# AVASCRIPT STUDY(변수&상수)

<p>프로젝트에서 제이쿼리와 스크립트 라이브러리에 의존하지 않고 자바스크립트의 기초를 탄탄히 공부하고 싶어서 인터넷 강의를 시작했다! </p>
<p>앞으로 하나하나 기록해봐야지 :-)</p>

<p class="txt_point">변수 - 언제든 변할 수 있는 값! ex)돈의 액수</p>

```
  1. var score = 0;
  2. var score;
      score = 0;
```

<p>1번과 2번의 의미는 같다.</p>

<p class="txt_point">상수 - 변하지 않는 값! ex)내가 태어난 년도</p>

<pre><code>const MAX_LEVEL = 99; 
</code></pre>

<p>이건 절대 바꿀 수 없음.</p>

<strong>* 변수와 상수를 만들 때 이름 짓는 팁!</strong>

<p>꼭 지켜야 하는 룰(지키지 않으면 오류!)</p>

1. JAVASCRIPT 식별자는 '문자'나 '밑줄' 아니면 '달러기호'로 시작해야 한다. 두번째 글자부터는 숫자도 가능하다.
2. '대문자와' '소문자'를 구별한다. myname 과 myName은 다름
3. '예약어(Javscript가 좋아하는 단어)는 사용하면 안됨 ex) if, var , for 같은 것'

<strong>* 변수와 상수에 넣는 것들?</strong>

<pre><code>var n = 10; 숫자열 - 10
var s = '10'; 문자열 - 10
</code></pre>

<p>확인하고 싶을땐 브라우저의 개발자도구 console에서 typeof 변수; ex) typeof n; 하면 값을 알 수 있다!</p>

<strong>* 데이터 타입</strong>

* 숫자형(number) 예)10, 3.14
* 문자열(string) 예) 'hello', '10'
* 논리형(boolean) 예) true , false