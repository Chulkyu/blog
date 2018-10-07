---
layout: post
title: Today I Learbed
date: 2017-10-08 02:13:00 +0300
description: Today I Learned # Add post description (optional)
img: how-to-start.jpg # Add image post (optional)
tags: [Programming, Learn, swift, ios, xcode] # add tag
---

# Terminal (CLI)

### * Shell : 사용자와 운영체제 (커널) 간에 대화를 가능하게 해주는 명령어 해석기

#### - 사용자 (명령) --> 셀 (해석) --> 커널 (명령 수행 후 결과 전송) --> 셀 (해석) --> 사용자 (결과 확인)

### * Kernel : 운영 체제의 핵심 역할

#### - 하드웨어 관리, 필요한 프로세스에 전달 등 여러 시스템 자원 제어

#### - 컴퓨터 부팅시 부트 로더에 의해 로드되어 항상 메모리에 상주

#### - 프로세서, 프로세스, 하드웨어, 메모리, 파일 시스템, 네트워크 등을 관리

#### - 인터럽트 처리기, 스케쥴링(처리 순서 결정), 수퍼바이저(사용권 부여) 등이 포함



### * Terminal Command

#### - ls : 목록 보기 / ls -a : 숨긴 파일까지 보기 / ls -al : 상세설명까지 보기

#### - cd "directory": 경로 이동 / cd .. : 상위 경로로 이동

#### - pwd : 현재 경로 확인

#### - mkdir "name": 폴더 생성 / rmdir "name" : 폴더 삭제 <폴더 안에 파일 있으면 삭제 X>

#### - touch "name" : 파일 생성 / rm "name" : 파일 삭제 / rm -rf "directory" : 폴더 안의 파일도 같이 삭제

#### - cp 복사할파일명 복사될파일명 : 파일 복사 (파일명 변경 가능)

#### - mv 변경전파일명 변경후파일명 : 파일명 변경

#### - mv ../파일명 : 파일을 상위폴더로 이동

#### - mv -v "directory" ... 이동할폴더 : 폴더 위치 이동

#### - nano : 파일에 내용 입력하기 위한 커맨드

#### - cat : 파일 안에 내용 확인

#### - head -n 5 : 파일 위에서 5번째 줄까지 내용 확인

#### - man "command" : 명령어 메뉴얼 확인

#### - more : 파일의 내용을 한번에 한 화면씩 보여준다.

#### - kill : 어플리케이션 실행 중지 / ps : '죽이고' 싶은 어플의 정확한 프로세스 ID 확인

#### - sudo : 일반 사용자가 어플을 설치해야 할때, 루트 권한을 임시로 부여(패스워드를 입력해야 한다.)

#### - passwd : 패스워드 변경, 현재 패스워드와 새로운 패스워드 입력

------

# *MVC (Model View Controller)

#### [MVC](https://medium.com/ios-development-with-swift/mvc-%ED%8C%A8%ED%84%B4-in-ios-7751911f8ca8)









------

# Xcode (IDE, Integrated Development)

#### playground

##### - 코드 작성 후 결과 바로 확인 가능

##### - 주석 /// (Quick help) : description까지 볼 수 있음

##### - command + option + / :

##### - ';' 세미콜론 생략 가능, 한 라인에 여러 구문(다중 명령)을 사용하고 싶을 경우는 세미콜론 필수

#### * Naming : 영어 외에도 유니코드 문자를 포함한 대부분 문자 사용 가능

##### - 변수명의 목적이 무엇인지 알 수 있도록 확실하게 (길어도 상관 없다)

##### - 선언 전에는 사용 불가

##### - let `let` = 1   // Swift 에서 사용되는 키워드일 경우 backquote(`) 를 이용해 사용 가능

#### * 변수로 사용할 수 없는 이름

##### 1. 같은 스코프 범위 내에서 중복되는 이름 : 같은 (), {}, [] 안에서 중복 X

##### 2. 공백문자 : 단어사이 띄워쓰기 X

##### 3. 수학 기호 (√, ∑ 등)

##### 4. 화살표 (→, ← 등)

##### 5. 숫자로 시작하는 이름 (시작 부분 외에는 사용 가능)

#### * Type Annotation

##### - 변수 선언 시 사용될 자료의 타입을 명확하게 지정하는 것

#### * Type Inference

##### - 변수 선언 시 초기화로 사용되는 값의 타입을 통해 변수 타입을 추론하여 적용

##### - 변수 선언 시 value 값을 나중에 지정해 주려고 할 때는 타입을 지정해주어야 한다. // let language: String

##### language = "Swift 4"



#### * Literals

##### - 소스 코드의 고정된 값을 대표하는 용어.

##### - 정수 / 실수 / 문자 / 문자열 / 불리언 등

##### - 2^16 범위 : -2^15 ~ 2^15 -1

##### - let q2: Int8 = Int8.max + 1 : 타입을 명시해주면 컴파일러가 돌아가기 전에 에러 확인 가능

##### - let q2 = Int8(127 + 1) : 실행시켜 보기 전에는 에러 확인 불가능

##### - 01111111 --> 1000000 : int8 최대값에 +1을 하면 음수로 변환되기 때문에 오류 발생

##### - Int8.max &+ 1 : Int8.min

##### - Int8.min &- 1 : Int8.max

#### * Type Conversion

