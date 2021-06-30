---
title: 파이썬 기초 강습 2 - 조건문과 반복문
date: 20-10-24 07:00:00
categories: python
published: True
---

우리는 왜 프로그래밍을 할까요? 어떤 대답이든 정답일 수 있겠지만, 가장 근본적인 부분에서 프로그래밍은 사람이 할 일을 컴퓨터가 대신 하도록 만드는 것이라고 생각합니다. 그리고 컴퓨터가 대신할 수 있는 일이라는 것은 결국 반복적인 작업이죠. 바로 그래서 우리는 반복문이 필요합니다.

가장 먼저 살펴 볼 반복문은 `for`입니다. 나열할 수 있는 대상에 대해, 그 수 만큼 반복하는 코드입니다. 이렇게 설명해도 복잡할테니, 예제 코드를 바로 볼까요?

<details>
  <summary markdown='span'>echo.py 코드</summary>
~~~python
def echo(in_string):
  print(in_string)

for letter in "Hello, world!":
  print(letter)

>>>
H
e
l
l
o
,

 w
 o
 r
 l
 d
 !
~~~
</details>
무슨 일이 일어난건지 이해하셨나요? "Hello, world!"라는 문자열 안의 모든 문자를 대상으로 해서 `print` 함수를 사용해주었습니다. 문자열 외에도 리스트와 딕셔너리 자료형에 대해 같은 방식으로 사용할 수 있습니다. 또한, 별도의 리스트가 아니라 정해진 수만큼 반복시킬 수도 있습니다.

~~~python
for i in range(10):
  print("Hello, world!")
~~~
이 코드를 통해 같은 동작인 `print("Hello, world!")`를 10번 반복시켰습니다. 그렇다면 기존의 echo 코드를 조금 바꿔볼까요?

~~~python
def echo(in_string):
  print(in_string)

for i in range(10):
  in_text = input("메아리 칠 문장을 입력하세요")
  echo(in_text)
~~~
이제 10번을 반복해서 메아리치게 할 수 있게 되었습니다. 더 많거나 적은 횟수를 원한다면 `range(10)`안의 숫자를 바꿔주면 됩니다. 하지만, 여전히 조금 아쉬운 부분이 있습니다. __아주 많이__ 할 수는 있어도, __무한히 많이__ 할 수는 없습니다. 그래서 이번에 살펴볼 반복문은 `while`입니다. while은 뒤에 오는 식이 참인 동안 while문 안의 코드를 반복 수행합니다. 비로소 질릴 때 까지 얼마든지 반복시킬 수 있게 된 것이죠.

~~~python
def echo(in_string):
    print(in_string)

while True:
    in_string = input("메아리 칠 문장을 입력하세요 : ")
    echo()
~~~

이제는 정말 메아리처럼, 입력을 해 주는 한 언제까지나 되풀이할 수 있게 됐습니다. 하지만 끝내는 방법을 모르겠네요. 콘솔에서 진행되고 있는 프로그램을 중단하는 단축키는 `Ctrl+C`입니다. 일단은 이 방법으로 프로그램을 종료하겠습니다. 그렇다면, 미리 약속된 특정한 단어나 문장을 입력했을 때 끝내도록 하면 좋겠습니다. 이러한 조건부 동작을 위해 조건문이 필요합니다.

## 조건문
~~~python
def echo(in_string):
    print(in_string)

while True:
    in_string = input("메아리 칠 문장을 입력하세요 : ")
    if (in_string == "끝"):
        break
    else:
        echo()
~~~

새롭게 추가된 코드를 조금 들여다 볼까요? `if (in_string == "끝"):`에서 `==`는 앞의 것과 뒤의 것이 같은지 비교한다는 의미입니다. 이 경우엔, 입력받은 값인 `in_string`이 `"끝"`이라는 문자열인지 확인한다는 의미입니다. `if`구문에 속하는 코드는 조건문이 참일 때, 수행됩니다. 즉 입력받은 값이 "끝"일 때, `break`를 한다는 얘기입니다. `break`는 반복문을 강제로 끝내는 명령어입니다. 그 다음 줄인 `else`는, 앞선 같은 수준의 조건문이 모두 거짓일 때 수행하겠다는 선언입니다. 지금은 조건문이 `if (in_string == "끝")` 밖에 없었으니, "끝"이 아닌 모든 입력값에 대해서 `echo(in_string)`을 수행한다는 뜻입니다. 이로써 "끝"을 입력하기 전에는 무한히 반복되는 메아리 프로그램을 만들 수 있었습니다.

