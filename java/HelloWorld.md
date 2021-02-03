# Hello World!

```java
public class HelloWorld{
    public static void main(String args[]) {
        System.outt.println("Hello World");
    }
}
```



1. `public class HelloWorld {}`

- public : 메소드의 접근제어자, public은 누구나 이 메소드에 접근할 수 있다는 의미

- class : 클래스 생성



2. `public static void main(String args[]) {}`

- static : 메소드에 static이 지정되어 있는 경우 이 메소드는 인스턴스 생성없이 실행 할 수 있음을 의미
- void : 메소드의 리턴값이 없음을 의미
- String : 문자열을 나타내는 자바의 자료형
- args[] : String 자료형에 대한 변수명으로 args 뒤에 []가 있으므로 한 개가 아닌 여러개의 값으로 이루어진 배열임을 의미



3. `System.out.println("Hello World");`

- 표준출력으로 데이터를 보내는 자바의 내장 메소드로 `println` 메소드로 들어오는 문자열 값을 화면에 출력한다.