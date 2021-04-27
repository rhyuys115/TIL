# django_model

## Model

> 웹 어플리케이션의 데이터를 구조화하고 조작하기 위한 도구

**개념**

- 모델은 단일한 데이터에 대한 정보를 가짐
- 일반적으로 각각의 모델은 하나의 데이터베이스 테이블과 매핑
- 모델은 부가적인 메타데이터를 가진 DB의 구조를 의미

<br>

## Database

> 체계화된 데이터의 모임(집합)

**기본 구조**

`쿼리(Query)`

- 데이터를 조회하기 위한 명령어
- 테이블형 자료구조에서 조건에 맞는 데이터를 추출하거나 조작하는 명령어

`스키마(Schema) `

- 데이터베이스에서 자료의 구조, 표현 방법, 관계 등을 정의한 구조
- 데이터베이스 관리 시스템(DBMS)이 주어진 설정에 따라 데이터베이스 스키마를 생성하며, 데이터베이스 사용자가 자료를 저장, 조회, 삭제, 변경할 때 DBMS는 자신이 ㅅ ㅐㅇ성한 데이터 베이스 스키마를 참조하여 명령을 수행

`테이블(Table)`

- 필드(field): 속성, 컬럼(Column)
  - 모델 안에 정의한 클래스에서  클래스 변수가 필드가 됨
- 레코드(record): 튜플, 행(Row)
  - 우리가 ORM을 통해 해당하는 필드에 넣은 데이터(값)

<br>

## ORM

> 객체-관계 매핑

**개념**

- 객체 지향 프로그래밍 언어를 사용하여 호환되지 않는 유형의 시스템간에(ex.Django-SQL)데이터를 변환하는 프로그래밍 기술
- DB를 객체(object)로 조작하기 위해 사용!! 

<br>

**장점**

- SQL을 몰라도 DB 연동이 가능하다.(SQL 문법을 몰라도 쿼리 조작 가능)
- SQL의 절자척인 접근이 아닌 객체 지향적인 접근으로 인해 생산성이 증가한다.
- ORM은 독립적으로 작성되어 있고, 해당 객체들을 재활용할 수 있다. 때문에 모델이서 가공된 데이터를 컨트롤러(django-view)에 의해 뷰(django-template)와 합쳐지는 형태로 디자인 패턴을 견고하게 만들기 유리

**단점**

- ORM 만으로 완전한 서비스를 구현하기 어려운 경우가 있다.
- 프로젝트의 복잡성이 커질 경우 설계 난이도가 상승할 수 있다.

<br>

## Migrations

> django가 모델에 생긴 변화(필드를 추가, 모델 삭제 등)을 반영하는 방법

<br>

`makemigrations`

- 모델을 변경에 기반한 새로운 migration(설계도 - 데이터베이스 스키마를 위한 버전관리 시스템) 만들 때 사용

- 모델을 활성화 하기 전에 DB 설계도(마이그레이션) 작성

  ```shell
  $ python manage.py makemigrations
  ```

- `0001_initial.py` 생성 확인

<br>

`migrate`

- 설계도를 실제 DB에 반영하는 과정

- `migrate`은 `makemigrations`로 만든 설계도를 실제 DB에 반영한다.

- 모델에서의 변경 사항들과 DB의 스키마가 동기화를 이룬다.

  ```shell
  $ python manage.py migrate
  ```

<br>

`sqlmigrate`

- 해당 migrations 설계도가 SQL 문으로 어떻게 해석되어서 동작할지 미리 확인할 수 있다.

  ```shell
  $ python manage.py sqlmigrate app_name 0001
  ```

<br>

`showmigrations`

- migrations 설계도들이 migrate 됐는지 안됐는지 여부를 확인 할 수 있다.

  ```shell
  $ python manage.py showmigrations
  ```

  