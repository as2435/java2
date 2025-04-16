# 김태율 202230209
## 3월 20일 (3주차)
### 프로그래밍 언어
[기계어]
* 0, 1의 이진수로 구성된 언어
* 컴퓨터의 CPU는 기계어만 이해하고 처리가 가능

[어셈블리어]
* 기계어 명령을 ADD, SU, MOVE 등과 같은 표현하기 쉬운 상징적인 단어인 니모닉 기호(mnemonic symbol)로 일대일 대응시킨 언어

[고급언어]
* 사람이 사용하는 언어로 이해하기 쉽고, 쉽게 표현할 수 있도록 고안된 언어
* Pascal, Basic, C/C++, Java, c# 등
* 절차 지향 언어와 객체 지향 언어로 나눌 수 있음

### 프로그램 언어의 패러다임 변화
[절차 지향 언어]
* 프로그램을 절차, 순서에 따라서 실행하는 방식
* 데이터(입력)와 함수를 분리하여 작성
* 코드의 유연성이 부족, 재사용 어려움
* 전역 변수를 많이 사용하기 때문에 코드의 가독성과 유지보수가 어려움
* C, Pascal, Fortran 등이 있음

[객체 지향 언어]
* 현실의 객체를 모델링하여 프로그램을 작성하는 방식
* 객체는 데이터와 데이터를 처리하는 메소드(함수)를 모두 포함
* 상속, 캡슐화, 다형성 등의 개념을 활용하여 유연하고 재사용 가능한 코드를 작성할 수 있음
* Java, C++, Python 등이 있음

[함수 지향 언어]
* 함수형 언어는 함수를 일급 객체로 취급, 상태 변경을 피하고 불변성을 지향하는 프로그래밍 패러다임
* 함수형 언어에서는 함수의 조합으로 복잡한 작업을 수행, 상태 변경 대신 데이터를 변환하는 방식으로 프로그램을 작성

## 3월 27일 (4주차)
### 자바의 특징
가비지 컬렉션
* 자바 언어는 메모리 할당 기능은 있어도 메모리 반환 기능 없음
* 사용하지 않는 메모리는 JVM에 의해 자동 반환 - 가비지 컬렉션

실시간 응용프로그램에 부적합
* 실행 도중 예측할 수 없는 시점에 가비지 컬렉션 실행 때문
* 응용프로그램의 일시적 중단 발생

자바 프로그램은 안전
* 타임 체크 엄격
* 물리적 주소를 사용하는 포인터 개념 없음

프로그램 작성 쉬움
* 포인터 개념이 없음. 동작 메모리 반환 하지 않음. 다양한 라이브러리 지원

실행 속도 개선을 위한 JIT 컴파일러 사용
* 자바는 바이트 코드를 인터프리터 방식으로 실행
* 기계어가 실행되는 것보다 느림
* JIT컴파일 기법으로 실행 속도 개선
* JIT 컴파일 - 실행 중에 바이트 코드를 컴파일하여 기계어를 실행하는 기법

### 소스 코드, 바이트 코드, 기계어
**1. 소스코드(source code)**
* 우리가 작성하는 Java 코드(.Java 파일)
* 사람이 읽을 수 있는 고수준 언어

**2. 바이트 코드(Bytecode, .class 파일)**
* Java 컴파일러(Javac)가 소스코드를 변환한 중간 코드
* CPU가 직접 실행할 수 없음 -> JVM이 실행해야 함
* 기계어와 다르게 플랫폼 독립적
* 바이트 코드는 JVM이 해석(인터프리터)하거나, JIT 컴파일러가 기계어로 변환 실행됨

**3. 기계어(Machine Code)**
* CPU가 직접 실행할 수 있는 0과 1의 이진 코드
* 운영체제(OS)와 CPU 아키텍쳐(intel, ARM 등)에 따라 다름
* 16진수 형태의 기계어

### Java의 데이터 타입
* 기본 자료형(Primitive Type) 8개 : boolean/char/byte/short/int/long/float/double
* 레퍼런스형 1개이며 용도는 다음 3가지
  1. 클래스에 대한 레퍼런스
  2. 인터페이스에 대한 레퍼런스
  3. 배열에 대한 레퍼런스
* 문자열은 기본 타입이 아님. String 클래스로 문자열 표현

### JAVA변수의 선언
* 변수 : 프로그램 실행 중에 값을 임시로 저장하기 위한 메모리의 공간으로 프로그램 수행 중 변경될 수 있음
* 변수 선언 : 데이터 타입에서 정한 크기의 메모리를 할당

ex)
``` java
int radius;
double weight = 75.56;
char c1, c2, c3 = 'c';
```

### 상수 선언
* final 키워드 사용
* 선언할 때 초기값 지정
* 실행 중 값의 변경은 불가능

ex)
``` java
final int LENGTH = 20;
static final double PI = 3.141592;
```

