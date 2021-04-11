---
title: 자바에서 출력
categories: [Dev]
comments: true
---
당연하게도 프로그래밍에서 제일 기초적이자 제일 **중요한** 요소 중 하나가 출력이다
출력에도 여러가지 종류가 있지만, 제일 기초적인 출력문 두개는 print와 println이다.   

## print
---
**print**는 말그대로 "출력"이라는 뜻으로 안쪽에 쓰인 문자를 출력한다
예시:
```java
package asdf20210221;

public class asdf02 {
    public static void main(String[] args) {

        System.out.print("Lorem Ipsum"); //괄호 안에 있는 글을 출력

    }
}
```
실행을 하면 실행 결과가 이렇게 나온다.   
    
    Lorem Ipsum   

하지만 여기에는 문제가 있다.   
만약 여러줄을 출력할시에 줄 바꿈이 안된다.   

이는 뒤에 ```\n```을 추가하여 해결할 수 있지만, 다른 해결책도 있다.   

## println
---
println은 사실상 print랑 같지만 ```\n```없이 출력이 끝나면 자동으로 줄바꿈을 한다.   
예시:   
```java
package asdf20210221;

public class asdf02 {
    public static void main(String[] args) {

        System.out.println("Lorem Ipsum");
        System.out.println("dolor sit amet,");
        System.out.println("consectetur adipiscing elit");

    }
}
```
실행 결과는 다음과 같다.   

    Lorem Ipsum
    dolor sit amet,
    consectetur adipiscing elit

이렇게 자동으로 줄바꿈이 되어서 유용하다.