##### - magnitude 와 abs 의 차이점은?

##### : type이 변한다. magnitude: UInt

##### : abs: Int

##### - 양수를 사용할 때 Int / UInt 중 어느 것이 좋을까? (사용성, 안전성, 타입 추론, 변환 등)

##### : Int (일반적으로 범용적으로 Int를 많이 쓴다)

### * Basic Operators

##### - 단항 연산자 : 연산자에 피연산자가 1개

##### - 이항 연산자 : 피연산자가 2개

##### - 삼항 연산자(Ternary Operation) :  a > 0 ? "positive" : "negative" (If 조건문과 동일)

#### * Comparison Operators

##### - 숫자가 아닌 문자열에 대한 비교는 ? : 아스키, 유니코드에 주어진 코드값에 의해 크기 결정

##### - && : 둘 다 true => true

##### - ll : 둘 중 하나만 true여도 true

##### - true ll  : 뒤의 조건은 확인하지 않고 true



#### * Range Operation

##### - for i in 1...100.reversed() { print(i) } : 100부터 1까지 거꾸로 반복



### * Function

#### - 일련의 작업을 수행하는 코드 묶음을 식별할 수 있는 특정한 이름을 부여하여 사용하는 것

##### - Input 과 Output 이 모두 있는 것 (Function)

##### - Input 이 없고 Output 만 있는 것 (Generator)

##### - Input 이 있고 Output 은 없는 것 (Consumer)

##### - Input 과 Output 이 모두 없는 것

#### * func someFunction(argumentLabel parameterName: Int)

#### Q) 왜 Argument Label - Parameter Name 따로 쓰는지?

##### - 외부/내부에서 함수 용도(의미)/수식을 이해하기 쉽도록

##### - argumentLabel : 함수를 외부에서 호출해서 쓸 때

##### - parameterName : 내부에서 매개변수 이름

##### ex) 5.distance(to: 10)



### * Typealias

##### - typealias <#type name#> = <#type expression#>

##### ex) typealias AudioSample = UInt16

##### - 타입을 어떤 경우에 이렇게 쓰려고 했는지 나중에 알기 쉽게 하기 위해서 타입이 어디에 쓰일지를 이름으로 붙여두는것

### *Practice

##### 1. input : name / print



##### 2. input : age / print

##### 3. input : name, age / print : introducemyself

##### 4. input : Int / output : check 2n or not

##### 5. input : Int, Int / output : a * b (a = 10)

##### 6. input : grade of 4 subject / output : Average



### // ============== 2018-09-11===============



### * Github

#### - .gitignore :



## * Conditional Statements

- #### if 조건문

- #### Switch Statements // === 정리 필요 ===

##### - 마지막에 default: break or return값 필요

##### - 범위가 아닌 복합체/다중요소(?) 중에 적합한 케이스가 있는지 확인할 때 if 조건문 보다 간결

##### - if 조건문은 조건이 bool 타입이어야 하지만 switch 조건문에서는 꼭 bool 타입이 아니여도 된다.



## * Early Exit

- ### guard statement

##### - if~else  쓰임새는 똑같. if 조건을 강조하고 싶을 때 !



Question  (switch 를 이용해서 구현)



두 개의 정수를 입력받아 두 수를 하나의 숫자로 이어서 합친 결과를 출력하는 함수 (1, 5 입력 시 15 반환)

문자열 두 개를 입력받아 두 문자열이 같은지 여부를 판단해주는 함수

학점을 입력받아 각각의 등급을 반환해주는 함수 (4.5 = A+,  4.0 = A, 3.5 = B+ ...)

세 수를 입력받아 세 수의 곱이 양수이면 true , 음수이면 false 반환하는 함수  (switch - where clause 사용할 것)

특정한 달을 숫자로 입력 받아 문자로 반환해주는 함수 (1 = "Jan" , 2 = "Feb")

윤년 구하기 (2월 29일이 있는 해.  매 4년 마다 윤년. 매 100년 째에는 윤년이 아님. 매 400년 째에는 윤년)



## * Loops

- ### For-In Loops

#### - Wildcard Pattern :  

#### - terminator :



### Question1

### Question2



## * Tuples

##### - 여러 타입의 변수를 지정 가능

##### - .0 : 첫번째 변수



## * Control Transfer Statement

#### - continue : 조건에 만족하면 재실행



## * Enumerations (Study more)

##### - 연관된 값의 그룹에 대해 공통 타입을 정의한 뒤 type-safe 하게 해당 값들을 사용 가능



## * Raw Value

##### - Strings, Characters, or any of the Integer or Floating-point number types

##### -raw value 는 해당 Enumeration 내에서 반드시 고유한 값이어야 함.

#### enum 타입이 Int일 때 :

##### - raw value를 직접 지정해주지 않으면 처음 0부터 순서대로 지정 받음

##### - 중간 case에 값을 지정해주면 지정해준 값+1의 값을 가진다.

#### enum 타입이 String일 때 :

##### - raw value를 지정해주지 않으면 자기 자신을 raw value로 지정 받음

##### - 중간 case에 값을 지정해주어도 다른 case 값은 변동 없이 자기 자신을 raw value로 지정 받는다.

## * Nested (Study more)





# *Collection

## * Array

##### - Ordered Collection

##### -Zero-based Integer Index

##### var variableArray = [1, 2]

