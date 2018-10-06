---
layout: post
title: About Swift Language
date: 2018-10-06 15:35:00 +0300
description: Learning Swift Language
img: software.jpg # Add image post (optional)
tags: [Productivity, Software] # add tag
---


# Swift Language

#### - 스위프트는 안전하고 빠르며 상호작용 하는 프로그래밍 언어이다. 폰, 데스크탑, 서버 외 어떤 것에서도 코드를 짜기에 aws ome한 방법이다. 개발하는데 있어 컴파일러와 랭귀지 모두 최적화 되어 있다.

#### - 새로운 프로그래머들도 배우기에 직관적이고 재밌게 배울 수 있다. 플레이그라운드에서 코드를 작성해 보면 빌드를 하거나 앱을 직접 돌려볼 필요 없이 결과를 즉시 알 수 있다.

- #### 변수는 항상 사용전에 initialized를 해주어야 한다.

- #### Array 인덱스 범위를 벗어나는 것을 체크

- #### Optional에서는 nil 값을 핸들링 해주어야 한다.

- #### 메모리 관리를 자동적으로 해준다

- #### 예기치 않은 오류의 처리 방법을 제안

#### - Swift는 타입 추론, 패턴 매칭, 간결한 syntax를 결합하여 복잡한 Ideas를 명확하고 간결하게 표현할 수 있다. 덕분에 코드는 쓰기 쉬울 뿐만 아니라 읽고 유지보수 하기도 쉽다.



# * A Swift Tour

#### swift에서 "Hello, World"를 print하기는 매우 간단하다.

```swift
print("Hello, world")
```



- ### Simple Values

#### use **'let'**  to make a constant, **'var'** to make a variable

#### - 변수는 항상 사용전에 initialized를 해주어야 한다.

```swift
var myVariable = 42
myVariable = 50
let myConstant = 42
```



#### - 변수에 값을 바로 넣어주지 않을 때에는 타입을 명확히 정해주어야 한다.

```swift
var myVariable: Int
myVariable = 42
myVariable = 50
let myConstant: Int
myConstant = 42
```



#### - Swift에서는 변수의 값이 명확하다면 자동으로 **'타입추론'**이 되기 때문에 타입을 굳이 적어줄 필요가 없다.(타입을 정해주어야 할 경우에만 타입 지정)

```swift
let explicitDouble: Double = 70	// type Double
let expliciFloat: Float = 70	// type Float

let implicitInteger = 70	// type Int
let implicitDouble = 70.0	// type Double
```



#### - 타입이 정해지면 변수에 다른 타입의 값을 넣을 수 없으며, 타입이 다른 변수와는 연산이 불가능하다.

```swift
let label = "The width is"	// type String
let width = 94				// type Int
label = 15					// error String != Int
width = "The Label is"		// error Int != String
let widthLabel = label + width // error String + Int
```



#### - 이를 가능하게 하기 위해서는 type convert(타입 전환)을 해주어야 한다.

#### 1. 변환시킬 타입을 앞에 적어주기

```swift
let widthLabel = label + String(width)
// "The width is 94
// (label: String) + (width: Int -> String)
```

#### 2. 보간법 : 백슬러시 (width)

##### - 숫자열을 문자열로 타입변환 시킬 때 사용

```swift
let apples = 3	// type Int
let oranges = 5	// type Int
let appleSummary = "I have \(apples) apples."
// "I have 3 apples."
let fruitSummary = "I have \(apples + oranges) pieces of fruit."
// "I have 8 pieces of fruit."

let strawberries = 2	// type Int
let bananas = 4.5		// type Double
let fruitSummary2 = "I have \(strawberries + bananas) pieces of fruit."
// error \(strawberries + bananas)
// error can't \(Int + Double)

let height = 180.3
let weight = 73.6
let introduce = "Hi, my height is \(height), weight is \(weight). Am I healthy? "
// "Hi, my height is 180.3, weight is 73.6. Am I healthy?"
```



#### - quotation(인용구) marks(""") : 변수에 여러줄의 문장을 입력할 때 사용

```swift
let quotation = """ Even though there's whitespace to the left, the actual lines aren't indented. Except for this line. Double quotes can appear without being escaped. """
```



#### - Using brackets([ ]) : array, dictionary 만들 때 사용

#### 접근 방법 array[index], dictionary["key"]

```swift
// array
var shoppingList = ["catfish", "water", "tulips"]
shoppingList[1] = "bottle of water"
// shoppingList = ["catfish", bottle of water", "tulips"]

// array 요새 추가하기
shoppingList.append("blue paint")
// shoppingList = ["catfish", "bottle of water", "tulips", "blue paint"]

// dictionary
var occupations = ["Malcolm": "Captain","Kaylee": "Mechanic",]
occupations["Jayne"] = "Public Relations"
// occupations = ["Malcolm": "Captain","Kaylee": "Mechanic", "Jayne": "Public Relations"]
```



#### - 빈(empty) array, dictionary 만들기, use the initializer syntax

```swift
let emptyArray = [String]()
let emptyDictionary = [String: Float]()
//array 와 dictionary 도 마찬가지로 값을 나중에 입력할 때는 타입을 명확히 적어주어야 한다.
```



#### - 타입을 유추(이미 한번 타입이 정해졌던 경우) 할 수 있을 경우 빈 array, dictionary

##### - for example, when you set a new value for a variable or pass an argument to a function

```swift
shoppingList = ["catfish", "bottle of water", "tulips", "blue paint"]
shoppingList = []

occupations = ["Malcolm": "Captain","Kaylee": "Mechanic", "Jayne": "Public Relations"]
occupations = [:]
```
