---
title: 자바 클래스
categories: [dev]
comments: true
---
# 클래스 소개
---
클래스를 선언하는 것은 자기가 사용할 변수를 선언하는 것과 같다.   
다른말로 객체를 만들수 있는것이다.   
예를 들어:
```java
public class Info {

}
```
이는 매우 간단한 클래스다, **Info**라는 클래스에 아무것도 넣지않고 선언한것이다.
 이를 객체로 선언하려면
 ```java
 Info jack = new Info();
 ```
 ```new```는 객체등을 생성할때 쓰는 키워드다, 대표 사용예로 ```Scanner```가 있다.   
 이렇게하면 "jack"이라는 이름을 가진 객체를 만들수있다.         
 클래스를 실제 세계와 비교하면 다음과 같다.
 ![](https://shop3.daumcdn.net/thumb/R500x500/?fname=http%3A%2F%2Fshop3.daumcdn.net%2Fshophow%2Fp%2FH13017442772.jpg%3Fut%3D20210427124141)   
 여기서 틀은 **class**가 되고, 그걸로 만드는 타코야끼는 **객체**가 된다.
   
이것처럼 클래스 하나로 여러 객체를 만들수있다.
```java
Info jack = new Info();
Info amy = new Info();
Info iva = new Info();
```
# 객체 변수
---
당연히 위에 있는 코드처럼 클래스안에 아무것도 안넣으면 쓸모가 없다.   
마치 타코야끼 틀은 있지만 재료가 없는거와 같다.   
   
      
이래서 클래스안에 **객체 변수**라는 것을 선언할 수 있다.
```java
public class Info {
    String name;
}
```
이러면 "Info"라는 클래스안에 ```name```이라는 객체 변수를 ```String```으로 선언한 것이다.   
하지만 객체 변수도 있기만하면 쓸모가 없다. 이를 쓸수있어야 한다.   
불러오는 방법은 매우 간단하다.
```
객체.객체변수
```
와 같이 불러온다.   
예를 들어
```java
public class Info {
        String name;

    public static void main(String[] args) {
        Info jack = new Info();
        System.out.println(jack.name);
    }
}
```
물론 이 상태로 출력을 하면 ```null```이 출력된다.
   
그 이유는 "name"이라는 객체 변수는 존재하나 안에 값이 없기 때문이다.
# 메소드
---
지금까지 클래스와 객체 선언, 객체 변수 선언에 대하여 배웠는데   
스캐너 같은 클래스를 보면 여러 기능들이 있다.   
   
예를 들어:
```java
int a = sc.nextInt();
double b = sc.nextDouble();
...
```
등 여러가지가 있다.     
이렇게 특정 값을 입력하거나 불러오는 기능들을 ```메소드```라고 한다.
   
이런 메소드들은 클래스 안쪽에서 선언이 가능하다.
```java
public class info(){
    String name;

    public void setName(String name) {
        this.name = name;
    }

    public static void main(String[] args) {
        info first = new info();
        first.setName("jack");
        System.out.println(first.name);
    }
}
```
이렇게 "setName"이라는 메소드를 선언할 수 있다.   
이 메소드의 구조를 보면 일단
```java
public void setName(String name)
```
에서 괄호 안에 ```String name```이 있다는 사실을 확인할 수 있다.   
이는 사용을 할때 괄호로 ```String``` 타입의 무언가를 입력 받는다는 뜻이다.   
   

또한 그 밑에는 ```this.name = name;```이 있는데, 여기서 "this"는 "이 클래스의"라는 뜻을 가지고 있고 "this"가 붙어있지 않는 "name"은 메소드의 변수를 뜻한다.   
그래서 해석을 하면
```java
클래스에 있는 변수에다 방금 입력 받은 값을 집어 넣는다.
```
가 된다.   
    

또한 알아야 할것은 객체 변수값은 공유가 되지 않는다는것이다.   
그래서
```java
public class info(){
    String name;

    public void setName(String name) {
        this.name = name;
    }

    public static void main(String[] args) {
        info first = new info();
        first.setName("jack");
        
        System.out.println(first.name);


        info second = new info();
        second.setName("james");
        
        System.out.println(second.name);
        
    }
}
```
이렇게 각각 다른 객체에 다른 값을 넣어도 ```first.name```의 값은 "jack"이고   
```second.name```의 값은 "james"가 된다.