---
title: 파이썬 기초 강습 3 - 패키지 사용
date: 20-10-24 23:00:00
categories: python
published: True
---

지금까지 배운 것으로 필요한 프로그램을 만들 수 있게 되었습니다. 하지만, 이미 다른 사람들이 편하게 쓸 수 있도록 만들어 놓은 프로그램을 활용할 수 있다면 더 쉽고 빠르게 프로그램을 만들 수 있을 것입니다. 이번에는 세 가지 서로 다른 패키지를 통해, 지난 시간에 만든 야구 게임을 한 단계 더 개선해 보겠습니다.

## 패키지
패키지란 누군가가 작성한 프로그램의 집합입니다. 이렇게 작성된 패키지는 배포되어 누구나 사용할 수 있도록 만들 수 있습니다. 파이썬의 경우, pypi(Python Package Index)를 통해 이러한 패키지 관리를 진행합니다. 파이썬을 설치할 때 함께 설치되기 때문에, 프롬프트 창에서 pip를 입력하는 것으로 설치되었는지를 확인할 수 있습니다.

## 기본 라이브러리
가장 먼저, python에 기본적으로 내장된 패키지 중 하나인 `random`을 사용해보겠습니다. 지난 시간의 야구 게임을 혼자서도 즐길 수 있도록, 자동으로 맞춰야 할 숫자를 생성해주는 것인데요. `random` 패키지에는 임의의 정수를 생성하는 함수인 `randint`가 있습니다. 파라미터로 최소값과 최대값을 주면, 그 범위 내의 임의의 정수를 줍니다. 이를 적용해 새롭게 프로그래밍을 해 봅시다.
<details>
  <summary>baseball.py 코드</summary>

~~~python
from random import randint

def check_validity(target_str, init_mode=False):
  if !(target_str.isdigit()):
    if !(init_mode):
      print("입력값이 숫자가 아닙니다")
    return False
  elif len(target_str) != 4:
    if !(init_mode):
      print("입력한 숫자가 네 개가 아닙니다")
    return False
  else:
    for i in range(3):
      for j in range(i+1, 4):
        if (target_str[i] == target_str[j]):
          if !(init_mode):
            print("중복되는 숫자가 있습니다")
          return False

def baseball(goal):
  for inning in range(9):
    ball = 0
    strike = 0
    print("%d회 공격" %(inning+1))
    while True:
      guess = input("입력해주세요 : ")
      if (check_validity):
        break
    for index in range(4):
      letter = guess[index]
        if (letter in answer):
            if (letter == answer[index]):
                strike += 1
            else:
                ball += 1
    if (strike > 3):
        print("You win!")
    else:
        print("%dB%dS" %(ball, strike))

while True:
  while True:
    answer = randint(1000, 9999)
    if check_validity(answer, True):
      break
  if (answer == "끝"):
    break
  print('\n'*40)
  baseball(answer)
~~~
</details>
임의의 숫자를 생성하고, 나아가서 이미 만들었던 `check_validity`함수를 이용해서 자동적으로 임의생성된 정수가 조건에 맞는지 확인합니다. 이러한 자동생성 과정에서는 check_validity의 출력 기능이 필요하지 않기 때문에, 두 번째 파라미터를 추가해 사용자에 의한 입력일 때만 작동하도록 만들었습니다. 이제, GUI를 통해 윈도우에서 사용할 수 있는 프로그램을 만들어 보겠습니다.

## pip를 이용한 패키지 설치
GUI 생성을 위해 PyQt5 패키지를 설치할 것입니다. 이것은 폭넓게 사용되는 UI 프레임워크인 Qt의 파이썬 버전입니다. 패키지 설치는 무척 간단합니다.

`pip install pyqt5`

본래는 이 화면을 구성할 수 있는 패키지인 `pyqt5-tools`도 설치 가능해야 하지만, 아직까지 파이썬의 최신 버전을 지원하지 않고 있기 때문에 직접 설치해줘야 합니다.

![Qt Designer 다운로드](https://build-system.fman.io/qt-designer-download
