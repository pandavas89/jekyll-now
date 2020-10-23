---
title: 파이썬 기초 강습 2 - 조건문과 반복문
date: 20-10-24 07:00:00
categories: python
published: False
---

우리는 왜 프로그래밍을 할까요? 어떤 대답이든 정답일 수 있겠지만, 가장 근본적인 부분에서 프로그래밍은 사람이 할 일을 컴퓨터가 대신 하도록 만드는 것이라고 생각합니다. 그리고 컴퓨터가 대신할 수 있는 일이라는 것은 결국 반복적인 작업이죠. 바로 그래서 우리는 반복문이 필요합니다.

가장 먼저 살펴 볼 반복문은 `for`입니다. 나열할 수 있는 대상에 대해, 그 수 만큼 반복하는 코드입니다. 이렇게 설명해도 복잡할테니, 예제 코드를 바로 볼까요?

```python
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
```
무슨 일이 일어난건지 이해하셨나요? "Hello, world!"라는 문자열 안의 모든 문자를 대상으로 해서 `print` 함수를 사용해주었습니다. 문자열 외에도 리스트와 딕셔너리 자료형에 대해 같은 방식으로 사용할 수 있습니다. 또한, 별도의 리스트가 아니라 정해진 수만큼 반복시킬 수도 있습니다.

```python
for i in range(10):
  print("Hello, world!")
```
이 코드를 통해 같은 동작인 `print("Hello, world!")`를 10번 반복시켰습니다. 그렇다면 기존의 echo 코드를 조금 바꿔볼까요?

```python
def echo(in_string):
  print(in_string)

for i in range(10):
  in_text = input("메아리 칠 문장을 입력하세요")
  echo(in_text)
```
이제 10번을 반복해서 메아리치게 할 수 있게 되었습니다. 더 많거나 적은 횟수를 원한다면 `range(10)`안의 숫자를 바꿔주면 됩니다. 하지만, 여전히 조금 아쉬운 부분이 있습니다. __아주 많이__ 할 수는 있어도, __무한히 많이__ 할 수는 없습니다. 그래서 이번에 살펴볼 반복문은 `while`입니다. while은 뒤에 오는 식이 참인 동안 while문 안의 코드를 반복 수행합니다. 비로소 질릴 때 까지 얼마든지 반복시킬 수 있게 된 것이죠.

```python
def echo(in_string):
    print(in_string)

while True:
    in_string = input("메아리 칠 문장을 입력하세요 : ")
    echo()
```

이제는 정말 메아리처럼, 입력을 해 주는 한 언제까지나 되풀이할 수 있게 됐습니다. 하지만 끝내는 방법을 모르겠네요. 콘솔에서 진행되고 있는 프로그램을 중단하는 단축키는 `Ctrl+C`입니다. 일단은 이 방법으로 프로그램을 종료하겠습니다. 그렇다면, 미리 약속된 특정한 단어나 문장을 입력했을 때 끝내도록 하면 좋겠습니다. 이러한 조건부 동작을 위해 조건문이 필요합니다.

## 조건문
```python
def echo(in_string):
    print(in_string)

while True:
    in_string = input("메아리 칠 문장을 입력하세요 : ")
    if (in_string == "끝"):
        break
    else:
        echo()
```

새롭게 추가된 코드를 조금 들여다 볼까요? `if (in_string == "끝"):`에서 `==`는 앞의 것과 뒤의 것이 같은지 비교한다는 의미입니다. 이 경우엔, 입력받은 값인 `in_string`이 `"끝"`이라는 문자열인지 확인한다는 의미입니다. `if`구문에 속하는 코드는 조건문이 참일 때, 수행됩니다. 즉 입력받은 값이 "끝"일 때, `break`를 한다는 얘기입니다. `break`는 반복문을 강제로 끝내는 명령어입니다. 그 다음 줄인 `else`는, 앞선 같은 수준의 조건문이 모두 거짓일 때 수행하겠다는 선언입니다. 지금은 조건문이 `if (in_string == "끝")` 밖에 없었으니, "끝"이 아닌 모든 입력값에 대해서 `echo(in_string)`을 수행한다는 뜻입니다. 이로써 "끝"을 입력하기 전에는 무한히 반복되는 메아리 프로그램을 만들 수 있었습니다.

그럼 지금까지 배운 내용을 바탕으로 해서 간단한 게임을 만들어 보겠습니다. 야구 게임을 만들겁니다. 숫자에 중복이 없는 임의의 네자리 숫자를 맞추는 게임이죠. 필요한 것을 정리해 볼까요?

- 정해진 정답값(숫자로만 구성된 문자열)
- 입력값
- 정답값과 입력값의 비교
- 결과 출력
- 위 과정의 반복

```python
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
```