##### variableArray = [0]  --> 1



## * Set

##### - Array 와 기본 모습은 똑같. 타입에 Set을 명시해주어야 한다.

##### - index가 따로 없어서 위치를 지정해서 추가하지 못함(just insert 사용)

#### * 집합 연산 사용 가능

##### - mutating 명령어와 리턴값만 반환해주는 명령어 존재

##### - 교집합 : a.intersection(b)

##### - 합집합 : a.union(b)

##### - 합-교 : a.symmertricDifference(b)

##### - 차집합 : a.subtracting(b)



## *Closer

#### - 클로져 중에서 이름이 있는 함수 = function

##### - 변수에 함수 자체를 담을 수 있다.

##### - 함수의 input 값, return 값에 다른 함수 자체를 넣어서 사용할 수 있다. (first class citizen 특성)



## * Optional

##### - Int 타입을 optional (Int) 타입에 대입은 가능, 반대는 불가





### // ============== 2018 - 09 - 17 =================



## * OOP (Object - Oriented Programming)

#### - 프로그래밍에도 코드를 더 효율적으로 만들고 작성하기 위한 패러다임이 존재.

#### - 절차 지향형, 객체지향형, 함수형, 논리형 등

##### - swift 언어는 객체지향형, 함수형, 프로토콜 지향 프로그래밍을 모두 다룰 수 있는 언어. 다만 IOS 프레임워크가 객체지향형 프로그래밍으로 구현되어 있어서, 객체지향 프로그래밍을 하도록 권장

------

#### - 객체지향: 프로그램을 여러 객체들의 모임으로 보는 것. 각각의 객체는 메세지를 주고 받을 수 있으며, 데이터를 처리할 수 있다.

#### - 객체지향 기본 구성 요소 : 클래스, 객체, 메소드, 프로퍼티 등

#### - 객체 : 클래스의 인스턴스로 자신만의 속성(property)와 행위(method)를 갖고 있다.

#### - 클래스 : 붕어빵을 만드는 기계 / 자동차 도면

#### - 객체 : 붕어빵 / 출고된 자동차

#### * 클래스 파일을 메모리에 올리면 객체화 되고, 객체들의 속성과 명령어가 실행되면서 프로그램이 실행되는 것 !

------

#### - 객체지향 프로그래밍이란 캡슐화, 다형성, 상속 을 이용하여 코드 재사용을 증가시키고, 유지보수를 감소시키는 장점을 얻기 위해서 객체들을 연결시켜 프로그래밍 하는 것

#### - 객체지향의 5대 특징

- ##### 추상화 : 객체들의 공통적인 부분을 뽑아서 따로 구현해놓는 것. 공통적인 부분만 뽑아내기 때문에 구체적인 정보를 담지 못하고, 추상적인 정보가 모여 있어서 '추상화'가 특징

- ##### 캡슐화, 은닉화 : 캡슐화, 은닉화는 같이 발생한다. 객체의 속성과 행위를 하나로 묶고(캡슐화), 실제 구현 내용 일부를 외부에 감추는(은닉화) 것.

- ##### 상속성 : 하나의 클래스가 갖고 있는 속성(property)과 행위(method)를 다른 클래스가 상속 받을때 사용.

- ##### 다형성 : 하나의 method나 class를 다양한 방법으로 동작시키는 것. 오버로딩이나 오버라이드가 대표적인 예시. 오버로딩은 같은 이름의 함수를 파라미터에 따라 다양하게 구현하는 것을 의미하고, 오버라이딩은 상위 클래스가 가지고 있는 메소드가 하위 클래스로 상속되어 하위 클래스에서 재정의해서 사용하는 것을 의미.

------

##### - 객체 : 데이터(상태) + 메서드(행위)

##### - Instance : 메모리에 저장되는...값?



#### Q. 다음 용어의 차이점은?

##### -  함수(Function) : 클래스 외부에 있는 함수 = free function

##### - 메서드(Method) : 클래스 내에 있는 함수



#### * Equatable, Identical

##### - 클래스 타입과 다른 타입은 비교 불가

##### - 같은 클래스 타입이라도 컴파일러가 클래스 내부 데이터 중 어떤걸 비교해야 하는지 판단 불가 이므로 비교 불가

> class User1: Equatable {

> var name = "이순신"

> let age = 30



> static func ==(lhs: User1, rhs: User1) -> Bool {

> return lhs.name == rhs.name

> }

> }



> let user3 = User1()

> var user4 = User1()   // 새로 선언할 때 마다 새로운 레퍼런스를 생성 !

> user3 == user4    // name의 값이 같으므로 true

> user3 === user4   // 레퍼런스 주소는 다르므로 false

> user3 !== user4   //



> user4.name = "홍길동"



> user4 = user3

> user4.name
>
>

> user4 = user3

##### // 레퍼런스 주소값과 value 값이 같아진다 -> 둘 중에 하나만 value값 바뀌어도               둘다 value 값이 바뀜 (레퍼런스 주소값이 같기 때문)

> user3 == user4   

##### // name 값이 같으므로 true

> user3 === user4  

##### // 레퍼런스 주소 값도 같아지므로 true

------



## * Initialize(초기화), Deinitialize

#### - 일반적으로 OOP에서는 생성자(Constructor)와 파괴자(Destructor) 라는 개념이 존재. 객체의 탄생과 사라지는 시점에 맞춰 시작과 끝에 호출되는 메소드.

