---
title: 배경지식 없이 github pages 만들기
date: 18-11-15 13:15:00
category: github pages
published: false
---

github pages는 github에서 제공하는 블로그입니다. 이 포스팅은 프로그래밍 관련 지식이 전무한 초보자를 대상으로 전제합니다.

## 1. github ID 만들기

github pages는 github에서 제공하는 서비스인 만큼, 계정이 필요합니다. 구글이나 페이스북 등의 기존 계정을 통해 만들수도 있고, 이메일 주소를 이용해 새롭게 만들어도 좋습니다. ID를 만들 때 한 가지 유의해야 할 것은, 별도의 도메인을 사용하지 않는 한 github pages를 이용해 만들어지는 블로그의 주소가 ```[github ID].github.io```로 고정된다는 점입니다. repository를 수정한다고 해서 주소를 바꿀 수는 없으며, 단지 repository와 github pages의 연결이 끊어질 뿐입니다. 마음에 드는 아이디가 모두 사용중이라고 해서 남 보여주기 창피한 아이디를 만들면 외부 도메인을 사야 하는 사태가 벌어집니다. 주의합시다.


## 2. Jekyll 그런건 난 모르겠고, 일단 fork!
Ruby 환경에서 Jekyll을 구동하는 걸 어려워하는 사람이 당연히 한둘이 아닙니다. 그래서 바로 이 프로젝트가 있습니다. barry clark씨에 의해 만들어진 [jekyll-now](https://codinfox.github.io/dev/2015/03/06/use-tags-and-categories-in-your-jekyll-based-github-pages/)입니다. 당장 작동하는 github pages를 fork해서 블로그 제목이나 설명, 링크 등을 모조리 갈아치우고 내 것인 척 합시다. fork란, 다른 이의 repository를 가져와서 원 repository에 영향을 주지 않고 독자적인 master branch를 만들어 나가겠다는 의미입니다. 달리 얘기하면, '오케이, 거기까지. 이제부턴 갈라서자'는 얘긴데, 사실 우리는 jekyll-now에 기여한 바가 없기 때문에 '오케이, 거기까지. 이제부턴 내가 할게'에 더 가깝겠습니다.

##3. 포스트 만드는 방법
github에서 제공하는 툴이기 때문에 포스팅도 commit과 push를 통해 이뤄집니다. ```/_posts/``` 폴더 내에 존재하고, 지정된 양식을 따르는 마크업 파일은 모두 포스트로 인식됩니다. YYYY-MM-DD-[제목].md의 형태입니다. 다만, 제목의 경우 스페이스 대신 하이픈으로 연결해줘야 합니다. 또한, 한글로 된 파일 제목은 권장되지 않습니다. 예를 들어, 여러분이 보고 계신 이 포스트는 repository에서 확인할 수 있듯이 ```2018-11-15-fast-start-without-basic.md``` 라는 이름으로 ```_posts``` 폴더 내에 존재합니다.

##4. 포스트 내용 작성
마크다운은 조금 낯설 수도 있습니다. 여러분이 잘 알고 있는 네이버 블로그나 한글, word 등에서 보던 것과 달리, 아무런 참고할 거리가 없는 흰 화면만 채워지길 기다리고 있습니다. 이것이 바로 WYSIWYG와 마크업 언어의 차이점입니다. ```WYSIWYG```는 ```What you see is what you get```의 약자로, 여러분이 보는 그대로 문서가 만들어지는 방식입니다. 반대로 마크업 언어는 그런 모든 설정을 약속된 기호를 통해 사용합니다.

기초적인 수준의 마크다운 문법은 다음 [링크](https://gist.github.com/ihoneymon/652be052a0727ad59601)를 참조하세요


카테고리 관리하는 방법 [링크](https://codinfox.github.io/dev/2015/03/06/use-tags-and-categories-in-your-jekyll-based-github-pages/)