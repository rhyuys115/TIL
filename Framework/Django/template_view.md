# Template & View

<br>

## 1. 프로젝트 생성

- 프로젝트 이름으로 Python 또는 Django에서 사용하는 키워드는 사용하지 않는다.

  ```bash
  $ django-admin startproject mysite
  ```

- 위의 명령을 통해 다음과 같은 구조로 파일들이 형성된다.

<img src="template_view.assets/startproject 구조.png" alt="startproject 구조" style="zoom:50%;" />

- mysite 디렉토리에서 다음 명령어를 통해 서버를 동작시킬 수 있다.

  ```bash
  $ python manage.py runserver
  ```


<br>

## 2. 앱 생성

- manage.py가 존재하는 디렉토리에서 다음 명령어로 앱을 생성할 수 있다.

  ```bash
  $ python manage.py startapp polls
  ```

- 생성된 파일 구조는 다음과 같다.

  <img src="template_view.assets/apps 구조.png" alt="apps 구조" style="zoom:50%;" />

- app 이름으로는 복수형을 사용한다.

- app을 생성하고 난 이후에 앱을 등록해준다.

  ```python
  from pathlib import Path
  
  # ------------중략------------ #
  INSTALLED_APPS = [
      'polls', # 생성 후 등록한 앱
      'django.contrib.admin',
      'django.contrib.auth',
      'django.contrib.contenttypes',
      'django.contrib.sessions',
      'django.contrib.messages',
      'django.contrib.staticfiles',
  ]
  
  ```

  > `mysite/settings.py`

<br>

## 3. URL 경로 생성