#### - 스위프트에서는 초기화(Initialization)와 마무리(Deinitialization)라는 개념의 용어를 사용.

- ### Initialization

##### 생성자(Constructor) 개념은 클래스가 객체화 될 때 자동으로 실행되는 메소드(init)를 지칭.  init은 구조체(struct)와 클래스(class) 모두 지원

##### - self : 메모리에 올라간 함수? 클래스? 를 다시 호출할 때 쓰는 용어

##### - lazy : lazy의 변수가 처음 호출될 때 초기화값이 할당됨

#### - init() 은 일반 메소드 선언과 다르게 func 키워드가 필요 없다.

#### 또한, override 시 override를 표기할 필요가 없다.

------

- ####  init 저장 속성 값 (Setting Intial Values for Stored Properities)

```swift
class SimpleClass {
    var value: Int

    init() {
        value = 0
    }
}
let simple = SimpleClass()
/* init 저장 속성 값을 이렇게 설정해 줘도 되지만 보통 저장 속성 값을 쓰는 경우는 class를 인스턴스화 시킬 때 초기값을 바로 설정해줄 때 사용한다. 그러기 위해선 init에 argument를 설정해주면 된다.
*/
```

------

#### - 클래스 인스턴스 생성 시, 프로퍼티 값에 새로운 값을 할당하려고 할 때 사용

#### - init은 클래스나 구조체의 인스턴스를 생성 할 때 넘기는 매개변수 구조에 따라 호출 되는 것이 다르다.

```swift
class SimpleClass2 {

    /*
    let value: Int

    변수 선언할 때 let으로 하면 인스턴스화 할 때
    초기화 과정에서만 변경 가능하고,
    초기화 설정이 끝난 뒤에는 변경 불가능하다.

    */

    var value: Int

    /*

    init(v: Int) {
    self.value = 5
}
       이렇게 값을 바로 넣어주게 되면 인스턴스화 할 때
       let simple = SimpleClass2(v: 55) 값을 넣어줘도
       값은 변하지 않는다.
       simple.value == 5

    */


    // 인스턴스화할 때 인자를 받아 값을 초기화 설정
    init(v: Int) {		// 앞에서 (var value: Int)로
        self.value = v  // 이미 value의 타입을 정해주었지만
    }					// init(v) -> error,
    					// init(v: Int)같은 타입 입력해야 함

    init() {
        self.value = -999
    }
}

```

#### 두 개의 init 이  override 되어 있다. 하지만 매개변수가 다르다. 특히 하나는 매개변수가 존재하지 않는다.

------

- #### init() : 기본 초기화 메소드(Default Initialization)로 아래와 같이 그냥 인스턴스를 생성하면 호출된다.

```swift
let simple1 = SimpleClass2()
print(simple1.value)
// -999
```

- #### init( v: Int) : 인자를 넣어서 초기화 메소드를 이용할 때

```swift
let simple2 = SimpleClass2(v: 5)
print(simple2.value)
// 5
```

##### * class 안에 기본 초기화 메소드 init() 없이 init(v: Int)만 있을시 인스턴스화 할 때 인자를 호출하지 않으면 에러가 발생한다

```swift
let simple3 = SimpleClass2() // error 발생
// "Missing argument for parameter 'v' in call"
```

- #### function과 같이 init도 호출시 argument 생략 가능하다.( _ )

```swift
class SimpleClass {
    var value = 0

    init(_ v: Int) {		// argument 자리에 _ (언더바)
        self.value = v
    }

    init() {
        self.value = -999
    }
}

let a = SimpleClass(10)     // argument 생략하고 인자 호출
// value == 10
```

------

#### - 초기화 시켜줄 매개변수가 여러개 있을 경우 모든 매개변수를 호출시 적어줘야 한다.

```swift
class SimpleClass3 {
    var value: Int
    var name: String
    var age: Int
    var score: Double

    init(v: Int, n: String, a: Int, s: Double) {
        self.value = v
        self.name = n
        self.age = a
        self.score = s
    }
}

let simple = SimpleClass3(v: 5, n: "maru", a: 2, s: 60.8)

```

------

#### - 상속 시 init도 그대로 상속된다. 또한 init을 오버라이드 할 때 super의 init을 호출하는 것으로 부모의 초기화 메소드를 그대로 이용할 수 있다. (init은 override 시 override를 표기할 필요 없다.)

```swift
class AnotherClass: SimpleClass2 {
    init() {
        super.init()
    }
}

var simpleClass2 = AnotherClass()
// instance.value == -999
```

#### * 위 예시에서는 super.init() 을 호출하지 않아도 문제가 없겠지만, 상속 시 부모의 초기화 메소드를 호출하지 않으면 대게 문제가 발생할 여지가 높으니 호출해주도록 하자.

------

#### - init() 은 override 가 가능하지만, 한 클래스 안에서 자신의 다른 init을 호출하면 에러 발생

```swift
class SimpleClass {
    var value = 0

    init(v: Int) {
        self.value = v
    }

    init() {
        self.init(v: -999)     // ERROR!
    }
}
```

#### - convenience 키워드를 사용하여 문제 해결.

- ##### convenience : 한 init이 다른 init을 호출하는 식으로 init이 여러 단계에 걸쳐 처리(multi-step initialization)해야 할 때 필요한 키워드

