---
title: 변수를 상수로
categories: [tips]
comments: true
---

보통은 프로그래밍을 할때 변수 안에 저장되는 값이 많이 변경이 되지만, 어떨때는 변경할 필요가 없거나 변경을 하면 안될수도있다.   
이럴때는 선언을 할때 상수로 선언을 해주면 된다.   
### 상수란, 
변경되지 않는 수로 한번지정을 해주면 그 값이 영원하다.
## 상수 선언 방법
**c**와는 다르게
 자바에서는 **상수 선언**이 일반 **변수 선언**과 사실상 같다. 그냥 변수타입 뒤에 "final"을 붙혀주면 된다.   
예시:
```java
final int num = 3;
```
이렇게 하면 *num*은 영원히 3으로 고정이 된다.   
   
   혹시 궁금하다면 **c**는 상수를 다음과 같이 선언한다.
```c
#define num 3; //이걸 헤더파일 불러오는 곳과 같은 곳에서 선언
```