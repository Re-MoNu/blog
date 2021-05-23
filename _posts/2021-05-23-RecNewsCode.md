---
title: 추천 기사 코드
categories: [dev]
comments: true
---
EA
```java
package RecommendedNews;
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        news sports = new news();
        news viral = new news();
        news political = new news();
        news gaming = new news();
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter 10 sports news titles");
        sports.Add();

        System.out.println("Enter 10 viral news titles");
        viral.Add();

        System.out.println("Enter 10 political news titles");
        political.Add();

        System.out.println("Enter 10 Gaming news titles");
        gaming.Add();

        System.out.println("Now enter 2 things that you're interested in (Enter the number)");
        System.out.println("1. Sports\n2. Viral posts\n3. Politics\n4. Gaming");

        int interest1 = sc.nextInt();
        int interest2 = sc.nextInt();

        switch(interest1){
            case 1 -> {
                String temp=sports.list[(int) (Math.random()*10)];
                System.out.println(temp);
                switch (interest2) {
                    default -> System.out.println("End of the List");
                    case 2 -> viral.Comp(temp);
                    case 3 -> political.Comp(temp);
                    case 4 -> gaming.Comp(temp);
                }
            }
            case 2 ->{
                String temp=viral.list[(int) (Math.random()*10)];
                System.out.println(temp);
                switch (interest2) {
                    default -> System.out.println("End of the List");
                    case 1 -> sports.Comp(temp);
                    case 3 -> political.Comp(temp);
                    case 4 -> gaming.Comp(temp);
                }
            }
            case 3 ->{
                String temp=political.list[(int) (Math.random()*10)];
                System.out.println(temp);
                switch (interest2) {
                    default -> System.out.println("End of the List");
                    case 2 -> viral.Comp(temp);
                    case 1 -> sports.Comp(temp);
                    case 4 -> gaming.Comp(temp);
                }
            }
            case 4 ->{
                String temp=gaming.list[(int) (Math.random()*10)];
                System.out.println(temp);
                switch (interest2) {
                    default -> System.out.println("End of the List");
                    case 2 -> viral.Comp(temp);
                    case 3 -> political.Comp(temp);
                    case 1 -> sports.Comp(temp);
                }
            }
        }
    }
}
class news{
    Scanner sc = new Scanner(System.in);
    String[] list = new String[10];
    public void Add(){
        for(int i=0;i<10;i++){
            String temp = sc.next();
            this.list[i] = temp;
        }
    }
    public void Comp(String name){
        for(int i=0;i<10;i++){
            if(list[i].equals(name)){
                System.out.println(list[i]);
                break;
            }
        }
    }
}

```
test inputs for the program
```
Sports1
Sports2
Sports3
Sports4
Sports5
Sports6
Sports7
SportsGaming
SportsPolitics
SportsViral

Viral1
Viral2
Viral3
Viral4
Viral5
Viral6
Viral7
SportsViral
ViralGaming
ViralPolitics

Politic1
Politic2
Politic3
Politic4
Politic5
Politic6
Politic7
SportsPolitic
ViralPolitic
PoliticGaming

Gaming1
Gaming2
Gaming3
Gaming4
Gaming5
Gaming6
Gaming7
SportsGaming
ViralGaming
PoliticGaming
```