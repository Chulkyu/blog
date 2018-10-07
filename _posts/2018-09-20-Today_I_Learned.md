---
layout: post
title: Today I Learbed
date: 2017-09-20 17:00:00 +0300
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

##### - 객체지향 프로그래밍이란 캡슐화, 다형성, 상속 을 이용하여 코드 재사용을 증가시키고, 유지보수를 감소시키는 장점을 얻기 위해서 객체들을 연결시켜 프로그래밍 하는 것

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



### * Class initialize

##### - self : 메모리에 올라간 함수? 클래스? 를 다시 호출할 때 쓰는 용어

##### - lazy : lazy의 변수가 처음 호출될 때 초기화값이 할당됨



## * Access Control

##### - 다른 모듈의 코드 또는 다른 소스 파일 등으로부터 접근을 제한하는 것

##### - 세부 구현 내용을 숨기고 접근할 수 있는 인터페이스 지정 가능

##### - open > public > ( internal > fileprivate > private )





# * Study more

### - Enum

### - Closure

### - initializer

### - self 호출