그럼 지금까지 배운 내용을 바탕으로 해서 간단한 게임을 만들어 보겠습니다. 야구 게임을 만들겁니다. 숫자에 중복이 없는 임의의 네자리 숫자를 맞추는 게임이죠. 필요한 것을 정리해 볼까요?

- 정해진 정답값(숫자로만 구성된 문자열)
- 입력값
- 정답값과 입력값의 비교
- 결과 출력
- 위 과정의 반복

<details>
  <summary markdown='span'>
  baseball.py 코드
  </summary>
~~~python
def baseball(goal):
  for inning in range(9):
    ball = 0
    strike = 0
    print("%d회 공격" %inning+1)
    guess = input("입력해주세요 : ")
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

answer = "1357"
baseball(answer)
~~~

이로서 야구 게임을 만들었습니다. 하지만 아직 갈 길이 멉니다. 게임이 의도된 대로 네 자리의 겹치지 않는 숫자만을 입력한다면 좋겠지만, 얼마든지 잘못 입력할 가능성이 있고 그에 따라서 기회가 허비될 가능성이 있습니다. 생각해 볼 수 있는 입력값 오류의 경우는 총 세 가지입니다.

1. 입력값이 숫자가 아닐 때
2. 입력값의 길이가 4가 아닐 때
3. 입력값에 중복되는 수가 있을 때

이 세 가지 경우를 검사하는 함수를 만들어 보겠습니다.

~~~python
def check_validity(target_str):
  if !(target_str.isdigit()):
    print("입력값이 숫자가 아닙니다")
    return False
  elif len(target_str) != 4:
    print("입력한 숫자가 네 개가 아닙니다")
    return False
  else:
    for i in range(3):
      for j in range(i+1, 4):
        if (target_str[i] == target_str[j]):
          print("중복되는 숫자가 있습니다")
          return False

def baseball(goal):
  for inning in range(9):
    ball = 0
    strike = 0
    print("%d회 공격" %inning+1)
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

answer = "1357"
baseball(answer)
~~~
<details>



하지만, 이렇게 해서야 매번 정해진 숫자인 1357을 맞추는 게임이 되고 말겠지요. 일단은 2인용 게임이라는 가정 하에 한 사람은 숫자를 정하고 한 사람은 맞추는 방식으로 개선해보겠습니다. 더불어서, 앞서 배워 본 `while`과 `break`를 이용해 특정한 명령어를 입력하기 전까지 반복되는 프로그램으로 개선해 보겠습니다.

<details>
  <summary markdown='span'>
  baseball.py 코드
  </summary>
~~~python
def check_validity(target_str):
  if !(target_str.isdigit()):
    print("입력값이 숫자가 아닙니다")
    return False
  elif len(target_str) != 4:
    print("입력한 숫자가 네 개가 아닙니다")
    return False
  else:
    for i in range(3):
      for j in range(i+1, 4):
        if (target_str[i] == target_str[j]):
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
  answer = input("맞춰야 할 값을 입력해 주세요 : ")
  if (answer == "끝"):
    break
  print('\n'*40)
  baseball(answer)
~~~
<details>

이제 우리는 의도한 대로 작동하는 야구 게임을 작성하는 데 성공했습니다. 혼자서도 게임을 플레이 할 수 있도록 랜덤하게 숫자를 생성하는 기능이나, 화면을 지워서 원하는 UI를 표현하면 좋겠지만, 그를 위해서는 패키지를 불러오고 사용하는 방법을 익혀야 합니다. 다음 시간에 마무리하기로 합니다.
