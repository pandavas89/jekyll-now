---
title: 배경지식 없이 github pages 만들기
date: 18-11-20 20:30:00
category: github pages
published: True
---

github pages는 github에서 제공하는 블로그입니다. 이 포스팅은 프로그래밍 관련 지식이 전무한 초보자를 대상으로 전제합니다.

## 1. github ID 만들기

github pages는 github에서 제공하는 서비스인 만큼, 계정이 필요합니다. 구글이나 페이스북 등의 기존 계정을 통해 만들수도 있고, 이메일 주소를 이용해 새롭게 만들어도 좋습니다.
![Let's sign up]({{ "/assets/image/sign_up.jpg"|absolute_url}})


username을 만들 때 한 가지 유의해야 할 것은, 별도의 도메인을 사용하지 않는 한 github pages를 이용해 만들어지는 블로그의 주소가 ```[github username].github.io```로 고정된다는 점입니다. repository를 수정한다고 해서 주소를 바꿀 수는 없으며, 단지 repository와 github pages의 연결이 끊어질 뿐입니다. 마음에 드는 아이디가 모두 사용중이라고 해서 남 보여주기 창피한 아이디를 만들면 외부 도메인을 사야 하는 사태가 벌어집니다. 주의합시다.


## 2. Jekyll 그런건 난 모르겠고, 일단 fork!
Jekyll은 Ruby 기반의 정적 사이트 생성기입니다. 따라서, Jekyll을 구동하기 위해선 Ruby 개발환경을 먼저 갖춰줘야 합니다. 하지만 그러려고 이 포스팅을 만든 게 아닙니다. 그러니 더 쉬운 방법을 찾아봅시다. [jekyll-now](https://github.com/barryclark/jekyll-now)입니다. github은 버전 관리 프로그램의 특성을 살려서 이미 작동하는 github pages를 포크하여 자신만의 블로그를 새롭게 시작할 수 있습니다.


![How to fork]({{ "/assets/image/fork.jpg"|absolute_url}})

fork 버튼을 누르면, 자신의 저장소로 현재 저장소가 통째로 복사됩니다. 저장소의 이름을 ```[github ID].github.io```로 바꿔줍니다.


![Let's change repo name]({{ "/assets/image/rename.jpg"|absolute_url}})

이제 자신의 github pages에 접속해 봅시다. ```[github ID].github.io```를 입력합니다.


![Access to the github pages]({{ "/assets/image/access.jpg"|absolute_url}})

Jekyll-now의 기본 테마가 여러분을 환영해줍니다!

다음 포스트에서는 포스트를 만드는 방법, 그리고 조금 더 간편한 편집/업로드를 위해 Atom IDE를 설치해 보겠습니다.
