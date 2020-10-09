---
title: 파이썬 기초 강습 0 - 파이썬 설치
date: 20-10-09 23:00:00
categories: productivity
published: True
---
컴퓨터와 관련된 일을 해 본 경험이 없는 분들을 대상으로 한 기초적인 파이썬 입문 가이드입니다.
Windows 10을 기준으로 해서 파이썬을 배우는 데 필요한 내용들을 정리해보겠습니다.
이번 준비 강좌에서는 파이썬을 설치하는 법을 설명합니다.

## Python?
프로그래밍 언어의 일종입니다. 자세한 내용은 다음 링크를 참조하세요 [링크](https://ko.wikipedia.org/wiki/%ED%8C%8C%EC%9D%B4%EC%8D%AC)

파이썬을 설치하기 위해서는 다음 링크에서 다운받으세요. [파이썬 다운로드](https://www.python.org/ftp/python/3.9.0/python-3.9.0-amd64.exe)

![파이썬 홈페이지]({{ "/assets/image/python_0/python.png"}})

![파이썬 다운로드]({{ "/assets/image/python_0/python_download.png"}})

다운로드한 프로그램을 실행하면 파이썬의 설치가 진행됩니다. 첫 화면에서 PATH 추가 여부를 물어보는데, 이를 체크하지 않으면 프롬프트 창에서 파이썬을 직접 실행할 수 없게 됩니다. 반드시 체크해주세요.
![파이썬 PATH 설정]({{ "/assets/image/python_0/python_path.png"}})

설치가 완료되었을 때 path length limit을 해제하는 옵션이 있는데, 이것 역시 체크해줍니다. 개발한 프로그램을 여러 PC에서 범용적으로 사용하기 위해서는 꺼주는 것도 좋은 방법이지만, 취미 수준에서의 로컬 개발에서는 고려할 필요 없는 부분입니다.
![파이썬 경로 길이 제한 해제]({{ "/assets/image/python_0/python_max_length.png"}})

## 개발의 첫 걸음, Hello, world!
개발에서의 첫 예제로 Hello, world!를 작성해 보겠습니다.

![메모장 Hello, world!]({{ "/assets/image/python_0/notepad.png"}})

먼저 메모장을 열고, print("Hello, world!")를 입력합니다. 이후 저장을 해 줍니다.

![메모장 Hello, world!]({{ "/assets/image/python_0/notepad_hello_world.png"}})

바탕화면으로 저장 경로를 설정한 후 hello_world.py로 파일명을 바꾸고,

![메모장 Hello, world!]({{ "/assets/image/python_0/notepad_save.png"}})

파일 형식 역시 모든 파일 (.*)로 바꿔줍니다.

이로써 우리는 첫 번째 예제인 Hello, world!를 완성했습니다.
그러면 그 결과물은 어디서 확인할 수 있을까요? 파이썬을 설치하는 과정에서 .py 형식의 파일은 모두 파이썬으로 연결되었으므로 파일을 더블클릭만 해도 실행이 됩니다. 하지만 실제로 더블클릭을 해 보면, 검은 창이 잠깐 나타났다가 사라질 뿐입니다.
이것은, 실행을 끝낸 프로그램이 종료되기 때문입니다. 결과를 확인하기 위해서는 파일을 프롬프트 창에서 열어줘야 합니다. 윈도우+R키를 눌러 실행창을 열고, cmd를 입력해주면 프롬프트 창이 열립니다.
![프롬프트창]({{ "/assets/image/python_0/prompt.png"}})
먼저, 만들어 준 파일이 있는 위치로 이동해 보겠습니다. 기본적으로 cmd를 실행하면 사용자 폴더로 진입하게 됩니다. C:\Users\[사용자 이름] 형식이 되고, 이는 프롬프트 창의 커서 앞에 표시되는 것으로도 확인할 수 있습니다.
앞서서 파이썬 코드를 저장해 준 바탕화면은 ``\``C:\Users\[사용자 이름]\Desktop으로 접근할 수 있습니다. 프롬프트창에 dir을 입력하면, 현재 있는 디렉토리의 파일과 폴더를 확인할 수 있습니다.
![dir 명령어]({{ "/assets/image/python_0/prompt_dir.png"}})

Desktop 폴더가 있는 것을 확인할 수 있습니다. 디렉토리를 바꾸기 위해서는 cd 명령어를 사용합니다. cd Desktop을 입력하면, 디렉토리가 바뀌는 것을 확인할 수 있습니다.
![cd 명령어]({{ "/assets/image/python_0/prompt_cd.png"}})

파이썬에서 코드를 실행하기 위해서는 'python으로 해당 파일을 열어라'는 명령을 컴퓨터에 전달해야 합니다. 그를 위해서는 python을 앞에 붙여주면 됩니다. python hello_world.py를 입력해주면, 작성한 코드 그대로 Hello, world!를 프롬프트창에 출력한 것을 확인해 볼 수 있습니다.
![Hello, world! 실행]({{ "/assets/image/python_0/prompt_hello_world.png"}})

이제 파이썬 코드를 작성할 수 있게 되었지만, 알아야 할 것도 많고 무엇보다 불편합니다. 메모장으로 프로그램을 작성하는 건 보통 생각하는 프로그래밍과도 많이 다른 것 같구요. 바로 그래서 IDE를 사용하게 됩니다. 다음 편에서 Atom IDE 설치를 진행해 보겠습니다.
