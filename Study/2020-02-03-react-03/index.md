---
layout: post
title:  "JSX는 또 뭐죠 2"
subtitle: "JSX"
type: "React"
study: true
text: true
author: "Song LEEE"
order: 22
date: 02 Feb 2020
---

# JSX가 뭐죠

<p><code>JSX</code>에 대해 자세히 봐보면 얼핏 보기엔 <code>html</code>과 비슷해 보여서 금방 배울 수 있겠다고 생각했다ㅋㅋㅋ</p>
<br>
<p><code>JSX</code>는 리액트 개발을 쉽게 하기 위해서, <code>HTML</code>과 비슷한 문법으로 작성을 하면 이를 <code>React.createElement</code>를 사용하는 자바스크립트 형태로 변환시켜준다.</p>
<br>
<p><code>XML</code>형태의 코드를, 자바스크립트로 변환해야 하기 때문에, <code>JSX</code>를 제대로 사용하기 위해서 몇가지 규칙을 준수해야한다!</p>
<p>css와 svg를 지워주고</p>
{% highlight python %}
  // src/App.js
  import React, { Component } from 'react';

  class App extends Component {
    render() {
      return (
        <div>

        </div>
      );
    }
  }

  export default App;
{% endhighlight %}

## 꼭 닫혀야 하는 태그
<p>태그는 꼭 닫혀있어야 한다! <code><div></code>태그를 열었으면, <code></div></code>를 통하여 태그를 꼭! 닫아주어야 한다.<br>
<code>html</code>에서 <code>input</code>이나 <code>br</code>태그를 작성할 때 태그를 안닫을때도 있는데, 똑같이 리액트에서 한다면 오류를 겪게  된다.</p>
<br>
{% highlight python %}
 import React, { Component } from 'react';

  class App extends Component {
    render() {
      return (
        <div>
          <input type="text">
        </div>
      );
    }
  }

  export default App;

{% endhighlight %}

![에러 이미지]('img/img_error.png')
<br>
<br>

## 감싸져 있는 엘리먼트
<p>두개 이상의 엘리먼트는 무조건 하나의 엘리먼트로 감싸져있어야 한다.</p>

{% highlight python %}
  // src/App.js
  import React, { Component } from 'react';

  class App extends Component {
    render() {
      return (
        <div>
          Hello
        </div>
        <div>
          Bye
        </div>
      );
    }
  }

  export default App;
{% endhighlight %}

![에러 이미지2]('img/img_error02.png')
<p>터미널 쪽에서 오류가 나타나게 된다. 하나의 태그로 감싸져있어야 한다고 에러가 뜬다!<br>이를 해결하기 위한 가장 간단한 방법은 <code>div</code>로 감싸주는 것이다.</p>
<br>
{% highlight python %}
  import React, { Component } from 'react';

  class App extends Component {
    render() {
      return (
        <div>
          <div>
            Hello
          </div>
          <div>
            Bye
          </div>
        </div>
      );
    }
  }

  export default App;
{% endhighlight %}

<p>그런데 가끔 어떠한 상황에서 무분별한 <code>div</code>를 사용하는게 마음에 들지 않을 수 있다! 예를들어 스타일을 제공할때 코드가 꼬일 수도 있고 <code>table</code>관련 태그를 작성할 때 번거로울 수도 있다.</p>
<p>그러한 상황엔 <code>Fragment</code>를 사용하면 된다!!!!!!!!!!!!</p>

{% highlight python %}
  import React, { Component, Fragment } from 'react';

  class App extends Component {
    render() {
      return (
        <Fragment>
          <div>
            Hello
          </div>
          <div>
            Bye
          </div>
        </Fragment>
      );
    }
  }

  export default App;

{% endhighlight %}

## JSX 안에 자바스크립트 값 사용하기