```swift
class SimpleClass {
    var value = 0

    init(v: Int) {
        self.value = v
    }

    convenience init() {
        self.init(v: -999)
    }
}

let simple = SimpleClass()
simple.value == -999

let simple2 = SimpleClass(v: 55)
simple.value == 55
```

------

- ####  init 기본 속성 값(Default Property Values)

##### - 짧고 명확한 initializer를 만들며 기본 값으로부터 속성의 타입을 추론하도록 만든다. initializer 상속을 쉽게 만드는 이점이 있다.

```swift
class DefaultClass {
    var value = 0
}

let default1 = DefaultClass()
// default1.value == 0

default1.value = 5
//default.value == 5

```

------

- #### 사용자 정의 초기화(Customizing initialization)

##### - 하나의 변수에 argument, parameter 를 다르게 설정해 주어 인스턴스화해서 호출 할 때 사용자가 필요한 인자로 설정해서 사용 가능

```swift
struct Celsius {
    var temperatureInCelsius: Double
    init(fromFahrenheit fahrenheit: Double) {
        temperatureInCelsius = (fahrenheit - 32.0) / 1.8
    }
    init(fromKelvin kelvin: Double) {
        temperatureInCelsius = kelvin - 273.15
    }
    init(_ celsius: Double) {
        temperatureInCelsius = celsius
    }
}
let boilingPointOfWater = Celsius(fromFahrenheit: 212.0)
// boilingPointOfWater.temperatureInCelsius is 100.0

let freezingPointOfWater = Celsius(fromKelvin: 273.15)
// freezingPointOfWater.temperatureInCelsius is 0.0

let bodyTemperature = Celsius(37.0)
// argument 생략
// bodyTemperature.temperatureInCelsius is 37.0
```

------

## * Study more

- #### 값 타입을 위한 이니셜라이저 델리게이션(Initializer Delegation for Value Types)

#### [Initialize 참조1](http://minsone.github.io/mac/ios/swift-initialization-summary)

------

- ### Deinitalization

#### - init의 반대 요소

##### * deinit은 클래스에서만 사용 가능

#### - deinit은 parameter를 가질 수 없다.

```swift
class SimpleClass {
    var value = 0

    deinit {
        self.value = 0
    }
}
```

##### deinit은 클래스 인스턴스가 필요 없어져 메모리에서 사라질 때(레퍼런스 카운트가 0이 될 때) 호출되는 기능. 주로 자신이 점찍어 놓은(retain) 다른 인스턴스의 메모리가 해제 될 수 있도록 조치(release)해 주는 것이 목적이지만, swift는 ARC 기반 하에 있어서 이런 행위는 거의 필요 없다.

##### * swift에서 deinit은 Singleton 인스턴스 등이 자신의 인스턴스를 활용하고 있다면 해당 Singleton 인스턴스에서 자신을 참조하지 않도록 처리하는데 주로 사용되지 않을까..?

#### [Initialize 참조1](http://minsone.github.io/mac/ios/swift-initialization-summary)

#### [Initialize 참조2](http://seorenn.blogspot.com/2014/06/swift-initialization-and.html)

------

## * Access Control

##### - 다른 모듈의 코드 또는 다른 소스 파일 등으로부터 접근을 제한하는 것

##### - 세부 구현 내용을 숨기고 접근할 수 있는 인터페이스 지정 가능

##### - open > public > ( internal > fileprivate > private )



### * Instance

##### : 클래스를 통해 호출할 수 없고, 클래스를 실체화 하여 생성된 인스턴스를 통해서 호출할 수 있는 메서드를 의미(뭔소리?)

------

# * Segue

- #### Segue란?

##### : 사전적 의미로는 '다른 것으로 부드럽게 넘어가는 것'을 의미한다. IOS에선 화면전환을 의미한다.

- #### Segue의 종류

  #### - 주의 : Segue를 할 때는 늘 새로운 인스턴스 객체가 생성

  ##### - Show : Show는 Navigation Controller에서 push/pop의 push를 의미한다. Navigation Controller의 스택 상에 Destination ViewController를 삽입하여 쌓게 된다. 'UINavigationControllerDelegate'를 사용하면 다양한 전환 효과를 구현할 수 있다.

  ##### - Show Detail(iPad만 해당) : UISplitViewController를 사용할 때, 사용하는 Segue. 아이패드에서 화면을 가로로 눕히면 등장하는 Detail View상에 ViewController를 밀어 넣게 된다. Navigation Controller의 스택에슨 전혀 영향을 주지 않는다.

  ##### - Present Modally : presentViewController 메소드와 동일한 동작을 하게 된다. 옵션에 따라 viewController를 띄우는 애니메이션에 변화를 줄 수 있다. Navigation Controller의 스택에는 전혀 영향을 주지 않는다. 단, 'Modally'라는 단어에서 알 수 있듯이 이미 Presentation을 한 ViewController에서 다른 ViewController를 presentation 할 수 없다. Show와 같이 'UINavigationControllerDelegate'를 사용하면 다양한 전환 효과를 구현할 수 있다.

  ##### - Popover Presentation(iPad만 해당) : Show Detail과 같이 iPad에서만 볼 수 있는 View Transition이다. 작은 팝업 뷰 혹은 context menu 형식으로 ViewController를 띄우는 방법이다. 아이폰에서도 사용은 가능핮디만 단순한 Modal View처럼 표시된다.

