---
layout: post
title: Swift Enumerations and Structures
date: 2018-10-09 21:24:00 +0300
description: About Swift Enumerations and Structures # Add post description (optional)
img: Swift-Enumerations-and-Structures.png # Add image post (optional)
tags: [Swift, Enumerations, enum, struct, Structures, Developer, Apple, Xcode, 스위프트] # add tag
---

- ## Enumerations and Structures

####  "enum은 관련된 값의 그룹에 대한 공통 유형을 정의하며 코드에서 유형이 안전한 방식으로 해당 값으로 작업 할 수 있게 한다. 또한, rawValue 라고 알려진 값이 각각의 enum case에 제공 되어 string, character, integer, floating-point 값으로도 될 수 있다." - apple 공식문서

#### - enumerations는 eunm case 에 관련된 methods를 가질 수 있다.

#### - enum의 타입은 enum의 rawValue 값의 타입을 결정한다.

- ### rawValue type: Int

#### - 특별히 설정하지 않으면 case 처음 순서대로 rawValue 0, 1, 2, 3...

#### - 중간의 case에 따로 정수(ex 75)를 지정하면 지정한 case 전에는 0,1,2,3..의 순서대로 rawValue값을 가지다가 따로 지정한 case 다음부터는 지정한 case의 rawValue값 + 1, + 2, +3...의 값을 가진다(76, 77, 78)

#### - rawValue는 고유한 값을 가져야 하기 때문에 0, 1, 2, 3, 1 과 같은 같은 값을 가지게 설정 할 수 없다.

- ### rawValue type: String

#### - 특별히 설정하지 않으면 case의 이름을 그대로 문자열로 가져온다.

#### - 중간의 case에 다른 문자열을 rawValue값으로 넣어줘도 다른 case들은 그대로 case 이름을 문자열로 갖는다.

------

```swift
enum Rank: Int {
    case ace
    case two, three, four, five, six, seven, eight, nine, ten
    case jack
    case queen = 75		// queen.rawValue = 75
    case king

    func simpleDescription() -> String {
        switch self {
        case .ace:
            return "ace"
        case .jack:
            return "jack"
        case .queen:
            return "queen"
        case .king:
            return "king"
        default:
            return String(self.rawValue)
        }
    }
}
let ace = Rank.ace						// ace
let aceRawValue = ace.rawValue			// 0
let twoRawValue = Rank.two.rawValue		// 1
let queenRawValue = Rank.queen.rawValue // 75
let kingRawValue = Rank.king.rawValue	// 76

let jack = Rank(rawValue: 10)			// jack
```

#### - rawValue값을 가지고 enum을 인스턴스화 시킬 수 있다.

```swift
let jack = Rank(rawValue: 10)			// jack
(type of jack)	// Rank?
```

##### * jack의 타입이 Rank?(Optional)인 이유는 enum에서 정의되지 않은 rawValue값으로 생성할 경우 nil 을 반환하기 때문

#### - Optional이기 때문에 unwrapping 하여 사용해야 한다.

```swift
if let jack = Rank(rawValue: 10) {
    let threeDescription =
    jack.simpleDescription()
}
```

------

#### - enum을 예측할 수 있다면 enum의 이름 생략 가능.

```swift
// 변수에 type annotation으로 enum 명시
let trumpCard: Rank = .ace
// Rank.ace -> .ace (enum 이름 생략 가능)

// 함수 선언에 parameter type annotation으로 enum 명시
func doSomething(with trumpCard: Rank) {

}
// 마찬가지로 doSomthing(with: Rank.king)에서 enum 이름 생략 가능
doSomething(with: .king)
```

------

#### - case의 values가 enum의 실제 values이다. rawValue는 유의미한 경우가 아니면 지정해주지 않아도 된다.

```swift
enum Suit {
    case spades, hearts, diamonds, clubs

    func simpleDescription() -> String {
        switch self {
        case .spades:
            return "spades"
        case .hearts:
            return "hearts"
        case .diamonds:
            return "diamonds"
        case .clubs:
            return "clubs"
        }
    }

    func color() -> String {
        switch self {
        case .spades:
            return "black"
        }
    }
}
let hearts = Suit.hearts		// hearts
let heartsDescription = hearts.simpleDescription()
// "hearts"



```

------

- ### Value Association

#### - rawValue를 따로 설정하지 않고, 각 case마다 parameter를 설정해 줄 수 있다. 이로써 어떠한 헝태의 다른 값이라도 enum의 각각의 case에 독립적으로 연동하여 사용할 수 있다.(인스턴스화 시킬때)

