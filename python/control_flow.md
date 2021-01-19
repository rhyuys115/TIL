# 제어문(Control Statement)

> 특정 상황에 따라 코드를 선택적으로 실행하거나 동일한 코드를 계속해서 실행해야하는 경우가 있다.이 경우, 코드 실행의 순차적인 흐름을 제어할 필요가 있는데 이 역할을 수행하는 것을 제어문이라고 한다. 제어문은 크게 **조건문**과 **반복문**으로 나눌 수 있다.



## 1 조건문(Conditional Statement)



### 1.1 `if`조건문의 구성

- 문법

```python
if <expression>:
    <코드 블럭>
else:
    <코드 블럭>
```

- `expression`에는 일반적으로 참/거짓에 대한 조건식이 들어간다.
- 조건이 참인 경우 `:`이후의 문장을 수행한다.
- 조건이 거짓인 경우 `else:`이후의 문장을 수행한다.
- `else`는 선택적이다.
- 조건문은 다른 조건문에 중첩될 수도 있다.



### 1.2 `elif`복수 조건

- 2개 이상의 조건을 활용할 경우 `elif <expression>:`을 활용한다.

```python
if <expression>:
    <코드 블럭>
elif <expression>:
    <코드 블럭>
else:
    <코드 블럭>
```

- `if` 와 같은 줄의 `<expression>`이 거짓인 경우 `elif` 뒤의 내용에 대해 조건 확인



### 1.3 조건 표현식(Conditional Expression)

- 활용법

```python
true_value if <조건식> else false_value
```

- 조건식의 값이 참이면 앞에 내용, 거짓이면 뒤에 내용



## 2. 반복문(Loop Statement)



### 2.1 `while`반복문

- 문법

```python
while <expression>:
    <코드 블럭>
```

- `while`문은 `<expression>`이 참(`True`)인 경우 반복적으로 코드를 실행한다.
- 종료조건을 설정하지 않으면 무한하게 반복된다.



### 2.2 `for`문

- 문법

```python
for <temp_var> in <iterable>:
    <코드 블럭>
```

- `for`문은 시퀀스(string, tuple, list, range)나 다른 순회가능한 객체(iterable)의 요소들을 순회한다.
- `enumerate()`: 인덱스(index)와 값(value)를 함께 활용 가능



### 2.3 반복제어(`break`, `continue`, `for-else`)



#### 2.3.1 `break`

```python
while <expression>:
    if <expression>:
        break
    <코드 블럭>
```

```python
for number in numbers:
    if <expression>:
        break
    <코드 블럭>
```

- `break`를 만나면 반복문을 종료한다.(`for`나 `while`문에서 빠져나간다)
- 하단에 있는 코드 블럭은 실행되지 않는다.



#### 2.3.2 `continue`

```python
while <expression>:
    if <expression>:
        continue
    <코드 블럭>
```

```python
for number in numbers:
    if <expression>:
        continue
    <코드 블럭>
```

- `continue`문은 continue 이후의 코드를 수행하지 않고 *다음 요소부터 계속하여 반복을 수행*한다.



#### 2.3.3 `for-else`

```python
for number in numbers:
    if <expression>:
        break
    <코드 블럭>
else:
    <코드 블럭>
```

- 끝까지 반복문을 실행한 이후에 실행된다.
  - 반복 가능한 객체의 소진(`for`의 경우) 혹은 조건이 거짓이 되어(`while`의 경우) 종료되면 실행
- 하지만 반복문이 **`break`문으로 종료될 때는 실행되지 않는다.**



