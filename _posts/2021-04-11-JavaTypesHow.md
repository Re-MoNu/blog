---
title: 자바 변수란?
categories: [Dev]
comments: true
---
자바나 다른 프로그래밍 언어에서 변수란,    
대충 **변하는 수**라고 생각을 하면 쉽다. 예를 들어 변수 **a**가 **정수**일때는 **a**에 **1**이나 **3**이나 **1972**같은 값을 넣어줄수도 있다.   
하지만 자바는 파이썬과는 달리 선언하는데 특정 방법이 있다. 양식은   
```java
[변수타입] (이름);
```
으로 선언한다. 변수타입의 종류들은 [여기서](https://re-monu.github.io/blog/2021-02/JavaTypes) 확인할 수 있다.   
## 명명규칙
- - -   
명명규칙은 변수를 선언하는 과정에서 이름을 정하는 규칙을 말한다, 이 규칙들은 어기면 컴파일 에러가 난다.      
1. 예약어 금지   
int나 char, if등 이미 정해진 것들은 불가능하다.   

2. 숫자로 시작하면 안된다   
    ```
    int 2a;
    ```
    는 불가 하지만   
    ```   
    int a2;
    ```
    같이 숫자로 끝나는 것은 가능하다.   

3. 특수기호는 '_'와 '$'만   
왠지는 모르겠지만, 이 2개만 가능하다.
## 형변환
- - -
가끔씩 **string**같은 문자로 받은 숫자를 **정수** 타입으로 변환시켜서 사용을 해야할때가 있다.   
이는 타입마다 다르지만, 형식은 다 비슷하다.   
1. **string**을 **int**로   
```java
package wow;
public class test {
    public static void main(String[] args) {
        String s_num = "10";

        int i_num = Integer.parseInt(s_num); //1번방식
        int i_num2 = Integer.valueOf(s_num); //2번방식
    }
}
```
2. **string**을 **double** 또는 **float**로
```java
package wow;
public class test {
    public static void main(String[] args) {
        String s_num = "10";

        double d_num = Double.valueOf(s_num); //Double
        float f_num = Float.valueOf(s_num); //Float
    }
}
```
3. **int**를 **float** 또는 **double**로
```java
package wow;
public class test {
    public static void main(String[] args) {
        int i_num = 10;
	
        double d_num = (double)i_num; //Double
        float f_num = (float)i_num; //Float
    }
}
```

더 적고싶지만 매우 피곤하기 때문에 그만 적고 가야지