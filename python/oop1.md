# OOP 1



## 1 객체(Object)

> Python에서 모든 것은 객체(object)이다.
>
> 모든 객체는 타입(type), 속성(attribute),조작법(method)을 가진다.



객체(Object)의 특징

- 타입(type): 어떤 연산자(operator)와 조작(method)이 가능한가?
- 속성(attribute): 어떤 상태(데이터)를 가지는가?
- 조작법(method): 어떤 행위(함수)를 할 수 있는가?



### 1.1 타입(Type)과 인스턴스(Instance)



#### 1.1.1 타입(Type)

- 공통된 속성(attribute)과 조작법(method)를 가진 객체들의 분류
- ex) `list`, `str`, `dict`



#### 1.1.2 인스턴스(Instance)

- 특정 타입(type)의 실제 데이터 예시(instance)이다.
- 파이썬에서 모든 것은 객체이고, 모든 객체는 특정 타입의 인스턴스이다.
- ex) `a=10`,` b=20`일 때, `a`,`b`는 `int` 타입의 인스턴스



### 1.2  속성(Attribute)과 메서드(Method)



#### 1.2.1 속성(Attribute)

- 속성(attribute)은 객체(object)의 상태/데이터를 뜻한다.
- ex) `Class.attribute`



#### 1.2.2 메서드(Method)

- 특정 객체에 적용할 수 있는 행위를 뜻한다.
- ex) `Class.method()`



`dir(a)` 함수를 통해 a가 속한 타입의 객체가 할 수 있는 모든 속성과 메서드를 확인할 수 있다.



## 2 객체 지향 프로그래밍(Object-Oriented Programming)

> object가 중심이 되는 프로그래밍



프로그래밍 패러다임 : 절차 중심 vs Object 중심

Object 중심의 장점

- 코드의 직관성
- 활용의 용이성
- 변경의 유연성



## 3 클래스(Class)와 객체(Object)

> `type`: 공통 속성을 가진 객체들의 분류(class)
>
> `class`: 객체들의 분류(class)를 정의할 때 쓰이는 키워드



### 3.1 클래스(Class) 생성

- 클래서 생성은 `class` 키워드와 정의하고자 하는 `<클래스의 이름>`으로 가능하다.
- `<클래스의 이름>`은 PascalCase로 정의한다.
- 클래스 내부에는 데이터와 함수를 정의할 수 있고, 이때 데이터 중  속성(attribute) 정의된 함수는 메서드(method)로 불린다.

```python
class ClassName:
    statement
```



### 3.2 인스턴스(Instance) 생성

- 정의된 클래스(`class`)에 속하는 객체를 해당 클래스의 인스턴스(instance)라고 한다.
- `Person` 클래스의 인스턴스는 `Person()`을 호출함으로써 생성된다.
  - ex) `person1 = Person()`
- type() 함수를 통해 생성된 객체의 클래스를 확인할 수 있다.
- `person1`은 사용자가 정의한 `Person`이라는 데이터 타입의 인스턴스이다.



### 3.3 메서드(Method) 정의

- 정의

```python
class Person:
    # 클래스 내부에서 정의된 함수 => 메서드
    def talk(self):
        print('안녕')
    
    # 메서드도 함수이기 때문에 추가적인 이자를 받을 수 있다.
    def eat(self,food):
        print(f'냠냠 {food}')
```

- 호출

```python
person1 = Person()
person1.talk()
person1.eat('치킨')
```



#### 3.3.1 `self`

> 인스턴스 자신(self)

- Python에서 인스턴스 메서드는 호출 시 첫번째 인자로 인스턴스 자신이 전달되게 설계하였다.
- 보통 매개변수명으로 `self`를 첫번째 인자로 설정



#### 3.3.2 생성자(constructor) 메서드



#### 3.3.3 소멸자(destructor) 메서드



### 3.4 속성(Attribute) 정의



### 3.5 매직메서드



