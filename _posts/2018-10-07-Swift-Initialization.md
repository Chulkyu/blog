---
layout: post
title: Swift Initialization
date: 2018-10-07 16:11:00 +0300
description: About Swift Initialization # Add post description (optional)
img: software.jpg # Add image post (optional)
tags: [Swift, Initialization, Developer, Apple, Xcode] # add tag
---

### * Initialize(초기화), Deinitialize

##### - 일반적으로 OOP에서는 생성자(Constructor)와 파괴자(Destructor) 라는 개념이 존재. 객체의 탄생과 사라지는 시점에 맞춰 시작과 끝에 호출되는 메소드.

##### - 스위프트에서는 초기화(Initialization)와 마무리(Deinitialization)라는 개념의 용어를 사용.

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

------
