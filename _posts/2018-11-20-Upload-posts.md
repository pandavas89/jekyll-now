---
title: 배경지식 없이 github pages 포스트 올리기
date: 18-11-20 01:00:00
category: github pages
published: False
---

## 1. 포스트의 규칙
일단은, 지난 포스트에서 생성된 첫 포스트를 열어봅시다. github pages의 모든 포스트는 ```_posts```폴더 내에 존재합니다. 브라우저에서 해당 포스트에 접근해 봅시다.

![Find _posts folder]({{ "/assets/image/open_posts.jpg"|absolute_url}})
![Get to _posts folder]({{ "/assets/image/post_folder.jpg"|absolute_url}})
    ---
    layout: post
    title: You're up and running!
    ---
    Next you can update your site name, avatar and other options using the _config.yml file in the root of your repository (shown below).

    ![_config.yml]({{ site.baseurl }}/images/config.png)

    The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.
다음과 같은 내용이 출력됩니다. 이것이 방금 본 포스트의 마크다운 문서입니다.

    ---
    layout: post
    title: You're up and running!
    ---
이 부분이 포스트의 헤더입니다. 여기에는 포스트 본문에 출력되지 않는 다양한 정보가 담깁니다. 현재로서는 포스트의 제목과 레이아웃이 포함되어 있습니다. 이 외에도 작성일자, 카테고리, 혹은 공개여부 등을 헤더를 통해 제어해 줄 수 있습니다.

github에서 제공하는 툴이기 때문에 포스팅도 commit과 push를 통해 이뤄집니다. ```/_posts/``` 폴더 내에 존재하고, 지정된 양식을 따르는 마크업 파일은 모두 포스트로 인식됩니다. YYYY-MM-DD-[제목].md의 형태입니다. 다만, 제목의 경우 스페이스 대신 하이픈으로 연결해줘야 합니다. 또한, 한글로 된 파일 제목은 권장되지 않습니다. 예를 들어, 여러분이 보고 계신 이 포스트는 repository에서 확인할 수 있듯이 ```2018-11-15-fast-start-without-basic.md``` 라는 이름으로 ```_posts``` 폴더 내에 존재합니다.


![Let's create post]({{ "/assets/image/new_post_online.jpg"|absolute_url}})

### 1.1. 온라인에서 포스트 작성/수정하기
가장 기초적인 포스트 작성/수정 방법은 github에서 직접 하는 것입니다. github 저장소 내의 ```_posts```폴더에서 수정을 원하는 파일을 선택해 줍니다. 이 경우엔, ```2014-11-1-first-post.md```를 수정해 보겠습니다. 다음과 같은 화면이 나타납니다. 연필 버튼을 누르면 파일에 대한 수정이 가능해집니다. 헤더가 아닌 본문 부분에 원하는 내용을 입력하거나 지워봅니다. github 저장소 내에서 모든 파일 변화는 commit과 push, 두 과정을 거쳐야 합니다. 이는 오픈 소스 개발에서 주로 사용되는 기능이고, 사실상 1인 기여인 우리의 github pages에서는 그저 동시에 commit과 push를 해주면 됩니다.

새롭게 포스트를 작성할 경우, 정해진 규칙에 따라 포스트 파일을 작성해야 합니다. ```yyyy-MM-dd-post-title.md```입니다. 이는 Jekyll이 포스트를 인식하기 위한 조건이기 때문에, 제목 규칙에 어긋나는 포스트는 ```_posts```폴더에 들어있더라도 포스트로 보여지지 않습니다. 또, 앞서 살펴본 것과 마찬가지로 헤더를 직접 삽입해야만 github pages에 표시되는 데에도 문제가 없습니다.

### 1.2. 오프라인에서 포스트 작성/수정하고 업로드하기
따라해 보신 분들은 느끼셨겠지만, 매번 github에 접속해 새로운 포스트를 작성하면 번거롭습니다. 이 과정을 조금 더 간단하게 해결하는 방법이 있습니다. atom IDE인데요, 이를 통해 단순히 마크다운 문서를 작성하는 것 뿐만 아니라 마크다운 문서의 미리보기, 저장소로의 commit과 push까지 한번에 처리할 수 있습니다. 설치 과정은 다음의 [링크](http://ide.atom.io)를 참조하세요. IDE는 (통합 개발 환경) Integrated Development Envirnment의 약자로, 다양한 프로그래밍 언어를 인식해 코드의 가시성을 높여주는 역할을 포함해 다양한 편의기능을 제공합니다.
atom IDE의 설치가 끝났다면 바로 나만의 포스트를 작성해 보는것도 좋겠지만, 더 편리하게 포스트와 github pages를 관리하기 위해서는 약간의 추가 과정이 필요합니다. ```ctrl+shift+P```키를 통해 command palette를 켜고, ```GitHub: Clone```을 입력하면 clone repository가 끝납니다. 이 과정을 통해 얻은 것은, 여러분의 github repository와 연결된 local repository입니다. 이를 통해 여러분은 atom의 git을 이용해 github pages의 변경사항을 빠르게 업로드 할 수 있습니다. 앞서와 같이, 먼저 ```2014-1-11-first-post.md```를 변경해보겠습니다.
```ctrl+shift+7``` 단축키를 통해 git 탭에 접근할 수 있고, 상태표시줄 오른쪽 하단의 git 상태창을 통해서도 접근할 수 있습니다. 변경사항이 있었다면, git 탭에서 변경된 파일들을 확인할 수 있습니다. 신규 파일은 초록색, 변경 파일은 노란색으로 표시됩니다. 업로드 할 파일을 선택해 ```stage``` 버튼을 누르면, commit 대상이 선정됩니다. 하단의 텍스트 창에 코멘트를 입력하고 commit 버튼을 누르면, 인터넷을 통해 했던 것과 동일하게 commit이 완료됩니다. 이 때, 상태표시줄에서 생긴 변화를 알아채셨나요? ```fetch```가 ```push```로 바뀌었습니다. 이제 ```push```를 클릭하면, 역시 인터넷을 통한 것과 마찬가지로 푸시가 완료됩니다. 변경사항이 github pages에 반영되었는지 확인해 봅시다.


## 2. 포스트 내용 작성
마크다운은 조금 낯설 수도 있습니다. 여러분이 잘 알고 있는 네이버 블로그나 한글, word 등에서 보던 것과 달리, 아무런 참고할 거리가 없는 흰 화면만 채워지길 기다리고 있습니다. 이것이 바로 WYSIWYG와 마크업 언어의 차이점입니다. ```WYSIWYG```는 ```What you see is what you get```의 약자로, 여러분이 보는 그대로 문서가 만들어지는 방식입니다. 반대로 마크업 언어는 그런 모든 설정을 약속된 기호를 통해 사용합니다.

기초적인 수준의 마크다운 문법은 다음 [링크](https://gist.github.com/ihoneymon/652be052a0727ad59601)를 참조하세요


카테고리 관리하는 방법 [링크](https://codinfox.github.io/dev/2015/03/06/use-tags-and-categories-in-your-jekyll-based-github-pages/)
