1주차는 예전에 배웠던 자바를 기억해내기 위한 개념공부이다. 점프 투 자바와 김영한 강사님 인프런 자바입문 강의를 참고하였다.
___
이번 공부의 목적은 흐릿해진 기본 구문을 눈과 손에 익히고, 클래스와 메서드 패키지같은 개념을 명확히 하는 것이다.
___
![img.png](img.png) 
자바,인텔리제이의 컴파일 과정과 원리에 대해 알아보았다.
##### 패키지
비슷한 성격의 자바 클래스를 모아놓은 디렉토리, 즉 폴더로 생각하면 된다.클래스의 식별에 용이하다.
##### 클래스
연관된 변수와 메소드를 그룹화 한 것이다. 하나의 사물을 하나의 클래스로 설명할 수 있다.
##### 메소드
클래스의 기능을 의미하며, 수학에서 함수의 역할을 한다.<br/><br/>
더 세부적인 내용은 추후에 다루겠다.
___
##### 변수
변수에 대해선 자세히 정리하지 않고 주의할만한, 까먹을만한 것만 정리해두겠다.
실무에선 다른것들은 거의 사용하지 않고 int, long, boolean, double, string 만 사용한다고 생각해도 된다.<br/><br/>
또한 변수명명에 대한 규칙과 관례가 존재한다.
- 변수 이름은 숫자로 시작할 수 없다.
- 이름에는 공백이 들어갈 수 없다.
- 자바의 예약어를 변수 이름으로 사용할 수 없다.(int, class, public 등)
- 변수 이름에는 영문자, 숫자, $, _ 만 사용할 수 있다.
- 카멜케이스를 사용하는게 일반적. 소문자로 시작 후 다음 단어는 대문자로 시작(myAcoount)<br/><br/>
자바 언어에 대한 관례
- 클래스의 첫 글자는 대문자, 나머지는 모두 소문자 시작!
- - 클래스: Person,Detail
- - 변수를 포함한 나머지 : firstName, secondName
- 예외가 딱 두가지 있다.
- - 상수는 모두 대문자 사용하고 언더바로 구분(USER_LIMIT)
- - 패키지는 모두 소문자 사용. org.spring.boot

간단한 변수 퀴즈를 풀어보라고 한다.. (사실 이걸 풀어야하나 싶지만 그래도 풀겠다) 변수 사용하여 print하라는 요구다.
```
public class HelloJava {
    public static void main(String[] args) {
        int num1=3;
        int num2=4;
        System.out.println(num1+num2);
        System.out.println(num1*num2);
        System.out.println(num1-num2);
    }
}
```
변수1에 10,변수2에 20을 할당하고 그 합을 sum 변수에 저장 후 출력하라.
```
public class HelloJava {
    public static void main(String[] args) {
        int num1=10;
        int num2=20;
        int sum=num1+num2;
        System.out.println(sum);
    }
}
```
Long 타입의 변수 선언 후, 변수를 100억으로 초기화 하여 출력, boolean 타입의 변수 선언하고, true로 초기화하여 출력.
```
public class HelloJava {
    public static void main(String[] args) {
        long a=10000000000L;
        boolean b= true;
        System.out.println(a);
        System.out.println(b);
    }
}
```
___
##### 연산자
- 산술 연산자 : +,-,*,/,%(나머지 연산자)
- 증감 연산자 : ++,--
- 비교 연산자 : ==, !=, >, <, <=, >= (문자열 비교는 .equals())
- 논리 연산자 : &&(AND), ||(OR), !(NOT)
- 대입 연산자 : =, +=, -=, *=, /=, %=
- 삼항 연산자 : ? :

##### 문제
클래스 이름은 OperationEx1으로하고, num1,num2,num3 세 개의 int 변수 선언하고 10,20,30 으로 초기화. 세 변수 합 계산 후 sum이라는 int변수에 저장. 세 변수의 평균 계산 후, average라는 int변수에 저장. sum과 average 변수의 값 출력.
```
public class OperationEx1 {
    public static void main(String[] args){
        int num1=10;
        int num2=20;
        int num3=30;
        int sum=num1+num2+num3;
        int average=sum/3;
        System.out.println(sum);
        System.out.println(average);
    }
}
```
int형 변수 score선언. Score가 80점 이상이고, 100점 이하면 true, 아니면 false 출력.
```commandline
public class OperationEx2 {
    public static void main(String[] args) {
        int score=80;
        boolean result=score>=80 && score<=100;
        System.out.println(result);
    }
}
```
___
##### if문 
은 딱히 정리할게 없어보인다.
##### swtich문
```
public class Switch {
    Switch( 조건식 ) {
        case value1:
            //실행코드
            break;
        default :
            //조건 어떤경우에도 해당하지 않을때.
    }
}
```
삼항 연산자는 자바에서 유일하게 항이 3개이다.
(조건) ? 참_표현식 : 거짓_표현식으로 작성할 수 있다.
##### 문제
학생의 점수를 기반으로 학점을 출력하는 자바 프로그램을 작성하자.
90점이상 A, 80이상 90미만 B, 70이상 80미만 C, 60이상 70미만 D, 60미만 F.
```
public class ScoreEx {
    public static void main(String[] args) {
        int score=85;
        if (score>=90)
            System.out.println("A");
        else if (80<=score)
            System.out.println("B");
        else if (70<=score)
            System.out.println("C");
    }
}
```
정수 x가 짝수이면 “짝수” 홀수이면 “홀수”를 출력하는 프로그램 삼항연산자 사용하여 작성.
```
public class ScoreEx {
    public static void main(String[] args) {
        int x=2;
        String result = (x%2==0) ? "짝수" : "홀수";
        System.out.println(result);
    }
}
```
___
##### 반복문 
while, do-while, for이 존재.