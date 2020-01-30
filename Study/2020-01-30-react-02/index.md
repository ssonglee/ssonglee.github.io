---
layout: post
title:  "JSX는 또 뭐죠"
subtitle: "새로운 문법인가요? JSX는 뭐에요"
type: "React"
study: true
text: true
author: "Song LEEE"
order: 21
date: 30 Jan 2020
---

# 컴포넌트부터 파헤치기

<p>지금 현재 인프런에서 공부 하고 있는 분의 컴포넌트 코드를 확인해보면</p>
{% highlight python %}

import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';

class App extends Component {
  render() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
        <p className="App-intro">
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
      </div>
    );
  }
}

export default App;
{% endhighlight %}

<p>하 이게 무슨소리인지.. HTML만 알겠고 위에 스크립트 코드는 하나도 모르겠다... 설명을 보면</p>
{% highlight python %}
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';
{% endhighlight %}
<p>천사 선생님의 설명을 보면 <code>import</code> 한다는 것은 무엇을 불러온다는것! 첫번째 코드는 리액트와 그 내부의 <code>Component</code>를 불러온다. 파일에서 <code>JSX</code>를 사용하려면,<br> 꼭 <code>React</code>를 <code>import</code>해주어야 한다.</p>

<p>그 아래는 같은 디렉토리에 있는 <code>logo.sgv</code>와 <code>App.css</code>파일을 불러 왔다.</p>
<p>이렇게 <code>import</code>한다는 것은 <code>webpack</code>을 사용하기에 가능한 작업이라고 한다! 이렇게 불러오고나면 나중에 프로젝트를 빌드하게 될 때 <code>webpack</code>에서 파일의 확장자에 따라 다른 작업을 하게 된다. CSS 파일을 불러오게 되면, 나중에 프로젝트에서 사용한 프로젝트를 한 파일에 모두 결합해주는 작업을 진행하고, Javascript 파일을 불러오게 되면 모든 코드들이 제대로 로딩되게끔 순서를 설정하고 하나의 파일로 합쳐준다.</p>
<p>규칙에 따라 여러 파일로 분리해서 저장하는것도 가능하다. 그리고 svg처럼 사전에 따로 설정이 되지 않은 확장자의 경우 그냥 파일로서 불러온 다음에 나중 특정 경로에 사본을 만들어주게 되고, 해당 사본의 경로를 텍스르로 받아오게 된다.</p>
<br>

{% highlight python %}
class App extends Component {
  ...
}
{% endhighlight %}

<p>컴포넌트를 만드는 방법은 두가지가 있다. 그 중 하나는 위처럼 클래스를 통해서 만드는 것이다. <br>
또 다른 방법은 함수를 통하여 컴포넌트를 만드는 것이다. </p>
<br>
{% highlight python %}
  render() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
        <p className="App-intro">
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
      </div>
    );
  }
{% endhighlight %}
<p>클래스 형태로 만들어진 컴포넌트에는 꼭 <code>render</code>함수가 있어야 한다.<br> 그리고 그 내부에서는 <code>JSX</code>를 <code>return</code>해줘야 한다. 위에 보이는 코드가 JSX이다.</p>
<br>
{% highlight python %}
  export default App;
{% endhighlight %}
<p>작성한 컴포넌트를 다른곳에서 불러와서 사용할 수 있도록 내보내기를 해주는 코드이다.</p>