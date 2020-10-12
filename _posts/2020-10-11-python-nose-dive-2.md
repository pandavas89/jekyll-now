---
title: 파이썬 기초 강습 2 - 문자열 자료형과 함수
date: 20-10-11 00:00:00
categories: python
published: False
---

python으로 기초 중의 기초인 Hello, world!를 구현해 보았습니다. 이번에는 여기에서 한 걸음 더 나아가 보겠습니다. 먼저 Hello, world!에 사용된 자료형과 함수를 알아보겠습니다.

```
print("Hello, world!")
```

`"Hello, world!"` 라는 문자열 리터럴이 사용되었고, `print` 함수가 사용되었습니다. 먼저 문자열부터 살펴보겠습니다.

## 문자열(String)
가장 간략하게 얘기한다면, 종류를 막론하고 따옴표로 둘러싸인 모든 문자들은 문자열이 됩니다. 우리가 사용해 본 `"Hello, World!"` 뿐만 아니라 `"a"`, `"3.141592"`, `"!@#$"`와 같은 것도 전부 문자열이 됩니다. 이러한 문자열은 앞서 설명된 `print`함수를 통해 출력될 수 있습니다.

## 함수(function)
프로그래밍에서의 함수란 __미리 약속된 입력으로부터 약속된 출력을 만들어내는 기능__이라고 말할 수 있습니다. 이미 사용해 본 `print`의 경우에는 전달받은 값을 문자열로 바꿔 출력하는 함수입니다.
조금 더 강의가 진행되어서 GUI를 활용하게 되기 전까지는 `print` 함수가 우리의 프로그램 UI 구현에 있어서 주요한 역할을 할 것입니다. `print`에 대한 더 자세한 설명은 [링크]("https://docs.python.org/3/library/functions.html#print")를 참조하세요.
파이썬에서 기본적으로 제공하는 함수들이나 다른 사람이 만들어 둔 함수를 사용할 수도 있고, 우리가 직접 정의한 함수를 사용할 수도 있습니다. 그러면 함수를 정의해 보겠습니다. 기존의 `hello_world.py`코드를 조금 바꿔볼까요.

```
def hello_world():
    print("Hello, world!")

hello_world()

>>> Hello, world!
```

코드를 실행해 보면, 전과 동일하게 Hello, world!를 출력하는 프로그램입니다. 그러면 작성된 코드를 하나씩 살펴볼까요?

`def hello_world():`

새로운 함수인 hello_world를 정의했습니다. `def`는 새로운 함수를 정의할 때 사용하는 명령어입니다. 이후에 오는 것은 새로운 함수의 이름이 됩니다. `()`괄호 안에는 아무것도 없는데, 이는 이 함수가 어떤 입력값(인자라고도 부릅니다)도 받지 않기 때문입니다.

`    print("Hello, world!")`

원래의 `hello_world.py`코드와 같지만, 들여쓰기가 된 것을 볼 수 있습니다. 이것은 이 줄이 새로운 함수 `hello_world`의 코드이기 때문입니다. `def hello_world():`를 기준으로 해서, 들여쓰기가 이어지는 한 모든 코드는 함수 `hello_world`의 코드로 인식됩니다. 이것은 파이썬의 중요한 특징 가운데 하나로, 다른 언어와는 달리 들여쓰기가 강제되고 들여쓰기는 그 자체로 의미를 가집니다. 이에 따라 코드의 가시성이 좋아지는 장점이 있습니다.

`hello_world()`
새롭게 정의해 준 `hello_world`를 호출해 주었습니다. 파이썬에서 함수를 호출할 때에는 인자값을 주지 않더라도 반드시 뒤에 소괄호를 붙여줍니다. 이 부분을 생략하게 되면, `hello_world`함수를 정의하는 부분만 존재하게 되기 때문에 코드를 실행해도 어떤 결과도 나타나지 않습니다. 반대로 코드를 다음과 같이 바꾼다면, Hello, world!가 두 번 인쇄됩니다.

```
def hello_world():
    print("Hello, world!")

hello_world()
hello_world()

>>> Hello, world!
>>> Hello, world!
```

#echo 함수 만들어보기
함수와 문자열에 대해 이해했으니, 입력받은 값을 그대로 출력하는 echo 함수를 만들어보겠습니다.
```
def echo(in_string):
    print(in_string)

echo("Hello, world!")
echo("This is python echo function test.")

>>> Hello, world!
>>> This is python echo function test.
```

`in_string`이라는 인자를 받아, 그것을 콘솔에 출력하는 함수입니다. `echo()` 내부에 다양한 문자열을 집어넣어 정상작동하는지 테스트 해 봅시다.

하지만 미리 입력된 문구만 입력하면 메아리라는 느낌이 잘 들지 않는 만큼, 사용자의 입력값을 직접 받아서 되풀이하도록 조금 더 수정해 보겠습니다.

```
def echo():
    in_string = input("메아리 칠 문장을 입력해 주세요 : ")
    print(in_string)

echo()
>>> 메아리 칠 문장을 입력해 주세요 : 야호!
>>> 야호!
```

새롭게 `input()`함수가 사용되었습니다. 콘솔에서 사용자 입력값을 받아오는 함수입니다. `input`에 전달해 준 인자값은 문자열을 입력받을 때 출력되므로 안내 메시지의 역할을 합니다.
in_string에 input에서 입력받은 값을 할당하고, 인쇄하는 프로그램이 되었습니다.