- #### Segue 화면 전환 방법

##### 1. ViewController(테이블뷰의 셀이 Static일 때 유용) : 스토리보드의 ViewController 아이콘을 화면전환할 ViewController에 Control 드래그 --> 옵션 선택

##### 2. Button : 스토리보드에 Button을 하나 만들고 Segue할 ViewController에 Control 드래그 --> 옵션 선택. Button을 코드로 끌어와 @IBAction으로 만들어줄 필요 없다.

##### * Button의 문제점 : 두번째 화면에서 다시 첫번째로 돌아올 방법이 없다는 것. Navigation Controller를 달아주고 Segue를 Present Modally가 아닌 Show로 하면 뒤로가기 버튼이 달리기는 하지만 그 외에는 방법이 없다. 이럴 땐 'Exit'가 필요 !

##### * Exit 만들기 (Unwind Segue) : 두번째 화면 --> 첫번째 화면, 첫번째 화면 위에 두번째 화면이 쌓여 있는데 두번째 화면이 없어지면서 다시 첫번째 화면이 나타난다. 만약 1 --> 2 --> 3 순으로 Segue를 하고 3에서 다시 1로 돌아가는 Unwind Segue를 만들면 3, 2 ViewController가 다 사라지고 1만 나타나게 된다.

##### ** <주의사항> 보통 button이 있는 ViewController에 Button 코드를 넣지만 Unwind Segue는 돌아갈 ViewController에 코드를 넣어야 한다. Button과 코드를 다 작성하고 Button을 Button이 있는 viewController의 Exit 아이콘에 Control 드래그 해서 연결하면 된다. **

- ##### source : Segue시 시작점에 해당하는 ViewController 가리킨다

- ##### destination : 전환하고자 하는 도착점에 해당하는 ViewController 가리킨다

- #### Segue 데이터 교환

##### - 화면을 전환하면서 두 화면 간에 데이터 교환, 갱신하고 무엇인가 보여줘야 더 큰 의미가 있다. Segue의 데이터 교환과 관련해서 UIViewController에서 2가지 메서드 제공.

- ##### prepareForSegue : 세그웨이 실행 전 준비

- ##### performSegueWithIdentifier : 세그웨이 실행

- #### Segue Identifier

##### - 세그웨이 데이터 교환을 더 알아보기 전에, 각 Segue를 구별할 수 있다록 식별자를 지정해 주는 작업이 우선되어야 한다. 데이터를 교환하는 메서드를 수행할 때, 메서드가 어떤 Segue에 대해 일을 처리해야하는지 알아야 한다. 각 Segue 별로 이름을 지정. Segue를 선택한 다음, 우측 상단의 Attributes Inspector 안의 Identifier에 이름 입력.



- #### PrepareForSegue

##### - Segue 실행 준비하는 메서드, 이동전 화면(A)에서 작성.

- ##### 어떤 Segue가 실행될 때인가?

- ##### 해당 Segue가 실행되면 이동할 화면(B)은 무엇인가?

- ##### 이동된 화면(B)의 어느 데이터를 어떻게 변경할 것인가?

##### - performSegueWithIdentifier 필요 없이 prepareForSegue만으로도 해당 Segue가 실행되면 즉시 데이터 교환이 실행됨.

##### ** <주의사항> 이동된 화면(B)의 IBOutlet(ex Label) 데이터를 바로 바꿔줄 순 없다. 화면(B)의 Label의 텍스트 값을 화면(A)에서 가져온 텍스트 값으로 변경하고 싶을 때, 바로 변경이 불가능. 화면(B)에 property를 만들어 Segue가 property 값을 변경하게 만들고, 화면(B)의 코드에서 Label의 데이터를 변경하도록 코드를 작성해야 한다.



- #### performSegueWithIdentifier

##### - performSegueWithIdentifier는 ''원하는 순간''에 prepareForSegue를 통해 Segue를 실행시키는 코드.

##### - Segue의 시점을 통제할 수 있게 된다.

##### - 주로 화면(A)가 테이블뷰나 컬렌션뷰일 때 사용.

##### - 화면(A)의 특정 셀이나 아이템을 누르면 화면(B)로 Segue하여 관련 데이터를 보여줄 때

##### - 테이블 뷰 : didSelectRowAthIndexPath 메서드

##### - 컬렉션뷰 : didSelectitemAtIndexPath 메서드

##### 메서드들 안에서 performSegueWithIdentifier 사용. 셀이나 아이템을 누르면 화면이 이동

##### - didSelectRowAtIndexPath와 같은 메서드들은 사용자가 선택한 IndexPath를 인자값으로 가지고 오기 때문에 그대로 IndexPath를 활용할 수 있는 장점이 있다. 사용자가 셀이나 아이템을 클릭하는 순간 바로 prepareForSegue에서 준비된 코드들이 실행되도록 하는 것이 didSelectRowAtIndexPath 내의 performSegueWithIdentifier이다.



------

# * Singleton

##### - 특정 클래스의 인스턴스에 접근할 때 항상 동일한 인스턴스만을 반환하도록 하는 설계 패턴

##### - 한 번 생성된 이후에는 프로그램이 종료될 때까지 항상 메모리에 상주

