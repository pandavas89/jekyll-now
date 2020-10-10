---
title: 파이썬 기초 강습 1 - Atom IDE 설치
date: 20-10-10 00:00:00
categories: python
published: True
---
지난 글에서 우리는 컴퓨터에 파이썬을 설치하고 가장 기초적인 프로그램인 Hello, world!를 작성해 보았습니다. 하지만 메모장으로 작성한 코드를 프롬프트 창에서 실행하는 것은 무척 번거롭고, 프로그래밍을 하고 있다는 느낌도 들지 않는 일입니다. 편리하고 보기 좋은 프로그래밍을 위해서 우리는 IDE를 사용합니다.

## IDE?
IDE는 Integrated Development Environment의 약자로 통합 개발 환경을 의미합니다. 이미 사용해 본 메모장과 같은 텍스트 편집기지만, 개발에 필요한 다양한 기능이 추가되어 있는 것이라고 생각하면 될 것 같습니다. 파이썬 개발에서 많이 사용되는 IDE는 Atom IDE, pycharm, vscode 등이 있습니다.

## IDLE
먼저 파이썬을 설치하면 기본적으로 따라오는 IDE인 IDLE를 사용해 보겠습니다.

![IDLE 화면]({{ "/assets/image/python_1/IDLE_window.png"}})

IDLE를 실행하면 어딘가 익숙한 화면이 반겨줍니다. 배경이 흰 색이냐 검은색이냐의 차이가 있을 뿐, 프롬프트 창에서 파이썬을 실행했을 때와 동일한 화면이 보입니다. 이러한 화면을 Shell이라고 합니다. 우리가 입력하는 명령을 실행하도록 해 주는 화면이라고 이해하면 빠릅니다. 그러면 지난 시간에 작성했던 hello_world.py를 불러와 보겠습니다. File-Open 메뉴를 선택해 줍니다.

![IDLE 불러오기]({{ "/assets/image/python_1/IDLE_open.png"}})

지난 번 작성한 메모장과 동일한 내용이 새 창으로 나타납니다. 한 가지 차이점이 있다면, print는 보라색, "Hello, world!"는 초록색으로 되어 있다는 것입니다. 이것이 IDE의 중요한 기능 중 하나입니다. __지원하는 프로그래밍 언어에 대해서, 그것이 의미하는 바에 따라 다른 색상을 부여하여 프로그래머가 더 쉽게 알아볼 수 있도록 해 줍니다.__ 그러면 이 코드를 실행해 보겠습니다. Run-Run Module 메뉴를 선택해줍니다. 혹은 F5 버튼을 눌러도 됩니다.

![IDLE 실행]({{ "/assets/image/python_1/IDLE_run.png"}})

![IDLE 쉘]({{ "/assets/image/python_1/IDLE_run_shell.png"_}})

지난 시간에 python hello_world.py를 프롬프트 창에 입력해서 나왔던 것과 동일한 결과를 앞서 열렸던 IDLE 쉘 화면에서 보여줍니다. 이것이 IDE의 또 다른 중요 기능입니다. __작성한 코드에 대해 즉각적으로 테스트해보고 결과를 확인하는 것입니다.__ 이것으로 기초적인 IDE의 기능은 확인해 봤으니, 우리가 사용할 Atom IDE를 설치해 보겠습니다.

## Atom?
Atom은 GitHub에서 제작한 오픈소스 에디터입니다. 다양한 IDE 가운데 Atom을 선택하는 것은 다양한 플러그인을 통해 필요로 하는 기능을 추가하기 편리하고, 무엇보다도 무료이기 때문입니다.

[Atom IDE 다운로드](https://atom.io)

![Atom 설치]({{ "/assets/image/python_1/atom_download.png"}})

Atom IDE 홈페이지에서 프로그램을 다운로드 할 수 있습니다.  설치를 진행하면 다음과 같은 화면이 나옵니다.

![Atom 설치]({{ "/assets/image/python_1/atom_install.png"}})

설치가 무사히 끝나고 Atom을 실행해보면 몇 가지 화면이 나옵니다. 가장 먼저 보이는, 큰 화면은 Welcome Guide라는 기본적인 사용법 설명이고, 다른 하나의 화면은 앞으로도 이 Welcome Guide를 계속 볼 지를 묻는 화면입니다. 이건 취향에 따라 체크하거나 두시면 됩니다.

![Atom Welcome Guide]({{ "/assets/image/python_1/atom_welcom_guide.png"}})
![Atom Welcome Guide 내용]({{ "/assets/image/python_1/atom_welcom_guide_page.png"}})

탭을 살펴보시면 다른 화면이 하나 더 떠 있을텐데, 이건 Telemetry Consent, 곧 이용 데이터 조사에 대한 동의를 묻는 내용입니다. Atom을 개선하기 위해서, 익명화 된 사용자 정보를 제공하는데 동의하는지 여부를 묻는 것인데 거부해도 사용에 지장은 없습니다.

![Atom Telemtry Consent]({{ "/assets/image/python_1/atom_telemetry_consent.png"}})

또한, 우상단에는 URI 핸들러 동의 팝업이 나타납니다. 이것은 atom:// 으로 시작하는 모든 주소를 atom이 처리하도록 하겠냐는 질문입니다. 달리 atom URI를 쓸 일이 없으므로, 동의해 주면 됩니다.

![Atom URI handler]({{ "/assets/image/python_1/atom_handler.png"}})

## Atom Packages
앞서 이야기한 것과 같이, Atom은 다양한 부가기능을 사용할 수 있습니다. 이번에는 프로그램의 즉시 실행을 가능하게 해 주는 script와 파일 확장자별로 다양한 아이콘을 제공해 주는 Seti UI를 설치할 것입니다.

![Atom Settings]({{ "/assets/image/python_1/atom_package_install.png"}})

설치 과정은 무척 간단합니다. Atom에서 File-Settings 메뉴를 이용하거나, Ctrl+,를 입력해 설정 화면을 열어줍니다. 여기에서 Install 항목을 선택해 줍니다. 검색창에 script를 입력하고 검색하면 script 패키지가 나타납니다. Install 버튼을 눌러 설치해 줍니다. Script 패키지의 실행 단축키는 Ctrl+Shift+B입니다. 이것은 패키지 설정에서 바꿀 수 있습니다. 먼저 제대로 작동하는지 확인해 보겠습니다. 설치된 내용이 적용되어야 하므로, Atom을 종료하고 다시 시작해줍니다.

![Atom Script Run]({{ "/assets/image/python_1/atom_script.png"}})

이제 hello_world.py를 열고 단축키를 입력해주면 하단에 프로그램 실행 결과가 앞선 프롬프트와 IDLE와 마찬가지로 출력되는 것을 확인해 볼 수 있습니다.

![Atom Seti-UI]({{ "/assets/image/python_1/atom_seti_ui.png"}})

이번에는 Seti-UI를 설치해 보겠습니다. 앞서 사용했던 Install 항목으로 돌아가서 seti-UI를 검색하고 오른쪽의 theme 버튼을 클릭해 줍니다. Install 버튼을 클릭해 설치합니다. 설치가 완료되면 Settings의 Theme 메뉴에서 UI Theme를 Seti로 바꿔줍니다. seti-UI 테마도 적용이 완료됩니다.

![Atome Theme]({{ "/assets/image/python_1/atom_theme.png"}})
Settings 화면에서 Theme를 선택합니다. UI Theme를 Seti로 바꿔줍니다.

![Atom Seti Theme]({{ "/assets/image/python_1/atom_seti_applied.png"}})

새로운 테마가 잘 적용된 것을 확인할 수 있습니다.
