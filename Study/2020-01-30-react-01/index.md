---
layout: post
title:  "React는 무엇이죠"
subtitle: "리액트 공부를 시작해보자"
type: "React"
study: true
text: true
author: "Song LEEE"
order: 20
date: 30 Jan 2020
---

# React

<p>
퍼블리셔 구인구직 사이트에는 우대사항에 <code>React</code> <code>Vue</code> <code>Angular</code> 이 세가지 프레임워크 사용이 올라오기 시작했다. 
'이게 뭐람? 난 아직 스크립트도 잘 모르는데 또 배울게 있네' 점점 퍼블리셔와 프론트엔드 개발자의 경계가 무너지고 있다고 느꼈다.
<br>그래서 시작한 리액트 공부! 아직 스크립트도 제대로 모르면서 왠 리액트람? 이라 생각하지만, 조금씩 스크립트 공부랑 같이 해봐야겠다.</p>

## 페이스북이 만든 리액트
<p>"컴포넌트"라는 개념에 집중이 되어있는 라이브러리이다.</p>
<p><code>Virtual DOM</code>이라는 가상의 DOM을 이용한다. 실제로 브라우저의 DOM에 새로운걸 넣는것이 아니라,<br>자바스크립트로 이뤄진 가상 DOM에 한번 렌더링을 하고, 기존의 DOM과 비교를 한 다음에 정말 변화가 필요한 곳에만 업데이트를 해준다. <br><code>Virtual DOM</code>을 사용함으로서 데이터가 바뀌었을 때 더이상 어떻게 업데이트를 할 지를 고려하는게 아니라 일단 바뀐 데이터로 그려놓고 비교를 한 다음에, 바뀐 부분만 알아서 찾아서 바꿔 준다고 한다! </p>

[Virtual DOM에 관련된 영상](https://www.youtube.com/watch?v=muc2ZF0QIO4) (https://www.youtube.com/watch?v=muc2ZF0QIO4)

<p><code>Virtual DOM</code>은 DOM변화를 최소화 시켜주는 역할을 하는데 이 횟수를 최소화 시키는것은 성능적으로 매우 중요한 이슈라고 한다.</p>

## 리액트 프로젝트 시작해보기
<p>리액트 프로젝트는 보통 JQuery 같은것을 단순히
{% highlight python %}
<script src="..."></script> 
{% endhighlight %}
의 형태로 불러와서 사용했던 것 처럼 사용하지는 않는다. 그렇게 한다면 굉장히 제한적이다. 그 대신 리액트 프로젝트를 제대로 작업하려면 컴퓨터에 <code>Node</code> <code>yarn</code> <code>Webpack</code> <code>Babel</code>등의 도구를 설치하여 프로젝트를 설정해줘야 한다.</p>
<br>

### Webpack, Babel이란?

<p>리액트 프로젝트를 만들게 되면, <code>컴포넌트</code>를 여러가지 파일로 분리해서 저장할 것이고, 또 이 컴포너트는 일반 자바스크립트가 아닌 <code>JSX</code>라는 문법으로 작성하게 된다. 여러가지의 파일을 한개로 결합하기 위해서 Webpack이라는 도구를 사용하고, JSX를 비롯한 새로운 자바스크립트 문법들을 사용하기 위해서 Babel 이라는 도구를 사용한다.</p>

## 준비사항
1. <code>Node.js</code> : Webpack과 Babel 같은 도구들이 자바스크립트 런타임인 Node.js를 기반으로 만들어졌다. 그렇기 때문에 해당 도구들을 사용하기 귀해 Node.js를 설치한다.
2. <code>Yarn</code> : Yarn은 조금 개선된 버전의 npm이라고 생각하면 된다. npm은 Node.js를 설치하게 될때 같이 딸려오는 '패키지매니저' 도구이다. 프로젝트에서 사용되는 라이브러리를 설치하고 해당 라이브러리들의 버전 관리를 하게 될때 사용한다.<br>
Yarn을 사용하는 이유는 '속도'와 '캐싱 시스템'을 사용하기 위함이다.
3. <code>코드 에디터</code> : VSCode 라던지 Atom WebStorm Sublime 같은 에디터!
4. <code>Git Bash</code> : Window 의 경우 Git for Window를 설치하여 Git Bash를 사용할것!

### Node.js 설치하기

* [설치 URL](https://nodejs.org/ko/download/)
<p>LTS 버전 최신으로 설치하면 된다!</p>

### Yarn 설치하기

* [설치 URL](https://legacy.yarnpkg.com/en/docs/install#windows-stable)
<p>각자의 운영체제에 맞는걸로 설치하면 된다.</p>