```swift
enum PaperSize{
    case A4(width :Int, height :Int), A5(color: String), Letter(count: Int)

    func desc() -> String
    {
        switch(self) {
        case let .A4(width, height):
            return "Width is \(width), Heigh is \(height)"
        case let .Letter(count):
            return "Total \(count) Letter(s)"
        case let .A5(color):
            return "A5 color is \(color)"

// 모든 case의 경우가 쓰여졌기 때문에 default는 필요 없다.
//        default :
//            return "Quit"
        }
    }
}

// 각각의 case에 다른 값들로 인스턴스화 시켜서 쓸 수 있다.
let paperA4 = PaperSize.A4(width :210, height :297)
let paperLetter = PaperSize.Letter(count: 1)
let paperA5Color = PaperSize.A5(color: "White")
paperA4.desc() //"Width is 210, Heigh is 297"
paperLetter.desc() //"Total 1 Letter(s)"
paperA5Color.desc() // "A5 color is white"
```

```swift
enum ServerResponse {
    case result(String, String)
    case weather(String)
    case failure(String)
}

let success = ServerResponse.result("6:00 am", "8:09 pm")
let failure = ServerResponse.failure("Out of cheese.")
let weather: ServerResponse = .weather("Sunny")

switch success {
case let .result(sunrise, sunset):
    print("Sunrise is at \(sunrise) and sunset is at \(sunset).")
case let .failure(message):
    print("Failure...  \(message)")
case .weather(let weather):
    print("Today weather is \(weather)")
}

success
// Prints "Sunrise is at 6:00 am and sunset is at 8:09 pm."

```



------

#### - enum의 연관값을 꺼내올 수 있는 방법

- #### if - case

- #### switch

```swift
enum NetworkError {
  case invalidParameter(String, String)
  case timeout
}

let error: NetworkError = .invalidParameter("email", "이메일 형식이 올바르지 않습니다.")
```

```swift
if case .invalidParameter(let field, let message) = error {
  print(field) // email
  print(message) // 이메일 형식이 올바르지 않습니다.
}

switch error {
case .invalidParameter(let field, let message):
  print(field) // email
  print(message) // 이메일 형식이 올바르지 않습니다.

default:
  break
}
```

------

#### * Optional도 enum이기 때문에 값을 똑같이 꺼내올 수 있다.

```swift
public enum Optional<Wrapped> {
  case none
  case some(Wrapped)
}
```

```swift
let age: Int? = 20

switch age {
case .none: // `nil`인 경우
  print("나이 정보가 없습니다.")

case .some(let x) where x < 20:
  print("청소년")

case .some(let x) where x < 65:
  print("성인")

default:
  print("어르신")
}
```

------

- ## Struct

#### - class와 매우 유사하다.

#### struct 안에 property, initializer, method 선언 가능.

#### - 데이터 타입(Data Type)을 정의하기 위한 용도?

#### - class와 차이점

- ##### struct는 상속(derive) 불가능하기 때문에 오버라이드(override)도 불가능

- ##### property를 변경하는 method에 반드시 mutating 이라는 지시어를 붙여야 인스턴스화 될 때 값의 변경을 일으키는 동작을 제어 할 수 있다.

#### * 클래스와 가장 큰 차이점

- #### class : call by reference

- #### struct : call by value

```swift
// Value

var a = 10
var b = 5

a = b       // a에 b의 value만 전달
// a = 5, b = 5

b = 999		// b의 값이 바뀌어도 a의 값은 변하지 않는다.
a           // 5
b           // 999
```

```swift
// Reference

class SomeClass {
    var value = 0

    init(value: Int) {
        self.value = value
    }
}

var obj1 = SomeClass(value: 10)
var obj2 = SomeClass(value: 20)

obj1.value          // 10
obj2.value          // 20

obj1 = obj2			// obj1에 obj2의 메모리 주소 자체를 전달
obj1.value          // 20
obj2.value          // 20

obj2.value = 100	// 둘 중 하나의 값이 변하면 둘 다 값이 변한다.
obj1.value          // 100
obj2.value          // 100
```

------

- #### class : call by reference

#### - class의 경우(Reference type) Stack에 레퍼런스, Heap에 구조체 할당

![call-by-reference1](/Users/maru/Desktop/blog/flexible-jekyll/assets/img/call-by-reference1.png)

#### - Reference 타입은 복사해도 값이 하나를 향해 같은 값을 가짐

![call-by-reference2](/Users/maru/Desktop/blog/flexible-jekyll/assets/img/call-by-reference2.png)

![call-by-reference3](/Users/maru/Desktop/blog/flexible-jekyll/assets/img/call-by-reference3.png)



------

- #### struct : call by value

#### - struct(Value type)의 경우  포인트가 stack에만 쌓이고 복사해도 stack만 사용

![call-by-value1](/Users/maru/Desktop/blog/flexible-jekyll/assets/img/call-by-value1.png)

![call-by-value2](/Users/maru/Desktop/blog/flexible-jekyll/assets/img/call-by-value2.png)

#### - Value 타입의 경우 복사해도 분리됨

![call-by-value3](/Users/maru/Desktop/blog/flexible-jekyll/assets/img/call-by-value3.png)



#### [enum,struct 참조1](https://devxoul.gitbooks.io/ios-with-swift-in-40-hours/content/Chapter-3/enums.html)

#### [enum,struct 참조2](https://academy.realm.io/kr/posts/letswift-swift-performance/)

------
