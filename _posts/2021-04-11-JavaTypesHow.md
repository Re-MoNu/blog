---
title: 자바 변수란?
categories: [dev]
comments: true
---
자바나 다른 프로그래밍 언어에서 변수란,    
대충 **변하는 수**라고 생각을 하면 쉽다. 예를 들어 변수 **a**가 **정수**일때는 **a**에 **1**이나 **3**이나 **1972**같은 값을 넣어줄수도 있다.   
하지만 자바는 파이썬과는 달리 선언하는데 특정 방법이 있다. 양식은   
```java
[변수타입] (이름);
```
으로 선언한다.   
    
예를 들어서 *char*타입으로 **c**라는 변수를 선언할때
```java
char c;
```
을 한다. 또한 선언과 동시에 할당을 시켜줄수도 있다.
예를 들어:
```java
int a = 21; //int 타입인 a를 선언하여 21을 할당
```
# 변수타입
- - -    
변수타입은 자바에서 크게 8가지가 있다.   

## 정수   
정수는 선언할때 크기에 따라 크게 4개로 나뉘어진다.
- - -   
### int   
*int*는 *intiger*의 약자이며 제일 기본적인 정수 저장 변수다.   
범위는 최대 **21억**으로 일반 용도로는 넉넉하다.   
### short   
*short*는 정수 변수 중에서는 2번째로 제일 작다.     
최대 **10000**까지 밖에 저장을 못하며, 생각나는 용도는 저장공간 절약 밖에 없다.   
### long   
정수 변수 중에서 제일 큰 값을 저장할 수 있다.      
범위는 **9,223,372,036,854,775,807**(알아서 읽으셈)이다.   
    
### Byte
*byte*는 **-128**에서 **127**까지 밖에 저장못하는 제일 작은 정수 변수타입이다.   
크기는 **4-byte**를 차지하는 *int*와는 다르게 **8-bit**로 자동지정이 된다.
## 문자   
문자는 크게 2개로 나뉘어진다.   
- - -   
### char     
문자 **하나**를 저장할때 쓰이며, 배열로 만들면 문자열 저장이 가능하다.   
### string   
보통 더 긴 단어나 문장을 저장할때 쓰인다, 다행이도 **C**와는 달리 따로 파일 불러올 필요가 없다.   
## 실수
- - -
실수는 보통 유리수 중에서 정수가 아닌 유리수를 저장할 때 사용된다.   
*double*과 *float*가 있는데 눈에 보이는 차이는 크게없다.   

둘의 차이점은 *float*는 소수점 밑 **6자리**까지 저장이 되며 *double*은 소수점 밑 **15자리**까지 저장된다.   
# 명명규칙
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
# 형변환
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

다 적으면 너무 많지만 대부분 형식은
```java
a = 변수타입.valueOf(strNum); //String 타입인 strNum을 "변수타입"으로 변환
```
이거나
```java
a = (변수타입)DoublNum //double 타입인 DoublNum을 "변수타입"으로 변환
```
일때가 많다.