##### - 어플리케이션에서 유일하게 하나만 필요한 객체에 사용

##### - UIApplication, AppDelegate 등



------

# * UserDefaults

##### - iOS 에서 데이터를 파일에 저장하기 위해 사용하는 대표적인 클래스 중 하나

##### - 간단한 정보를 저장하고 불러올 때 사용하며 내부적으로 pList 파일로 저장

- #### Question : 메모리와 파일로 저장하는 형태의 차이점?

##### - 메모리 : 앱 종료 시 사라짐

##### - 파일 : 앱 종료 후에도 남이있음

------

# * Protocols

##### - 스위프트의 프로토콜 기능은 개발자에게 '이 메소드나 프로퍼티 등의 요구사항(스펙)을 구현해라' 라고 명시하는 것.

##### - 특정 클래스를 만들 때 프로토콜을 명시하면 해당 프로토콜의 요구사항대로 메소드나 프로퍼티를 직접 구현해야 한다.

##### - 특히 Delegate를 사용할 때는 Delegate의 스펙이 프로토콜(@protocol)에 정의되어 있어서 꼭 써주어야 한다.

- #### Protocol 선언

```swift
 Protocol someProtocol {

 func someFunction() -> Int

 var someProperty: String { get set }

 optional func anotherFunction()

 }
```



#####  

##### - 프로토콜 내부에는 메소드나 프로퍼티 등을 구현 없이 이름만 정의되어 있다. ex) someFunction(), someProperty의 getter 와 setter가 필요하다는 의미로 이해.

##### - optional func anotherFunction() 은 꼭 구현할 필요가 없다는 의미

##### - 프로토콜 내부에는 static func나 class func 같은 정적 멤버 구현 요구도 정의 가능

- #### Protocol의 사용

##### - 구조체(struct)나 클래스(class)는 사용할 프로토콜 이름 오른쪽에 콜론(:)을 부인 이후 명시 가능.

```swift
struct SomeStruct: SomeProtocol {

 	func someFunction() -> Int {

 		return 0

 }

 	var someProperty:  String {

        get {

 			return "from someProperty"

 }

 		set {

 			self.someProperty = newValue + "!"

	 		}

 	}

 }
```



#### #

##### - 프로토콜을 쓴다고 하고 구현하지 않으면 구현하지 않았다는 error 발생





- #### Delegation

##### - Protocol이 가장 빈번하게 사용되는 예 : Delegation(위임)

##### - 서로 다른 클래스 간의 이벤트를 알려주기에 효과적인 패턴



# * Delegate

- #### delegate란 무엇인가?

##### - 어떤 객체가 해야 하는 일을 부분적으로 확장해서 대신 처리한다



- #### Delegation Pattern

##### - delegate라는 용어가 사용되면 그게 바로 Delegation Pattern을 구현한 것

##### * Delegation Pattern은 특정 클래스가 하는 일 중 일부를 자신의 커스텀 클래스에서 대신 처리하기 위해 사용하는 패턴

###### <참고> Delegation Pattern은 데코레이터 패턴(Decorator Pattern)의 하위 분류로서 '확장 기능 제공'을 위한 디자인 패턴 중 하나

- ##### Delegate의 규칙을 정의한 Protocol과 이 프로토콜을 사용하는 클래스(Delegate 선언)

```swift
 Protocol BlahProtocol {

 	func blah(blahObject: BlahClass)

 }

 class BlahClass {

 	var delegate: BlahProtocol?

 	func something() {

 		self.delegate?.blah(self)

	 }

 }
```





- ##### 다른 클래스에서 Delegate를 위임받아 사용

```swift
class CustomClass: BlahProtocol {

 	let blah = BlahClass()

 	init() {

 		self.blah.delegate = self

 		self.blah.something()

 }

 	func blah(blahObject: BlahClass) {

 		print("Calling with blah protocol")

	 	}

 }

 let cc = CustomClass() 	
// 콘솔에 "Calling with blah protocol"
```

######  

##### - CustomClass는 BlahProtocol의 규칙에 따라 특정한 메소드 구현

##### - 내부에서 쓰는 BlahClass 인스턴스의 delegate에 자신을 위임(delete)

##### * Delegation Pattern은 이처럼 특정 클래스에서 하는 일 중 일부를 자신의 클래스에서 구현 할 수 있도록 하는 디자인 패턴 *

------

## *Property get, set, didSet, willSet

#### - property에는 {get, set} 또는 {didSet, willSet} 을 사용 가능

#### - 하나의 property에 {get, set}, {didSet, willSet} 모두 같이 쓸 순 없다

- #### get, set sytax

```swift
class GetSet {

    var storage: Int		// get,set을 사용하기 위해선
   							// 또 다른 storage property가 필요
    init(storage: Int) {
        self.storage = storage
    }


    var intProperty: Int {		// get, set property
        get {					// get만 사용할 땐 get 생략 가능
            return storage - 1	// set만 사용은 불가
        }
        set {
            storage = newValue + 1
        }
    }

    func subscription() {
        print("get is \(intProperty)")
    }	// 읽기 전용인 get property를 사용해 데이터를 읽어온다						
}

let getSet = GetSet(storage: 15)
getSet.subscription()
// "get is 14"
// get은 GetSet 클래스를 인스턴스화 시킬 때 설정해준 초기화 값만 읽어온다.

getSet.intProperty = 16
getSet.storage
// 17
```

