---
layout: post
title: Javascript String 정리
categories: [Javascript]
---
> JAVASCRIPT STUDY

<strong>문자열의 길이</strong>

<p class="txt_point">length 속성은 문자열의 길이를 담고 있습니다.</p>

{% highlight python %}
  var str = 'SongE';
  console.log(str.length);
{% endhighlight %}

```
결과 : 5
```

<br>
<br>
<br>

<strong>특정 인덱스의 문자 받아오기</strong>

<p class="txt_point">str.charAt(index)를 하면 문자열 str의 index 인덱스에 있는 문자를 받아올 수 있습니다.str[index]와 같은 셈</p>

{% highlight python %}
  var str = "SongE";
  console.log(str.charAt(2));
{% endhighlight %}

```
결과 : n
```
<p class="txt_point">str.charAt(index)와 str[index]에는 약간의 차이가 있다.</p>

<br>
<br>
<br>

<strong>문자열 안에서 다른 문자열 검색</strong>

<p class="txt_point">str.indexof(searchValue)를 하면 문자열 str 내에 문자열 searchValue가 포함되어 있는지 확인할 수 있다.</p>

1. 만약 포함되어 있다면 문자열이 시작되는 문자의 인덱스가 리턴된다.
2. 포함되어있지 않다면 -1이 리턴된다
3. 여러번 포함되어 있다면 처음 발견된 인덱스가 리턴된다.

{% highlight python %}
  var str = 'Hello World';

  console.log(str.indexOf('e'));
  console.log(str.indexOf('z'));
  console.log(str.indexOf('ello'));
  console.log(str.indexOf('o'));
{% endhighlight %}

```
결과 : 1
결과 : -1
결과 : 1
결과 : 4
```

<br>
<br>
<br>

<strong>마지막 인덱스 찾기</strong>

<p class="txt_point">lastindexOf는 indexOf와 동일한데 가장 뒤에 위치한 검색 결과를 찾아준다.<br>예를들면 'Hello World'에는 o가 두 번 나온다.<br>이 때 indexOf는 앞에 있는 o를 last indexOf는 뒤에 있는 o를 찾아준다.</p>

{% highlight python %}
  var str = 'Hello World';

  console.log(str.indexOf('o'));
  console.log(str.lastindexOf('o'));
{% endhighlight %}

```
결과 : 4
결과 : 7
```

<br>
<br>
<br>

<strong>대소문자 변환</strong>

<p class="txt_point02">대문자로 바꾸기</p>

<p class="txt_point">str.toUpperCase()를 하면 str의 모든 글자가 대문자로 바뀌어서 리턴된다.</p>

{% highlight python %}
  var str = "SongE"
  consle.log(str.toUpperCase());
{% endhighlight %}

```
결과 : SONGE
```

<p class="txt_point02">소문자로 바꾸기</p>

<p class="txt_point">str.toLowerCase()를 하면 str의 모든 글자가 소문자로 바뀌어 리턴된다.</p>

{% highlight python %}
  var str = "SongE"
  consle.log(str.toLowerCase());
{% endhighlight %}

```
결과 : songe
```

<br>
<br>
<br>

<strong>문자열 자르기</strong>

<p class="txt_point02">시작 지점과 끝 지점으로 자르기</p>

<p class="txt_point">str.substring(indexStart, indexEnd)를 하면 인덱스 indexStart부터 인덱스 indexEnd까지의<br>문자열을 잘라서 만든 새로운 문자열이 리턴된다. 만약 indexEnd를 쓰지 않으면, 인덱스 indexStart 부터 끝까지 문자열이 잘린다.</p>

{% highlight python %}
  var str = 'Hello World!';

  console.log(str.substring(2,5));
  console.log(str.substring(2));
{% endhighlight %}

```
결과 : llo
결과 : llo World!
```

<p class="txt_point02">시작 지점과 길이로 자르기</p>

<p class="txt_point">str.substr(start, length)를 하면 인덱스 start부터 길이 length의 문자열이 잘려서 리턴된다.</p>

{% highlight python %}
  var str = 'Hello World!';

  console.log(str.substr(2,5));
{% endhighlight %}

```
결과 : llo W
```

<p class="txt_point02">앞뒤의 공백을 없애줍니다.</p>

<p class="txt_point">str.trim()을 하면 문자열 str의 앞뒤로 있는 '공백(띄어쓰기,들여쓰기,줄바꿈 등)'을 모두 지운 새로운 문자열이 리턴된다.</p>

{% highlight python %}
  var str ='              Hello World!          ';

  console.log(str.trim());
{% endhighlight %}

```
결과 : Hello World!
```

<br>
<br>
<br>

<strong>그리고? 더 많은 정보를 알고 싶다면</strong> [참고!](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/prototype)