### 연산자
* 연산 : 주어진 식을 계산하여 결과를 알아내는 과정
  - 증감 : `++` `--`
  - 산술 : `+` `-` `*` `/` `%`
  - 시프트 : `>>` `<<` `>>>`
  - 비교 : `>` `<` `>=` `<=` `==` `!=`
  - 비트 : `&` `|` `^` `~`
  - 논리 : `&&` `||` `!` `^`
  - 조건 : `?` `:`
  - 대입 : `=` `*=` `/=` `+=` `-=` `&=` `^=` `|=` `<<=` `>>=` `>>>=`
  
### 산술 연산자
* 산술연산자 : 더하기(+), 빼기(-), 곱하기(*), 나누기(/), 나머지(%)

### 증감 연산
* 1 증가 혹은 감소 시키는 연산 : `++`, `--`
* 전위 연산자 (++a)
* 후위 연산자 (a++)

### 대입 연산
* 연산의 오른쪽 결과를 왼쪽 변수에 대입

### 비교 연산, 논리 연산
* 비교연산자 : 두 개의 값을 비교하여 true/ false 결과
* 논리연산자 : 두 개의 논리 값에 논리 연산. 논리 결과

### 조건 연산
* 3개의 피연산자로 구성된 삼항 연산자
* opr1 ? opr2 : opr3 -> opr1이 결과가 true면 opr2, false면 opr3
* if-else을 조건연산자로 간결하게 표현 가능

### 비트 연산
* 비트 논리 연산 : 비트끼리 AND, OR, XOR, NOT 연산
* 비트 시프트 연산 : 비트를 오른쪽이나 왼쪽으로 이동

### 조건문 - 단순 if 문, if-else 문
* 단순 if 문
  - if의 괄호 안에 조건식(논리형 변수나 논리 연산)
  - 실행문장이 단일 문장인 경우 둘러싸는 {} 생략 가능

* if-else 문
  - 조건식이 참인 경우와 거짓인 경우에 실행할 문장을 각각 지시

### 다중 if-else 문
* 다중 if문
* 조건문이 너무 많은 경우, switch 문 사용 권장

### switch 문
* switch 문의 식과 case 문의 값과 비교
  - case의 비교 값과 일치하면 해당 case의 실행문장 수행
  - break를 만나면 switch 문을 벗어남
  - case의 비교 값과 일치하는 것이 없으면 default 문 실행
  - default문은 생략 가능

## 4월 3일 (5주차)

### 반복문
* 자바 반복문 - for 문, while 문, do-whlie 문
  
---

### for
* for 문을 이용하여 1부터 10까지 합 출력

``` java
public static void main(String[] args) {
        int i, sum = 0;

        for (i=1; i<=10; i++){ // 1~10까지 반복
            sum += i;
            System.out.print(i); // 더하는 수 출력

            if (i <= 9) // 1~9까지는 '+' 출력
                System.out.print("+");
            else { // i가 10인 경우
                System.out.print("="); // '=' 출력
                System.out.print(sum); // 덧셈 결과 출력
            }
        }
    }
```
**결과** `1+2+3+4+5+6+7+8+9+10=55`

---

### while
* while 문을 이용하여 입력된 정수의 평균 구하기

``` java
public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int count=0, n=0;
        double sum=0;

        System.out.println("정수를 입력하고 마지막에 0을 입력하세요.");
        while((n=scanner.nextInt()) != 0){  //0이 입력되면 while 문 벗어남
            sum=sum+n;
            count++;
        }
        System.out.print("수의 개수는 " + count + "개이며 ");
        System.out.println("평균은 " + sum/count + "입니다.");
        scanner.close();
    }
```
**결과** 
`정수를 입력하고 마지막에 0을 입력하세요.`

`10 20`

`30`

`0`

`수의 개수는 3개이며 평균은 20.0 입니다.`

---

### do-while
* do-while 문을 이용하여 'a' 에서 'z' 가지 출력하기

``` java
 public static void main(String[] args) {
        char a = 'a';

        do{
            System.out.print(a);
            a = (char) (a+1);
        } while (a <= 'z');
    }
```

**결과** 
`abcdefghijklmnopqrstuvwxyz`

---

### continue
* continue 문을 이용하여 양수 합 구하기

``` java
public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("정수를 5개 입력하세요.");
        int sum=0;

        for(int i=0; i<5; i++){
            int n=scanner.nextInt();
            if(n<=0) continue;
            else sum += n;
        }
        System.out.println("양수의 합은 " + sum);

        scanner.close();
    }
```

**결과** 
`정수를 5개 입력하세요.`

`6`

`3`

`-8`

`2`

`-4`

`양수의 합은 11`

---

### break
* break 문을 이용하여 "exit"이 입력되면 while 문 벗어나기

``` java
public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("exit을 입력하면 종료합니다");

        while(true) {
            System.out.print(">>");
            String text = scanner.nextLine();
            if(text.equals("exit"))
                break;
        }

        System.out.println("종료합니다...");
        scanner.close();
    }
```

**결과** 
`exit을 입력하면 종료합니다`

`d`

`sdf`

`exio`

`exit`

`종료합니다...`