------

- ### get, set을 사용하는 경우

#### 1. property에 값이 할당 될 때 적절한 값인지 검증할 때

#### 2. 다른 property 값에 의존적인 property를 관리 할 때

#### 3. property를 private하게 사용하기 위해 [참조](https://medium.com/ios-development-with-swift/%ED%94%84%EB%A1%9C%ED%8D%BC%ED%8B%B0-get-set-didset-willset-in-ios-a8f2d4da5514)

------

#### 1. property에 값이 할당 될 때 적절한 값인지 검증할 때

##### - set의 newValue를 사용하여 property의 값이 바뀌기 전에 확인 가능

```swift
class Company {
    var memberStorage: Int = 0
    var member: Int {
        get {
            return memberStorage
        }
        set {
            if newValue > 0 {
                memberStorage = newValue
            } else {
                print("직원 수는 0명 보다 많아야 합니다.")
            }
        }
    }
}
let company = Company()
company.member = -5		// "직원 수는 0명 보다 많아야 합니다."
company.memberStorage	// 0

company.member = 15
company.memberStorage	// 15

```

------

#### 2. 다른 property 값에 의존적인 property를 관리 할 때

##### - 회사 멤버 저녁식사 비용은 회사 멤버수에 비례(의존적)

##### - get을 활용하여 member 수에 맞춰 memberDinnerCost 계산 가능

##### - get만 사용하였기 때문에 클래스 외부에서 memberDinnerCost는 변경 불가, 오직 member 수에 따라 계산된 값이 반환된다.

```swift
class Company {
    var memberStorage: Int = 0
    var member: Int {
        get {
            return memberStorage
        }
        set {
            if newValue > 0 {
                memberStorage = newValue
            } else {
                print("직원 수는 0명 보다 커야 합니다.")
            }
        }
    }

    var memberDinnerCost: Int {
        get {
            return memberStorage * 10000
        }
    }

}
let dinnerCost = Company()
dinnerCost.member = 15
dinnerCost.memberDinnerCost		// 150000
```

------

- ### didSet, willSet

#### - property observer : 내부적으로 **"초기화 된"** property 값을 감시

- #### didSet : property 값이 변경된 직후에 호출

- #### willSet : property 값이 변경되기 직전에 호출

#### - didSet, willSet을 활용하여 원하는 타이밍에 작업 수행 가능

#### * property observer를 사용하기 위해서는 property의 값이 ''**반드시 초기화**'' 되어 있어야 한다.

#### - 클래스의 init() {} 안에서 값을 할당 할 때는 didSet, willSet은 호출 되지 않음. 초기화 이후부터 property를 감시

```swift
var propertyObserver: Int = 10 {
    didSet(oldValue) {
        // propertyObserver의 값이 변경된 직후에 호출, oldValue는 propertyObserver의 변경 전 값
    }
    willSet(newValue) {
        // propertyObserver의 값이 변경되기 직전에 호출, newValue는 변경 될 새로운 값
    }
}
```

------

- #### didSet, willSet(property observer) 사용하는 경우

#### - 가장 빈번한 사용은 Model에서 갱신된 값을 View에 보여줄 때

#### [MVC](https://medium.com/ios-development-with-swift/mvc-%ED%8C%A8%ED%84%B4-in-ios-7751911f8ca8)

##### - ex) View에 점수를 표시하는 Label이 있다고 가정. 점수가 바뀔 때마다 View의 Label을 업데이트 해주고 싶을 때.

```swift
score = 85
scoreLabel.text = "Score: \(score)"
```

##### - 이렇게 해도 View의 Label은 정상적으로 바뀌지만, 만약 여러곳에서 score의 값을 바꾼다면 score의 값이 바뀌는 곳 마다 scoreLabel.text = "Score: \(score)" 를 적어주어야 한다. (Bad Case)

------

#### - 이럴 때 property observer를 사용할 수 있다.

##### - property observer를 사용하면 score값이 바뀔 때마다 View의 값을 갱신하는 작업을 따로 해줄 필요가 없다.

```swift
var score: Int = 0 {
    didSet {
        scoreLabel.text = "Score: \(score)"
// score의 값이 바뀐 직후 didSet이 실행되어 scoreLabel.text의 값을 바꾼다
    }
}
```

------

#### - 바뀐 값과 바뀌기 전의 값을 비교하는 작업도 가능

```swift
var score: Int = 0 {
   didSet {
      print("현재 점수는: \(score), 이전 점수는: \(oldValue)")
   }
}
score = 5
// "현재 점수는: 5, 이전 점수는: 0"
```

------













# *NavigationController











# * UITapBarController





# * Study more

### - Enum

### - Closure

### - initializer

### - self 호출 -> 객체지향

### - viewController : contain, contents

### - lazy

#### - 값 타입을 위한 이니셜라이저 델리게이션(Initializer Delegation for Value Types)

#### [Initialize 참조1](http://minsone.github.io/mac/ios/swift-initialization-summary)

#### - get,set을 사용하는 경우 / 3. property를 private하게 사용하기 위해 [참조](https://medium.com/ios-development-with-swift/%ED%94%84%EB%A1%9C%ED%8D%BC%ED%8B%B0-get-set-didset-willset-in-ios-a8f2d4da5514)
