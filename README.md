# hexo-example

hexo를 이용하여 blog theme 적용하기.

## hexo를 선택한 이유

팀에서 작업중인 개인 형 블로그를 만들어 주는 서비스를 기획하는 과정에서 [StaticGen](https://www.staticgen.com/)에서 검토하던 중 Jekyll, HubPress등을 검토하다가 블로그 형태에 가장 적합할 것 같다고 판단하여 [**Hexo**](https://www.staticgen.com/hexo)를 선택하게 되었다.

가장 큰 이유는 언어가 javascript라는 점, 다양한 테마들이 있다는 점으로 선택하게 되었다.

내부적으로 [다양한 테마](https://hexo.io/themes/)들 중 [hexo-theme-chan](https://github.com/denjones/hexo-theme-chan)을 선택했고, [블로그 - http://wagunblog.com](http://wagunblog.com/wp/) 내용들을 한 번 옮겨보려고 한다.

## Hexo 시작하기

### hexo-cli를 설치

```
npm install hexo-cli -g		// hexo를 global로 설치
hexo init hexo-example		// 현재 디렉토리의 하위 디렉토리가 생성됩니다.
cd hexo-example
```

### localhost로 확인하는 방법

```
hexo server
```

브라우저에 http://localhost:4000/을 통해서 확인.

![Hexo landscape theme](/ignoreDir/img/sample1.jpg)

### hexo-theme-chan 테마 설치

```
git clone https://github.com/denjones/hexo-theme-chan.git themes/chan	// theme 설치
```

### 테마 연결하기

`hexo-example/_config.yml`파일에서 기본으로 설정되어있는 `theme: landscape`를 `theme: chan`으로 변경

### 서버 재시작 및 확인

```
hexo server
```

브라우저에 http://localhost:4000/을 통해서 확인.

![Hexo chan theme](/ignoreDir/img/sample2.jpg)

### deploy git

[`hexo-deployer-git`](https://github.com/hexojs/hexo-deployer-git) 설치

```
npm install hexo-deployer-git --save
```

`hexo-example/_config.yml`파일에서 다음과 같이 추가 설정

```
# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
...
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: <repository 주소>(ex : https://github.com/kjk7034/hexo-example.git)
  branch: <branch로 deploy 할 경우> gh-pages
  message: <commit 메시지>
```

배포
```
hexo clean
hexo deploy
```