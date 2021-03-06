---
layout: post
title:  "AMP는?"
subtitle: "amp에 관한 간단한듯 어려운 포스팅"
type: "Google AMP"
etc: true
text: true
order: 3
date: 17 Jun 2019
---

<p>한 회사에서 AMP방식으로 작업을 한다 하여 열심히 구글링을 해보았다.</p>

<p>모바일 기기에서 웹 사이트의 접근성을 높이기 위한 가속화 모바일 페이지</p>
<p>거의 즉시에 가까운 페이지 로딩을 위해 여러 기법들로 최적화 하였고 AMP HTML/JS/CSS 로 구성되어 있다.</p>

<br>
<br>
<br>

<strong>AMP 동작 원리</strong>

<p class="txt_point no-bottom">AMP에 포함되는 모든 자바스크립트는 비동기 방식으로 실행된다.</p>

1. AMP에는 개발자가 직접 작성한 별도의 자바스크립트를 포함될 수 없다.
2. 페이지 동작과 관련된 부분은 커스텀 AMP요소를 통해 구현할 수 있다.
3. iframe 안에 별도로 외부 자바스크립트 라이브러리를 포함할 수 있다.(메인 페이지 렌더링에 방해 안됨)

<br>

<p class="txt_point no-bottom">이미지,광고,iframe과 같은 외부 리소스들의 사이즈와 위치를 지정해야 한다.</p>

1. 외부 리소스를 다운받기 전에 HTML요소의 사이즈를 지정하면, 리소스 다운로드 여부와 관계없이 페이지 레이아웃을 정할 수 있다.
2. 이러한 원리로 전체 문서의 레이아웃을 정하기 위해 단 한번의 HTTP요청만 필요하다!
3. 따라서 리소스가 로딩될 때 레이아웃을 다시 그릴 필요가 없다.

<br>

<p class="txt_point no-bottom">커스텀 스크립트를 사용하는 경우 커스텀 태그를 지정해주어야 한다.</p>
{% highlight python %}
<script async custom-element="amp-iframe" src="https://cdn.ampproject.org/v0/amp-youtube-0.1.js"></script>
{% endhighlight %}

<br>

<p class="txt_point no-bottom">외부 라이브러리들이 렌더링 동자겡 방해되지 않도록 한다.</p>

1. AMP는 외부 자바스크립트 라이브러리를 iframe 안에서만 허용한다.(메인 페이지 실행을 방해하지 않음)
2. iframe 에서 스타일 재계산이나 페이지 레이아웃 재종어 일어나더라고, DOM 사이즈가 작기 때문에 속도가 빠르다.

<br>

<p class="txt_point no-bottom">모든 CSS 스타일은 인라인이어야 하고 사이즈가 제한되어 있다.</p>

1. 인라인 CSS 스타일은 1개만 허용되기 때문에 다른 웹사이트에 비해 최소 1개 이상의 HTTP 요청을 줄인다. 
2. 인라인 CSS 스타일의 최대 사이즈는 50kb

<br>

<p class="txt_point no-bottom">웹 폰트 요청은 효율적으로 해야한다.</p>

1. 일반적인 웹 페이지에서는 외부 자바스크립트와 스타일 시트를 순차적으로 로딩한 후 폰트를 다운받는다.
2. AMP 에서는 폰트를 받기까지의 외부 자바스크립트와 스타일 시트를 다운받는 HTTP 요청이 존재하지 않는다.
3. 자바스크립트의 경우 async 속성을 스타일 시트의 경우 인라인을 이용하기 때문 

<br>

<p class="txt_point no-bottom">스타일 재계산 최소화 하기</p>

1. 페이지에서 요소 측정이 일어날 때마다 스타일이 제 계산 된다.
2. 그리고 이는 전체 페이지 레이아웃 재조정과 열결되기 때문에 많은 비용이 소모된다. 
3. 모든 DOM 을 화면에 그리기 전에 읽기 때문에 한 프레임당 최대 한번만 스타일을 재계산한다.

<br>

<p class="txt_point no-bottom">GPU 가속화 애니메이션만 사용</p>

1. 빠른 성능을 위한 최적화 방법은 GPU 위에서 애니메이션을 실행하는것이다.
2. GPU의 단점은 페이지 레이아웃 재조정을 못하는 것인데 이 작업을 보통 브라우저에 위임한다.
3. 애니메이션은 GPU에서 실행될 수 있도록 CSS 규칙을 정해야 한다.
4. 특히 AMP는 애니메이션 작업과 변환 작업을 transform 과 opacity 에서 하기 때문에 레이아웃 조정이 필요 없다.

<br>

<p class="txt_point no-bottom">AMP는 리소스 로딩 순서를 정한다.</p>

1. AMP는 리소스 다운로드를 모두 제어하고 중요도에 따라 순서를 정한다.
2. 이미지나 광고는 필요한 경우에만 빨리 다운로드 한다.
3. 레이지 로딩 관련 리소스는 pre-fetch를 해놓기 때문에 로딩이 되어야 하는 시점에 더 빠르게 로딩되고 CPU는 필요시에만 사용 된다.

<br>
<br>
<br>

<strong>AMP 시작하기</strong>

{% highlight python %}
<!doctype html>
<html amp lang="en">
  <head>
    <meta charset="utf-8">
    <script async src="https://cdn.ampproject.org/v0.js"></script>
    <title>Hello, AMPs</title>
    <link rel="canonical" href="http://example.ampproject.org/article-metadata.html" />
    <meta name="viewport" content="width=device-width,minimum-scale=1,initial-scale=1">
    <script type="application/ld+json">
      {
        "@context": "http://schema.org",
        "@type": "NewsArticle",
        "headline": "Open-source framework for publishing content",
        "datePublished": "2015-10-07T12:02:41Z",
        "image": [
          "logo.jpg"
        ]
      }
    </script>
    <style amp-boilerplate>body{-webkit-animation:-amp-start 8s steps(1,end) 0s 1 normal both;-moz-animation:-amp-start 8s steps(1,end) 0s 1 normal both;-ms-animation:-amp-start 8s steps(1,end) 0s 1 normal both;animation:-amp-start 8s steps(1,end) 0s 1 normal both}@-webkit-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-moz-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-ms-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-o-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}</style>
    <noscript><style amp-boilerplate>body{-webkit-animation:none;-moz-animation:none;-ms-animation:none;animation:none}
    </style></noscript>
  </head>
  <body>
    <h1>Welcome to the mobile weg</h1>
  </body>
</html>
{% endhighlight %}

<br>

<p>위에 코드에서 AMP과 관련된 부분은</p>

{% highlight python %}
<!-- AMP 자바스크립트 라이브러리 로딩 -->
<script async src="https://cdn.ampproject.org/v0.js"></script>

<!-- AMP CSS 스타일 -->
<style amp-boilerplate>body{-webkit-animation:-amp-start 8s steps(1,end) 0s 1 normal both;-moz-animation:-amp-start 8s steps(1,end) 0s 1 normal both;-ms-animation:-amp-start 8s steps(1,end) 0s 1 normal both;animation:-amp-start 8s steps(1,end) 0s 1 normal both}@-webkit-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-moz-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-ms-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-o-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}</style>
<noscript><style amp-boilerplate>body{-webkit-animation:none;-moz-animation:none;-ms-animation:none;animation:none}</style></noscript>
{% endhighlight %}

1. AMP에서 일반 HTML 태그들은 그대로 사용되지만, 위와 같이 img 태그는 amp-img 로 변환하여 사용한다.
2. ambed, param 등등 몇개의 HTML 표준 태그들은 AMP에서 사용할 수 없다. [참고!](https://github.com/ampproject/amphtml/blob/master/spec/amp-html-format.md)
3. amp-img 태그를 사용하는 이유는 해당 리소스가 로딩되기 전에 페이지 레이아웃을 정하고 
레이지 로딩에 대한 네트워크 제어와 리소스 로딩 우선순위를 효율적으로 관리하기 위함

<strong>AMP CSS 스타일링 추가</strong>

<p>AMP의 요소에 대한 스타일링은 &lt;style amp-custom&gt; 태그를 이용한다.</p>

{% highlight python %}
<style amp-custom>body{background-color:white;} amp-img{background-color:gray; border:1px solid black;}</style>
{% endhighlight %}

<p class="txt_point no-bottom">AMP CSS 스타일링에 대해 주의해야 할 점!!</p>

1. 모든 AMP 페이지는 <style amp-custom> 태그 한 개만 포함할 수 있다.
2. HTML 인라인 CSS를 사용할 수 없다. 모든 스타일 규칙은 head 안에 선언되야함.
3. !important 를 비롤하여 몇몇 표준 스타일 규칙을 사용할 수 없고 외부 스타일 시트 참조도 불가능 하다.(커스텀 폰트 제외)

<p class="txt_point no-bottom">AMP 검색과 배포</p>

1. 같은 웹 컨텐츠에 대해 AMP, non AMP 페이지 2개를 모두 갖고 있는 경우가 있다.
2. 이러한 경우 <link> 를 이용해서 두 페이지를 연결한다.
3. 일반 HTML 페이지에서는 

{% highlight python %}
<link rel="amphtml" href="https://www.example.com/url/to/amp/document.html">
{% endhighlight %}

4. AMP 페이지에는
{% highlight python %}
<link rel="canonical" href="https://www.example.com/url/to/full/document.html">
{% endhighlight %}

5. 만약 구분 없이 AMP 페이지만 가지고 있을 경우
{% highlight python %}
<link rel="canonical" href="https://www.example.com/url/to/amp/document.html">
{% endhighlight %}

<strong>튜토리얼 결과 페이지</strong>

<p>위 코드들의 결과물을 아래와 같다.</p>

![getting-started-result](https://user-images.githubusercontent.com/43769441/59585538-b054c200-911b-11e9-9efe-aff0178157c0.png)

<strong>참고하면 좋은 사이트</strong>

[AMP 사이트](https://amp.dev/)
[google 공식 블로그](https://googleblog.blogspot.com/2015/10/introducing-accelerated-mobile-pages.html)